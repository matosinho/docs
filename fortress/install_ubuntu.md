# Binary Installation on Ubuntu

Fortress binaries are provided for Ubuntu Bionic and Focal. All of the Fortress
binaries are hosted in the osrfoundation repository. To install all of them,
the metapackage `ignition-fortress` can be installed.

Up to Fortress's release date, the binaries should be considered unstable.

First install some necessary tools:

```bash
sudo apt-get update
sudo apt-get install lsb-release wget gnupg
```

Then install Ignition Fortress:


```bash
sudo wget https://packages.osrfoundation.org/gazebo.gpg -O /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-prerelease $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-prerelease.list > /dev/null
sudo apt-get update
sudo apt-get install ignition-fortress
```

All libraries should be ready to use and the `ign gazebo` app ready to be executed.

Head back to the [Getting started](/docs/all/getstarted)
page to start using Ignition!

## Uninstalling binary install

If you need to uninstall Ignition or switch to a source-based install once you
have already installed the library from binaries, run the following command:

```bash
sudo apt remove ignition-fortress && sudo apt autoremove
```

## Troubleshooting

See [Troubleshooting](troubleshooting)
