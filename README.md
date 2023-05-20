<a name="readme-top"></a>
<h2 align="center">Goshh-Server</h3>

<!-- LOGO -->
<br />
<div align="center">
  <a href="Placeholder">
    <img src="https://github.com/5ur/Goshh/blob/main/logos/server_logo.png" alt="Logo" width="35%" height="35%">
  </a>

<p align="center">
  A Go message and file sharing service
  <br />
  <a href="Placeholder"><strong>Wiki»</strong></a>
</div>


<!-- TOC -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#prerequisites">Prerequisites</a></li>
    <li><a href="#Installation">Installation</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#examples">Examples</a></li>
  </ol>
</details>

### Built With
[![Go][Go]][Go-url] [![Powershell][Powershell]][Powershell-url] [![Vim][Vim]][Vim-url] [![Exchange][StackExchange]][StackExchange-url] [![Overflow][StackOverflow]][StackOverflow-url] [![Windows][Windows]][Windows-url]

# Prerequisites
**Minimum version of go required is 1.16  **
## Windows
Start by installing Go:  
You can download and install Go from: https://go.dev/dl/

Or you and use a package manager:  
**Scoop**: https://scoop.sh/
```Powershell
irm get.scoop.sh | iex
scoop bucket add main
scoop install main/go
```
**Winget**
```Powershell
winget install -e --id GoLang.Go
```

## Linux
**apt**
```Shell
apt install golang -y
```

You can also manually install the bin (eg; apt ins installing an older version of go lesser than 1.16): https://go.dev/dl/  

```Shell
wget https://go.dev/dl/go1.20.4.linux-amd64.tar.gz
tar -C /usr/local -xzf go1.20.4.linux-amd64.tar.gz

```

Depending on your distro you might have one of these two files:  
`vim /etc/profile` or `/etc/bash.bashrc`  
You can add the the Go bins to path in one of those or both to make the binary available for all users:  
```Shell
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```
You can also just add the above to a specif user's bashrc or profile.  

# Installation
## Windows
1. Clone the repository:
   ```Powershell
   git clone https://github.com/5ur/Goshh-Server.git
   cd .\Goshh-Server\   
   ```
2. Download the external go packages
   ```Powershell
   # If need be (eg; you use a newer/older version of go, delete the go.mod file and create your own):
   go mod init Goshh-Server
   go get .
   go mod tidy
   ```
3. Build the binary
   ```Powershell
   go build .
   ```
4. Create your config file
  ```Powershell
  mv config.yaml.example config.yaml
  vim config.yaml
  ```
  Example config file:
  ```YAML
  # Gin debug mode:
  debugMode: true
  # Port for the engine:
  serverPort: 5150
  # Use default gin router (if false new is created):
  useDefault: true
  # Trusted proxy slice/array
  trustedProxies:
    # Local host only:
    - 127.0.0.1
    # Some RFC 1918 range:
    - 10.0.0.0/8
  # Time in which the slice of messages will be dumped
  cleanupInterval: "10s"
  # This achieves the same as adding all 1918 ranges in trustedProxies, just more convenient
  allowLocalNetworkAccess: true
  # You understand what this does with no context needed
  allowedFileTypes:
    - txt
    - md
    - jpg
  # You understand what this does with no context needed
  fileSavePath: "tmp/"
  # Time after which a stale file will be deleted (ie; not downloaded at all, not downloaded enough times to reach the allowedFileDownloadCount limit)
  staleFileTTL: "30s"
  # The amount of times a file is allowed to be downloaded (kept in check by the file struct values)
  allowedFileDownloadCount: 1 
  ```
5. That's it

## Linux
1. Clone the repository:
```Shell
git clone https://github.com/5ur/Goshh-Server.git
cd Goshh-Server/
```
2. Build in the same way
```Shell
# If need be (eg; missing go.mod or you have a different go version)
go mod init Gosh-Server
go mod tidy

# Finally:
go build .
```
3. Create your config file
```Shell
mv config.yaml.example config.yaml
vim config.yaml
```
Example config file:
```YAML
# Gin debug mode:
debugMode: true
# Port for the engine:
serverPort: 5150
# Use default gin router (if false new is created):
useDefault: true
# Trusted proxy slice/array
trustedProxies:
  # Local host only:
  - 127.0.0.1
  # Some RFC 1918 range:
  - 10.0.0.0/8
# Time in which the slice of messages will be dumped
cleanupInterval: "10s"
# This achieves the same as adding all 1918 ranges in trustedProxies, just more convenient
allowLocalNetworkAccess: true
# You understand what this does with no context needed
allowedFileTypes:
  - txt
  - md
  - jpg
# You understand what this does with no context needed
fileSavePath: "tmp/"
# Time after which a stale file will be deleted (ie; not downloaded at all, not downloaded enough times to reach the allowedFileDownloadCount limit)
staleFileTTL: "30s"
# The amount of times a file is allowed to be downloaded (kept in check by the file struct values)
allowedFileDownloadCount: 1 
```
4. That's it.

<!-- MARKDOWN LINKS & IMAGES -->
[product-screenshot]: logo/logo.png
[Go]: https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white
[Go-url]: https://go.dev/doc/

[Powershell]: https://img.shields.io/badge/powershell-5391FE?style=for-the-badge&logo=powershell&logoColor=white
[Powershell-url]: https://github.com/PowerShell/PowerShell

[Vim]: https://img.shields.io/badge/NeoVim-%2357A143.svg?&style=for-the-badge&logo=neovim&logoColor=white
[Vim-url]: https://github.com/AstroNvim/AstroNvim

[StackExchange]: https://img.shields.io/badge/StackExchange-%23ffffff.svg?&style=for-the-badge&logo=StackExchange&logoColor=white
[StackExchange-url]: https://stackexchange.com/

[StackOverflow]: https://img.shields.io/badge/Stack_Overflow-FE7A16?style=for-the-badge&logo=stack-overflow&logoColor=white
[StackOverflow-url]: https://stackoverflow.com/

[Windows]: https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white
[Windows-url]: https://www.microsoft.com/en-us/windows?r=1

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
