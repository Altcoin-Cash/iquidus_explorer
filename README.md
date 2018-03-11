Iquidus Block chain Explorer configured and modified by xixmexix
setup and running on ubuntu 14.04


apt-get update
apt-get -y upgrade
apt-get -y dist-upgrade
apt-get install -y nano htop git curl
apt-get install -y build-essential libtool autotools-dev pkg-config libssl-dev
apt-get install -y libboost-all-dev
apt-get install -y libevent-dev
apt-get install -y libminiupnpc-dev
apt-get install -y autoconf
apt-get install -y automake unzip libgmp-dev
apt-get install -y software-properties-common
add-apt-repository -y ppa:bitcoin/bitcoin
apt-get update
apt-get install -y libdb4.8-dev libdb4.8++-dev
cd /var
touch swap.img
chmod 600 swap.img
dd if=/dev/zero of=/var/swap.img bs=1024k count=2000
mkswap /var/swap.img
swapon /var/swap.img
free
echo "/var/swap.img none swap sw 0 0" >> /etc/fstab
cd


<compile your coin wallet and sync it>


sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
sudo apt-get update
sudo apt-get install -y mongodb-org
apt-get install upstart-sysv -y
reboot
sudo service mongod start
apt-get update
apt-get install nodejs nodejs-legacy -y
apt-get install npm -y
apt-get update
sudo mongo
> use explorerdb
> db.createUser( { user: "coindrpc", pwd: "Thisisapasswordyouwillmakeup", roles: [ "readWrite" ] } )
> exit
cd\

git clone https://github.com/xixmexix/iquidus_explorer.git explorer
cd explorer
npm install --production
cp ./settings.json.template ./settings.json
-Modify the Settings File
./dv7coind -daemon -txindex
npm start

-log in with different putty window
node scripts/sync.js index reindex
sudo node scripts/sync.js index update
sudo node scripts/peers.js index update 
sudo npm install forever -g
sudo npm install forever-monitor
apt-get install gnome-schedule -y
sudo crontab -e
*/1 * * * * cd ./explorer && /usr/bin/nodejs scripts/sync.js index update > /dev/null 2>&1
*/2 * * * * cd ./explorer && /usr/bin/nodejs scripts/sync.js market > /dev/null 2>&1
*/5 * * * * cd ./explorer && /usr/bin/nodejs scripts/peers.js > /dev/null 2>&1