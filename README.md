# cowpatty
Cowpatty
apt-get install build-essential
apt-get install libssl-dev
apt-get install libpcap0.8-dev
apt-get install libdigest-hmac-perl
wget http://proton.cygnusx-1.org/~edgan/cowpatty/cowpatty-4.6-fixup16.patch
patch < cowpatty-4.6-fixup16.patch
make
make install
cd ..
cowpatty

Если все пойдет хорошо, вы должны увидеть cowpatty меню помощи: 
cowpatty 4.6 - WPA-PSK dictionary attack. 
cowpatty: Must supply a pcap file with -r

параметры

-f файл словарь
-d Хэш файл (genpmk)
-r файл Захват пакетов
-s SSID сети (вложить в кавычки, если SSID содержит пробелы)
-c Проверить по уважительным 4-полосных кадров, не трескается
-h Распечатать эту справочную информацию и выйти
-v Версия для печати подробных сведений (более-V для получения дополнительной многословия)
-V Версия для печати программы и выход

#/bin/bash
echo -e "\n \e[1;31m[*] Installing build-essential\e[0m"
sudo apt-get -y install build-essential
echo -e "\n \e[1;34m[*] Installing libssl-dev\e[0m"
sudo apt-get -y install libssl-dev 
echo -e "\n \e[1;34m[*] Installing libpcap0.8-dev\e[0m"
sudo apt-get -y install libpcap0.8-dev 
echo -e "\n \e[1;34m[*] Installing libdigest-hmac-perl\e[0m"
sudo apt-get -y install libdigest-hmac-perl 
echo -e "\n \e[1;34m[*] Downloading cowpatty-4.6.tgz\e[0m"
wget http://wirelessdefence.org/Contents/Files/cowpatty-4.6.tgz 
md5sum cowpatty-4.6.tgz 
echo "\e[1;34mMD5 SHOULD BE b90fd36ad987c99e7cc1d2a05a565cbd\e[0m"
echo -e "\n \e[1;34m[*] Extracting cowpatty-4.6.tgz\e[0m"
tar -xvf cowpatty-4.6.tgz > /dev/null
cd cowpatty-4.6 > /dev/null
echo -e "\n \e[1;34m[*] Downloading Cowpatty Patch\e[0m"
wget http://proton.cygnusx-1.org/~edgan/cowpatty/cowpatty-4.6-fixup16.patch
echo -e "\n \e[1;34m[*] Patching Cowpatty code"
patch < cowpatty-4.6-fixup16.patch
echo -e "\n \e[1;34m[*] Compiling Cowpatty\e[0m"
make
echo -e "\n \e[1;34m[*] Installing cowpatty to system\e[0m"
sudo make install
echo -e "\n \e[1;34m[*] Removing Cowpatty Directory\e[0m"
cd .. > /dev/null
rm -r -f cowpatty-4.6 > /dev/null
echo -e "\n \e[1;34m[*] Removing cowpatty-4.6.tgz\e[0m"
rm cowpatty-4.6.tgz > /dev/null
echo -e "\n \e[1;34m[*] testing to see if cowpatty works\e[0m"
cowpatty
echo -e "\n \e[1;34m[*] Done!\e[0m"
-------------------------------------------------------------------------------------------------
tar zxfv cowpatty-4.6.tgz
cd cowpatty-4.6
make cowpatty
cp cowpatty /usr/bin
