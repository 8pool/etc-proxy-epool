#Description

# Epool Supported etc-proxy for Linux

This is Stratum Proxy for Ethereum based pools (RPCv2) using asynchronous networking written in Python Twisted.
Originally developed for DwarfPool http://dwarfpool.com/eth

#Features

* Additional up to 20% increase of earning compared to standard pools
* ETC stratum proxy
* Automatically failover via proxy
* Only one connection to the pool
* Workers get new jobs immediately
* Submit of shares without network delay, it's like solo-mining but with benefits of professional pool
* Central Wallet configuration, miners doesn't need wallet as username
* Support monitoring via email
* Bypass worker_id for detailed statistic and per rig monitoring
* pass submitHashrate to pool

#How it works
```
   Pool A <---+                        +-------------+ Rig1 / PC1
 (Active)      |                       |
               |                       +-------------+ Rig2 / PC2
               |                       |
  Pool B <---+-----StratumProxy  <-----+-------------+ Rig3 / PC3
(FailOver)                             |
                                       +-------------+ Rig4 / PC4
                                       |
                                       +-------------+ Leaserigs
```

#ToDo

* ---


#Configuration

* all configs in file  etc-proxy.conf


#Command line to miner start, recommended farm-recheck to use with stratum-proxy is 200

* ./ethminer --farm-recheck 200 -G -F http://127.0.0.1:8080/rig1


#External script to restart proxy (made by rain)

* https://paste.ubuntu.com/15327007/


# Proxy working check

* To check that proxy works open in browser http://127.0.0.1:8080/ (or your changed ip and port from config)
* If you see "Ethereum Classic stratum proxy" and some infos about connections.
* If not then mostly case that you have application running on this port, at example Antivirus.


#Donations

* ETH:  0xe9a7e26bf5c05fe3bae272d4c940bd7158611ce9


#Requirements

etc-proxy is built in python. I have been testing it with 2.7.3, but it should work with other versions. The requirements for running the software are below.

* Python 2.7+
* python-twisted


#Installation and start

* [Linux]
1) install twisted
```
 apt-get install python-twisted
```

2) start proxy with
```
 python ./etc-proxy.py
```

#Credits

* Original version by Slush0 (original stratum code)
* More Features added by GeneralFault, Wadee Womersley and Moopless
* Dwarfpool eth-proxy

#License

* This software is provides AS-IS without any warranties of any kind. Please use at your own risk.
