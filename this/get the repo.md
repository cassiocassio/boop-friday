example file inside a dir

quick edit

# get the repo
  git clone https://github.com/juju/juju-gui
  cd juju-gui

# or another's branches
  git remote add frankban https://github.com/frankban/juju-german vatgui

# see the branches
git remote -v

# update branches
git fetch origin
git fetch frankban

# switch to a branch
git checkout ssh-spike
git checkout main

# make from scratch
make clean-all
# then
make sysdeps
# finally make and run
make deps fast-babel gui run

# get the proxy (first time)
sudo apt install golang-go
export GOPATH=~/stuff
go get github.com/juju/guiproxy
cd ~/stuff/bin

# open the proxy - payment version
./guiproxy -controller jimm.staging.jujucharms.com:443 -config 'gisf: true, jujuEnvUUID:"", paymentURL: "https://api.staging.jujucharms.com/payment/", payFlag: true, stripeKey: "pk_test_YmLJ2j3tAHqKN3Czwyq5ly91", combine: false, accountFlag: true'

# simple version
./guiproxy -controller jimm.staging.jujucharms.com:443 -config 'gisf: true, jujuEnvUUID:"http://localhost:8042/"'

# with status
./guiproxy -controller jimm.staging.jujucharms.com:443 -config 'gisf: true,jujuEnvUUID:"http://localhost:8042/", flags: {"status": true}'
