# Maintainer: Justin Dray <justin@dray.be>
# Maintainer: Daniel Egeberg <daniel.egeberg@gmail.com>
pkgname="nzbdrone-torrents"
pkgver="2.0.0.2221"
pkgrel=1
pkgdesc="PVR for newsgroup users"
arch=(any)
url="http://www.nzbdrone.com"
license=('GPL3')
depends=('mono' 'libmediainfo' 'sqlite')
optdepends=('sabnzbd: an NZB downloader'
            'nzbget: an NZB downloader'
	    'transmission: a torrent downloader'
	    'deluge: a torrent downloader')
install='nzbdrone.install'
provides='nzbdrone'
conflicts='nzbdrone'
changelog=
source=("http://update.nzbdrone.com/v2/torrents/mono/NzbDrone.torrents.${pkgver}.mono.tar.gz"
        "nzbdrone.sh"
        "nzbdrone.service")
noextract=()
md5sums=('4b9e41c7c03e9f0b132fc3ce687aa64a'
         '3b61cab484404951eb5d2c0cf760da07'
         '42cdce41e518760ea9769bacd840a113')

package() {
    cd $srcdir

    msg2 "Install NzbDrone in /usr/lib"
    install -d -m 755 "${pkgdir}/usr/lib/NzbDrone"
    cp -dpr --no-preserve=ownership "${srcdir}/NzbDrone" "${pkgdir}/usr/lib"

    msg2 "Install executable into /usr/bin"
    install -D -m755 "${srcdir}/nzbdrone.sh" "${pkgdir}/usr/bin/nzbdrone"

    msg2 "Install nzbdrone.service"
    install -D -m 644 "${srcdir}/nzbdrone.service" "${pkgdir}/usr/lib/systemd/system/nzbdrone.service"
}
