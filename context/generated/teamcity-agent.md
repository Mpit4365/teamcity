## teamcity-agent tags

Other tags

- [teamcity-minimal-agent](teamcity-minimal-agent.md)
- [teamcity-server](teamcity-server.md)

#### multi-architecture

When running an image with multi-architecture support, docker will automatically select an image variant which matches your OS and architecture.

- [latest](#latest)
- [2020.1.1](#202011)
- [latest-windowsservercore](#latest-windowsservercore)
- [2020.1.1-windowsservercore](#202011-windowsservercore)

#### linux

- 18.04-sudo
  - [2020.1.1-linux-sudo](#202011-linux-sudo)
- 18.04
  - [2020.1.1-linux](#202011-linux)

#### windows

- 1909
  - [2020.1.1-nanoserver-1909](#202011-nanoserver-1909)
  - [2020.1.1-windowsservercore-1909](#202011-windowsservercore-1909)
- 1903
  - [2020.1.1-nanoserver-1903](#202011-nanoserver-1903)
  - [2020.1.1-windowsservercore-1903](#202011-windowsservercore-1903)
- 1809
  - [2020.1.1-nanoserver-1809](#202011-nanoserver-1809)
  - [2020.1.1-windowsservercore-1809](#202011-windowsservercore-1809)
- 1803
  - [2020.1.1-nanoserver-1803](#202011-nanoserver-1803)
  - [2020.1.1-windowsservercore-1803](#202011-windowsservercore-1803)


### latest

Supported platforms: linux 18.04, windows 1809, windows 1903

#### Content

- [2020.1.1-linux](#202011-linux)
- [2020.1.1-nanoserver-1809](#202011-nanoserver-1809)
- [2020.1.1-nanoserver-1903](#202011-nanoserver-1903)

### 2020.1.1

Supported platforms: linux 18.04, windows 1809, windows 1903

#### Content

- [2020.1.1-linux](#202011-linux)
- [2020.1.1-nanoserver-1809](#202011-nanoserver-1809)
- [2020.1.1-nanoserver-1903](#202011-nanoserver-1903)

### latest-windowsservercore

Supported platforms: windows 1809, windows 1903

#### Content

- [2020.1.1-windowsservercore-1809](#202011-windowsservercore-1809)
- [2020.1.1-windowsservercore-1903](#202011-windowsservercore-1903)

### 2020.1.1-windowsservercore

Supported platforms: windows 1809, windows 1903

#### Content

- [2020.1.1-windowsservercore-1809](#202011-windowsservercore-1809)
- [2020.1.1-windowsservercore-1903](#202011-windowsservercore-1903)


### 2020.1.1-linux

[Dockerfile](linux/Agent/Ubuntu/18.04/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Installed components:

- Git
- Mercurial
- [.NET SDK x64 v.3.1.300](https://dotnetcli.blob.core.windows.net/dotnet/Sdk/3.1.300/dotnet-sdk-3.1.300-linux-x64.tar.gz)

Container platform: linux

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-linux
```

Docker build commands:

```
docker build -f "context/generated/linux/MinimalAgent/Ubuntu/18.04/Dockerfile" -t teamcity-minimal-agent:2020.1.1-linux "context"
docker build -f "context/generated/linux/Agent/Ubuntu/18.04/Dockerfile" -t teamcity-agent:2020.1.1-linux "context"
```

Base images:

```
docker pull ubuntu:18.04
```

_The required free space to generate image(s) is about **2 GB**._
### 2020.1.1-linux-sudo

[Dockerfile](linux/Agent/Ubuntu/18.04-sudo/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.
This image allows to do *__sudo__* without a password for the *__builduser__* user.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Container platform: linux

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-linux-sudo
```

Docker build commands:

```
docker build -f "context/generated/linux/MinimalAgent/Ubuntu/18.04/Dockerfile" -t teamcity-minimal-agent:2020.1.1-linux "context"
docker build -f "context/generated/linux/Agent/Ubuntu/18.04/Dockerfile" -t teamcity-agent:2020.1.1-linux "context"
docker build -f "context/generated/linux/Agent/Ubuntu/18.04-sudo/Dockerfile" -t teamcity-agent:2020.1.1-linux-sudo "context"
```

Base images:

```
docker pull ubuntu:18.04
```

_The required free space to generate image(s) is about **3 GB**._
### 2020.1.1-nanoserver-1809

[Dockerfile](windows/Agent/nanoserver/1809/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Installed components:

- [.NET SDK x64 v.3.1.300](https://dotnetcli.blob.core.windows.net/dotnet/Sdk/3.1.300/dotnet-sdk-3.1.300-win-x64.zip)
- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)

Container platform: windows

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-nanoserver-1809
```

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1809/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1809 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1809/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1809 "context"
docker build -f "context/generated/windows/Agent/nanoserver/1809/Dockerfile" -t teamcity-agent:2020.1.1-nanoserver-1809 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1809
docker pull mcr.microsoft.com/powershell:nanoserver-1809
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019
```

_The required free space to generate image(s) is about **25 GB**._
### 2020.1.1-nanoserver-1903

[Dockerfile](windows/Agent/nanoserver/1903/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Installed components:

- [.NET SDK x64 v.3.1.300](https://dotnetcli.blob.core.windows.net/dotnet/Sdk/3.1.300/dotnet-sdk-3.1.300-win-x64.zip)
- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)

Container platform: windows

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-nanoserver-1903
```

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1903/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1903 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1903/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1903 "context"
docker build -f "context/generated/windows/Agent/nanoserver/1903/Dockerfile" -t teamcity-agent:2020.1.1-nanoserver-1903 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1903
docker pull mcr.microsoft.com/powershell:nanoserver-1903
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-1903
```

_The required free space to generate image(s) is about **25 GB**._
### 2020.1.1-windowsservercore-1809

[Dockerfile](windows/Agent/windowsservercore/1809/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Installed components:

- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)
- [JDK <img align="center" height="18" src="/logo/corretto.png"> Amazon Corretto x64 v.8.252.09.2](https://corretto.aws/downloads/resources/8.252.09.2/amazon-corretto-8.252.09.2-windows-x64-jdk.zip)
- [Git x64 v.2.19.1](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/MinGit-2.19.1-64-bit.zip)
- [Mercurial x64 v.4.7.2](https://bitbucket.org/tortoisehg/files/downloads/mercurial-4.7.2-x64.msi)

Container platform: windows

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-windowsservercore-1809
```

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1809/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1809 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1809/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1809 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1809
docker pull mcr.microsoft.com/powershell:nanoserver-1809
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019
```

_The required free space to generate image(s) is about **24 GB**._
### 2020.1.1-windowsservercore-1903

[Dockerfile](windows/Agent/windowsservercore/1903/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.

The docker image is available on:

- [https://hub.docker.com/r/jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)

Installed components:

- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)
- [JDK <img align="center" height="18" src="/logo/corretto.png"> Amazon Corretto x64 v.8.252.09.2](https://corretto.aws/downloads/resources/8.252.09.2/amazon-corretto-8.252.09.2-windows-x64-jdk.zip)
- [Git x64 v.2.19.1](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/MinGit-2.19.1-64-bit.zip)
- [Mercurial x64 v.4.7.2](https://bitbucket.org/tortoisehg/files/downloads/mercurial-4.7.2-x64.msi)

Container platform: windows

Docker pull command:

```
docker pull jetbrains//teamcity-agent:2020.1.1-windowsservercore-1903
```

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1903/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1903 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1903/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1903 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1903
docker pull mcr.microsoft.com/powershell:nanoserver-1903
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-1903
```

_The required free space to generate image(s) is about **24 GB**._
### 2020.1.1-nanoserver-1803

[Dockerfile](windows/Agent/nanoserver/1803/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.
The docker image is not available and may be created manually.

Installed components:

- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)
- [.NET SDK x64 v.3.1.300](https://dotnetcli.blob.core.windows.net/dotnet/Sdk/3.1.300/dotnet-sdk-3.1.300-win-x64.zip)

Container platform: windows

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1803/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1803 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1803/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1803 "context"
docker build -f "context/generated/windows/Agent/nanoserver/1803/Dockerfile" -t teamcity-agent:2020.1.1-nanoserver-1803 "context"
```

Base images:

```
docker pull mcr.microsoft.com/powershell:nanoserver-1803
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-1803
```

_The required free space to generate image(s) is about **24 GB**._
### 2020.1.1-nanoserver-1909

[Dockerfile](windows/Agent/nanoserver/1909/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.
The docker image is not available and may be created manually.

Installed components:

- [.NET SDK x64 v.3.1.300](https://dotnetcli.blob.core.windows.net/dotnet/Sdk/3.1.300/dotnet-sdk-3.1.300-win-x64.zip)
- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)

Container platform: windows

Docker build commands:

```
docker build -f "context/generated/windows/Agent/nanoserver/1909/Dockerfile" -t teamcity-agent:2020.1.1-nanoserver-1909 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1909
docker pull 2020.1.1-teamcity-agent:windowsservercore-1909
docker pull mcr.microsoft.com/powershell:nanoserver-1909
```

_The required free space to generate image(s) is about **3 GB**._
### 2020.1.1-windowsservercore-1803

[Dockerfile](windows/Agent/windowsservercore/1803/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.
The docker image is not available and may be created manually.

Installed components:

- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)
- [JDK <img align="center" height="18" src="/logo/corretto.png"> Amazon Corretto x64 v.8.252.09.2](https://corretto.aws/downloads/resources/8.252.09.2/amazon-corretto-8.252.09.2-windows-x64-jdk.zip)
- [Git x64 v.2.19.1](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/MinGit-2.19.1-64-bit.zip)
- [Mercurial x64 v.4.7.2](https://bitbucket.org/tortoisehg/files/downloads/mercurial-4.7.2-x64.msi)

Container platform: windows

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1803/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1803 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1803/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1803 "context"
```

Base images:

```
docker pull mcr.microsoft.com/powershell:nanoserver-1803
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-1803
```

_The required free space to generate image(s) is about **23 GB**._
### 2020.1.1-windowsservercore-1909

[Dockerfile](windows/Agent/windowsservercore/1909/Dockerfile)

This is an official [JetBrains TeamCity](https://www.jetbrains.com/teamcity/) build agent image.
The docker image is not available and may be created manually.

Installed components:

- [PowerShell](https://github.com/PowerShell/PowerShell#get-powershell)
- [JDK <img align="center" height="18" src="/logo/corretto.png"> Amazon Corretto x64 v.8.252.09.2](https://corretto.aws/downloads/resources/8.252.09.2/amazon-corretto-8.252.09.2-windows-x64-jdk.zip)
- [Git x64 v.2.19.1](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/MinGit-2.19.1-64-bit.zip)
- [Mercurial x64 v.4.7.2](https://bitbucket.org/tortoisehg/files/downloads/mercurial-4.7.2-x64.msi)

Container platform: windows

Docker build commands:

```
docker build -f "context/generated/windows/MinimalAgent/nanoserver/1909/Dockerfile" -t teamcity-minimal-agent:2020.1.1-nanoserver-1909 "context"
docker build -f "context/generated/windows/Agent/windowsservercore/1909/Dockerfile" -t teamcity-agent:2020.1.1-windowsservercore-1909 "context"
```

Base images:

```
docker pull mcr.microsoft.com/windows/nanoserver:1909
docker pull mcr.microsoft.com/powershell:nanoserver-1909
docker pull mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-1909
```

_The required free space to generate image(s) is about **24 GB**._
