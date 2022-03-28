# Technical Requirements

## The Basics

Since GBC is a smaller-stakes environment, it is a great place to refine new skills. Be sure to read instructions carefully and ask questions ([discord channel](https://t.co/yrSN2dS9Z2)) as needed.

* **Using the Terminal**:  You will be required to enter commands into a terminal window. These will be simple copy-paste instructions, but familiarity with using a terminal is helpful.&#x20;
* **Key Management**: You will use the command line to derive a key-pair for validating blocks as well as a mnemonic you will use later to derive a withdrawal pair. It is important to store these safely (offline highly recommended).

### Connectivity

A reliable internet connection is key - bandwidth should not be throttled or capped. Upload bandwidth should be a minimum of 700 MB/hour with increases likely. Brief periods offline may result in small inactivity penalties, but this will be recouped quickly as long as the outage is short.

Note that synching the execution layer Gnosis Chain may take up to 12 hours depending on your setup.&#x20;

### Security

When setting up hardware or a VM, use proper security measures including securing the root account, setting up a firewall, and forwarding necessary ports to the correct machines from the router.

* OpenEthereum & Nethermind: 30303 TCP/UDP
* Prysm & Lighthouse: 12000 UDP, 13000 TCP

### Time Sync

Your clock should be synchronized to prevent skipping block sealing.

&#x20;Enter`timedatectl status` , you should see similar output:

```bash
Local time: Tue 2020-06-30 17:16:19 UTC
Universal time: Tue 2020-06-30 17:16:19 UTC
RTC time: Tue 2020-06-30 17:16:19
Time zone: Etc/UTC (UTC, +0000)
System clock synchronized: yes
systemd-timesyncd.service active: yes
RTC in local TZ: no
```

If **`System clock synchronized`** displays **`yes`**   you are good to go.

If not, you can either:

* [x] synchronize clock with NTP servers (allow **UDP** port **123** for both incoming and outgoing traffic) or
* [x] use the following script to sync with google.com:

Create `fixtime.sh` script and run it with `watch -n 60` command in a `screen`

```bash
echo sudo date -s '"$(wget -qSO- --max-redirect=0 google.com 2>&1 | grep Date: | cut -d' ' -f5-8)Z"' > fixtime.sh
chmod +x fixtime.sh
screen -S time
watch -n 60 ./fixtime.sh
```

Press `Ctrl+A+D` to leave the `screen`

## Node Requirements

{% hint style="info" %}
Recommended requirements are met when using DappNode preconfigured hardware or a liquid staking service.
{% endhint %}

### Beacon Chain Node Requirements

Minimum & Recommended specifications for running GBC clients:

### Prysm Client

**Prysm Minimum**

* Operating System: 64-bit Linux, Mac OS X 10.14+, Windows 64-bit
* Processor: Intel Core i5–760 or AMD FX-8100 or better
* Memory: 8GB RAM
* Storage: 128GB available space SSD
* Internet: Broadband connection

**Prysm Recommended**

* Processor: Intel Core i7–4770 or AMD FX-8310 or better
* Memory: 16GB RAM
* Storage: 256GB available space SSD
* Internet: Broadband connection

### Lighthouse Client

**Lighthouse Minimum**

* Dual-core CPU, 2015 or newer
* 8 GB RAM
* 128 GB solid state storage
* 10 Mb/s download, 5 Mb/s upload broadband connection

**Lighthouse Recommended**

* Quad-core AMD Ryzen, Intel Broadwell, ARMv8 or newer
* 16 GB RAM
* 256 GB solid state storage
* 100 Mb/s download, 20 Mb/s upload broadband connection

### Nimbus Client

**Nimbus Minimum**

* Dual-core CPU, 2015 or newer
* 4 GB RAM
* 128 GB solid state storage
* 10 Mb/s download, 5 Mb/s upload broadband connection

**Nimbus Recommended**

* Quad-core CPU
* 8 GB RAM
* 256 GB solid state storage
* 100 Mb/s download, 20 Mb/s upload broadband connection

****

### Gnosis Chain Execution Layer Node Requirements

It is optional to run your own Gnosis node. You can link GBC to an existing node through a JSON RPC endpoint, and this is the easiest method when you first setup your node. You will be encouraged to update your setup once the merge happens. If you have experience and would prefer to setup your own GC node now, here are the instructions.

GC Nodes can be run with you choice of 2 clients (OpenEthereum and Nethermind) and the following recommended minimum specs:

* OS: Ubuntu (Nethermind & OE), Windows & MacOs (Nethermind only)
* CPU: 2 cores
* RAM: 4GB
* Disk: 100gb SSD
* Git installed `git --version`

[-> Nethermind Node Setup](../clients/gnosis-chain-node-openethereum-and-nethermind/nethermind-node-setup.md)

[-> OpenEthereum Node Setup ](../clients/gnosis-chain-node-openethereum-and-nethermind/openethereum-node-setup.md)

## Ready to Get Started?

\-> [Get started with your Node Setup](get-started-node-setup/)
