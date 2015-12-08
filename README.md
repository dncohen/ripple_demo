# Dependencies

Requires node version v0.12.7 (or greater, but tested on that version).

run:

~~~
npm install
~~~

# Decommissioning wallets

Decommissioning a wallet means all it's balances will be returned to issuers, trust lines will be removed, and order will be removed.  XRP in excess of minimum reserves may be sent to another wallet.

Open `decommission.conf` and edit appropriately.  You will want to change the addresses where XRP is returned to.

Run the decommission script for example like this, to decommission 5 wallets:

~~~
./decommission --xrp rUakSGuVF1GAPws34371B9KcX8L1dfpXni r3mi3YYwWJXcBtGUjkmmy7Dskj2GswKYx7 rh4Akk3AUnBuqJePfLB4TbhBFQrwUMF1re rpLZCcKZPnAhX1rQEyhcLMsfqvhuir3BaK rhXyyNVRbVdUMbSzBzMR3rJct75CeEdFdy
~~~

The order of clearing out trustlines matters.  Put market makers first on the command line.  Then hot wallets, then cold wallets.

You will be prompted for the secret for each wallet that has placed orders, or has trust lines to zero out, or XRP to return

Use `-a` or `--altnet` to decommission altnet wallets.

Use `-x` or `--xrp` to return excess XRP.

Use `decommission --help` for more information.


# Dependencies (old - the information that follows was written for scripts that require ripple-rest and may no longer work)

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
