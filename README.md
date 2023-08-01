# POC - Custom Package Debian Repository


## About

This POC is a continuation from the [Packaging a .NET Core Service for Ubuntu](https://github.com/UlisesGascon/poc-packaging-dot-net-core-service-for-ubuntu). In this case, I followed the guide [Creating a private Debian package repository by Jesús Corrius](https://medium.com/bluekiri/packaging-a-net-core-service-for-ubuntu-4f8e9202d1e5)

## Try it out


1. Add this public key to your trusted keys
```bash
wget -qO - https://raw.githubusercontent.com/UlisesGascon/poc-custom-package-debian-repository/main/PUBLIC.KEY | sudo apt-key add -
```

2. Add this repository as source list
```bash
echo "deb https://raw.githubusercontent.com/UlisesGascon/poc-custom-package-debian-repository/main/ bionic main" | sudo tee /etc/apt/sources.list.d/ulisesgascon.list
```

3. Update sources list

```bash
sudo apt-get update
```

4. Install `demoapi` package

```bash
sudo apt-get install demoapi
```

5. Check the service status

```bash
systemctl -l status demoapi.service
```