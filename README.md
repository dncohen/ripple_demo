# Dependencies

## Ubuntu

~~~
sudo apt-get install python3-pip
pip3 install requests
~~~

# Setup

~~~
cd ripple_demo
cp examples/market_mover.conf .

# Edit ./market_mover.conf
~~~

# Run

~~~
# Run once, will place one buy and one sell order.
./market_mover

# Run every 10 seconds.  One buy and sell each time.
watch -n 10 ./market_mover
~~~
