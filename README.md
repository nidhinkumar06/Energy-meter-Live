<div align="center">
  <h1>Monitor Modbus Devices with InfluxDB</h1>
  <br>
  <div align="center">
    <img src="./assets/modbus-influxdata.webp" alt="aog" height="105">
    </div>
</div>

**ABOUT**
----------
Monitor the Energy meters with InfluxDB via Telegraf and visualize the metrics in Chronograf

## Setup Instructions
----------------------

## Installation

#### GO - Updating the Modbus Plugin
--------------------------------------

1. Download `GO` from the following [link](https://golang.org/doc/install)
2. Once the file is downloaded unzip it using the following command in ubuntu `tar -C /usr/local -xzf go1.15.6.linux-amd64.tar.gz`
3. Once extracted add the GO path in `.bashrc` and `.profile` file like below

```
#set GO in .bashrc file
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

4. Add the go path in `.profile` like below

```
export PATH=${PATH}:/usr/local/go/bin
```

Once done close the file and refresh the `.bashrc` and `.profile` using the command `source .bashrc` and `source .profile`

Now the installation of GO is completed in the local machine

#### Clone Telegraf Package
-----------------------------

1. Clone the Telegraf package using the command `go get github.com/influxdata/telegraf`
2. Once cloned navigated to the plugins directory like `cd go/src/github.com/influxdata/telegraf/plugins`
3. Once navigated to `plugins` directory navigate to `input` directory and then navigate to `modbus` directory
4. Once you have navigated to the modbus directory replace the modbus.go file with the one which you have downloaded
5. Navigate back to telegraf directory `go/src/github.com/influxdata/telegraf`
6. Now build the telegraf plugin using the command `make telegraf`
7. Note: We are not updating in the `all.go` file in input plugin since the modbus plugin is available in the all.go file
8. Once the build is completed run the telegraf service using the below command in the following path `go/src/github.com/influxdata/telegraf`

```
sudo ./telegraf --config /pathof/telegraf.conf  //add the telegraf.conf file path

sudo ./telegraf --config /home/nidhin/Destop/telegraf.config
```

Now the telegraf service starts which will collect the metrics from EnergyMeters via Modbus and dump it into InfluxDB

Now you can visualize the metrics in Chronograf like the below video

[<img src="https://i9.ytimg.com/vi/pr0A9vyT1nc/mq2.jpg?sqp=CLy40v8F&rs=AOn4CLBkPtH01QxMaIcBptk4H9Af5Y9aLA">](https://youtu.be/pr0A9vyT1nc)