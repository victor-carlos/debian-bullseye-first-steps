# debian-bullseye-first-steps

This README contains an essential instructions for use after the Debian installation.

**DISCLAIMER:** I use this script on my Debian installations. There is no guarantee of successful installations. Errors can happen and packages can become obsolete. **Use at your own risk**

---

## Basic Configuration

  dpkg --add-architecture i386
  
  apt-get update

## Removing Firefox ESR
  apt-get install firefox-esr -y

## Firefox Installation
  cd /home/$USER/Downloads/
  
  tar -jxvf firefox-*.bz2
  
  mv firefox /opt/
  
  ln -s /opt/firefox/firefox /usr/bin/firefox
  
  rm -rf /opt/firefox/plug-ins
  
  mkdir /usr/lib/mozilla
  
  mkdir /usr/lib/mozilla/plug-ins
  
  ln -sf /usr/lib/mozilla/plug-ins /opt/firefox/plug-ins
  
  chown -c -R $USER /opt/firefox
  
  touch /usr/share/applications/firefox.desktop
  
  cat <<EOF >/usr/share/applications/firefox.desktop
  [Desktop Entry]
  
  Version=1.0
  
  Encoding=UTF-8
  
  Name=Firefox Web Browser
  
  GenericName=Firefox
  
  Name[pt]=Firefox Navegador Web
  
  Comment=Navegador WEB
  
  Exec=firefox
  
  Type=Application
  
  Categories=Application;Internet;Network;WebBrowser;
  
  Icon=/opt/firefox/browser/chrome/icons/default/default128.png
  
  EOF
  
## Codecs ans Plugins
  apt-get install faad ffmpeg2theora icedax mjpegtools mpeg2dec mpeg3-utils mpegdemux mpg123 mpg321 x264 arj p7zip unrar unrar-free gstreamer1.0-plugins-* pulseaudio-module-bluetooth -y
 
## Apps
  apt-get install deluge gparted gpart kdenlive audacity inkscape youtube-dl vlc gimp simplescreenrecorder krita git qmmp wine spectre-meltdown-checker desktop-file-utils libblockdev-mdraid2 libblockdev-mdraid-dev ksystemlog chromium falkon curl telegram-desktop elisa -y

## Installing YOUTUBE-DL
  sudo wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O /usr/bin/yt-dlp

  sudo chmod a+rx /usr/bin/yt-dlp

