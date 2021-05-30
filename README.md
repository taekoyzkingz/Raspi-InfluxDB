# How to Install InfluxDB in Raspberry PI

- First we add Influx repositories to apt
```bash
$ wget -qO- https://repos.influxdata.com/influxdb.key | sudo apt-key add -
$ source /etc/os-release
$ echo "deb https://repos.influxdata.com/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
```
- Update apt with the new repos, & install
```bash
$ sudo apt update && sudo apt install -y influxdb
```
- Then start the influxdb service and set it to run at boot
```bash
$ sudo systemctl unmask influxdb.service
$ sudo systemctl start influxdb
$ sudo systemctl enable influxdb.service
```
