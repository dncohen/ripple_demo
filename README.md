# Dependencies

## RHEL / Centos

~~~
sudo yum install python-requests python-argparse
~~~

## Ubuntu

~~~
sudo apt-get install python3-pip

pip3 install requests
# or,
apt-get install python3-requests
~~~

## Mac

~~~
brew install python3
pip3 install requests
~~~

# Market Mover

## Setup Market Mover

~~~
cd ripple_demo
cp examples/market_mover.conf .

# Edit ./market_mover.conf
~~~

## Run Market Mover

~~~
# Run once, will place one buy and one sell order.
./market_mover

# Run every 10 seconds.  One buy and sell each time.
watch -n 10 ./market_mover
~~~

# Ripple Connect Status Check

Displays a summary of how liquid the markets and hot wallets are.
Parses Ripple Connect config files to determine which wallets to
inspect.

## Run Ripple Connect status check

~~~
./ripple_connect_status
~~~
