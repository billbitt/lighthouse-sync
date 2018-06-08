# lighthouse-sync for spee.ch

This repo is a fork of [lighthouse-sync](https://github.com/filipnyquist/lighthouse-sync) created by @filipnyquist. It has been modified slightly to sync claims into a mysql table for use with spee.ch.

## how to run this repository locally

### clone & this repo

```
git clone https://github.com/billbitt/spee.ch-sync
npm install
```

### start mysql

create a database called `lbry`

create a copy of `config/sequelizeCliConfig.js` that contains your mysql credentials

### start lbrycrd

install the latest release of [`lbrycrd`](https://github.com/lbryio/lbrycrd/releases)

start lbrycrdd and leave running 

```
./lbrycrdd -server -txindex -rpcuser=lbry -rpcpassword=lbry
``` 

### start the lbry block decoder
Clone the repo 

```
git clone https://github.com/cryptodevorg/lbry-decoder
```

Be sure that you have python 2.7 and pip installed

```
sudo pip install -r requirements.txt
````

Configure the `config.json` file to your lbrycrd daemon settings. (i.e. edit the `config.json` to change the port to `9245`)

start the decoder and leave running

```
python decoder.py
``` 

### start the sync tool
```
node sync.js
```
