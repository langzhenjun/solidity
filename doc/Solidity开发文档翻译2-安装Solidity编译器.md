# Solidity开发文档翻译（二）：安装Solidity编译器

## 版本号
Solidity的版本号使用Semantic Versioning管理方式，有正式版和开发版。开发版包含一些未经验证的修改，可能还存在问题，虽然尽了最大的努力，但并不能保证可以正常高效的运行。我们推荐使用最新的正式版。在下文中，我们将会使用最新的正式版。

## Remix
我们推荐使用Remix来编写小合约并快速学习Solidity。

访问Remix在线服务(https://remix.ethereum.org/)，你并不需要安装任何东西。如果你想在离线状态下使用它，请转到（https://github.com/ethereum/browser-solidity/tree/gh-pages），然后在页面上下载.ZIP文件。

安装命令行solidity编译器软件，将可以查看其他更多的使用选项。如果你想要开发一个大型的合约或者你想要更多的编译选项，请选择使用一个命令行编译器。

## npm和node.js
使用npm来便捷地安装solcjs，它是一个solidity编译器。solcjs程序并不能提供本文使用到的所有特性功能，我们假定你使用全功能的编译器solc来学习这篇文章(https://solidity.readthedocs.io/en/v0.4.21/using-the-compiler.html#commandline-compiler)。因此，如果你正在使用从npm上安装的solcjs，请转到（https://github.com/ethereum/solc-js）。

>说明：solc-js项目是使用Emscripten从C++ solc项目派生而来的。solc-js可以在Javascript项目中直接使用（Remix就是如此）。请从solc-js的仓库中获取它的使用指令。
```bash
npm install -g solc
```
>说明：命令名称是solcjs，它和solc等其他工具并不兼容，它们并不能一起使用。

## Docker
根据最新的docker，我们提供了一个solidity编译镜像。```stable```仓库包含solidity的稳定版，```nightly```包含不稳定的开发分支。
```bash
docker run ethereum/solc:stable solc --version
```

## 二进制包
Solidity的二进制包部署在solidity/releases(https://github.com/ethereum/solidity/releases)。
我们为Ubuntu也提供了包源，最新稳定版：
```bash
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install solc
```
如果你想使用开发板：
```bash
sudo add-apt-repository ppa:ethereum/ethereum
sudo add-apt-repository ppa:ethereum/ethereum-dev
sudo apt-get update
sudo apt-get install solc
```
快照版本：
```bash
sudo snap install solc
```
测试开发版：
```bash
sudo snap install solc --edge
```
Arch Linux：
```bash
pacman -S solidity
```
Homebrew：
```bash
brew update
brew upgrade
brew tap ethereum/ethereum
brew install solidity
brew linkapps solidity
```
Gentoo:
```bash
emerge dev-lang/solidity
```

## 源码安装
### 克隆仓库
执行一下命令来安克隆仓库：
```bash
git clone --recursive https://github.com/ethereum/solidity.git
cd solidity
```

如果你想要帮助开发Solidity，你应该fork它，然后把你自己的fork地址添加到remote中：
```bash
cd solidity
git remote add personal git@github.com:[username]/solidity.git
```

Solidity有一些git的子模块。请确保它们已经被加载：
```bash
git submodule update --init --recursive
```

### macOS
在macOS中使用，请确保已经安装最新版本的XCode，他包含Clang C++ 编译器，集成开发环境，和其他一些用来构建C++应用程序的苹果开发工具。如果你准备第一次安装XCode，或者已经安装了最新版，你将会在使用命令行钱同意一个证书：
```bash
sudo xcodebuild -license accept
```
macOS上的构建需要你安装Homebrew这个包管理软件来安装外部的依赖。

### Windows
（暂时省略）

### 外部依赖
（暂时省略）


### 命令行构建
请确保在构建前已经安装外部依赖。
Solidity项目使用CMake来配置构建。构建Solidity在Linux、macOS和其他类Unix系统上几乎是一致的：
```bash
mkdir build
cd build
cmake .. && make
```
或者更简单地：
```bash
#note: this will install binaries solc and soltest at usr/local/bin
./scripts/build.sh
```
甚至在Windows上：
```bash
mkdir build
cd build
cmake -G "Visual Studio 14 2015 Win64" ..
```

## CMake options

## The version string in detail

## Important information about versioning




>原文地址(https://solidity.readthedocs.io/en/v0.4.21/introduction-to-smart-contracts.html)

>反馈邮箱(mailto:langzhenjun@gmail.com)

>github(http://github.com/langzhenjun/solidity.git)