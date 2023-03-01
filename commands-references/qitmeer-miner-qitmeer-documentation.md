# Qitmeer-Miner :: Qitmeer Documentation

### Qitmeer-Miner user guide <a href="#qitmeer-miner-user-guide" id="qitmeer-miner-user-guide"></a>

_**qitmeer-miner**_ is the miner tool for _**qitmeer**_ network , it can get reward by generate block.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

Update Go to version at least 1.12 (required >= **1.12**)

Check your golang version

```
$ go version >= 1.12
$ cargo >= 1.36.0 (c4fcfb725 2019-05-15)
```

### Compile <a href="#compile" id="compile"></a>

```
$ git clone git@github.com:Qitmeer/qitmeer-miner.git
$ cd lib/cuckoo
$ cargo build --release
```

* Ubuntu ENV

```
$ sudo apt-get install beignet-dev nvidia-cuda-dev nvidia-cuda-toolkit
$ go build 
```

* Centos ENV

```
$ sudo yum install opencl-headers
$ sudo yum install ocl-icd
$ sudo ln -s /usr/lib64/libOpenCL.so.1 /usr/lib/libOpenCL.so
$ go build
```

* MAC
* Windows ENV

**Prequisite:**

1. Install **Build Tools for Visual Studio**:\
   [https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools\&rel=16](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools\&rel=16)
2. Build

**Any questions can see** [**issues**](https://github.com/Qitmeer/qitmeer-miner/issues?q=is%3Aissue+is%3Aclosed) **or can** [**create**](https://github.com/Qitmeer/qitmeer-miner/issues/new)

### Run <a href="#run" id="run"></a>

```
$ cp qitmeer.conf.example qitmeer.conf
```

* 1.run with the config file `qitmeer.conf`
* 2.run with command

```

- 1.run with the config file `qitmeer.conf`
- 2.run with command
```

```
$ ./qitmeer-miner -h
Usage:
    qitmeer-miner [OPTIONS]

Debug Command:
  -l, --listdevices    List number of devices.

The Config File Options:
  -C, --configfile=    Path to configuration file
      --minerlog=      Write miner log file

The Necessary Config Options:
  -P, --pow=           blake2bd|cuckaroo|cuckatoo (blake2bd)
  -S, --symbol=        Symbol (PMEER)
  -N, --network=       network privnet|testnet|mainnet (mainnet)

The Solo Config Option:
  -M, --mineraddress=  Miner Address
  -s, --rpcserver=     RPC server to connect to (127.0.0.1)
  -u, --rpcuser=       RPC username
  -p, --rpcpass=       RPC password
      --randstr=       Rand String,Your Unique Marking. (Come from Qitmeer!)
      --notls          Do not verify tls certificates (true)
      --rpccert=       RPC server certificate chain for validation

The pool Config Option:
  -o, --pool=          Pool to connect to (e.g.stratum+tcp://pool:port)
  -m, --pooluser=      Pool username
  -n, --poolpass=      Pool password

The Optional Config Option:
      --cpuminer       CPUMiner (false)
      --proxy=         Connect via SOCKS5 proxy (eg. 127.0.0.1:9050)
      --proxyuser=     Username for proxy server
      --proxypass=     Password for proxy server
      --trimmerTimes=  the cuckaroo trimmer times (40)
      --intensity=     Intensities (the work size is 2^intensity) per device. Single global value or a comma
                       separated list. (24)
      --worksize=      The explicitly declared sizes of the work to do per device (overrides intensity). Single
                       global value or a comma separated list. (256)
      --timeout=       rpc timeout. (60)
      --use_devices=   all gpu devices,you can use ./qitmeer-miner -l to see. examples:0,1 use the #0 device
                       and #1 device
      --max_tx_count=  max pack tx count (1000)
      --max_sig_count= max sign tx count (5000)
      --log_level=     info|debug|error|warn|trace (debug)
      --stats_server=  stats web server (127.0.0.1:1235)
      --edge_bits=     edge bits (24)
      --local_size=    local size (4096)
      --group_size=    work group size (256)

Help Options:
  -h, --help           Show this help message
```

### Stats Web Server <a href="#stats-web-server" id="stats-web-server"></a>
