<h1 align="center">  NATUCASH Blockchain Node</h1>

<p align="center">
  <a href="https://github.com/natucash/natunode/actions" target="_blank">
    <img alt="Checks status" src="https://badgen.net/github/checks/natucash/natunode?cache=600"  />
  </a>
  <a href="https://github.com/niobiocash/nbrcnode/releases" target="_blank">
    <img alt="Downloads" src="https://badgen.net/github/assets-dl/natucash/natunode?color=blue" />
  </a>

  <br/>



  <a href="https://t.me/natucash" target="_blank">
    <img alt="Telegram" src="https://badgen.net/badge/icon/natucash?icon=telegram&label=Telegram"/>
  </a>

</p>

> NATUCASH is Based on WAVES an open source [blockchain protocol](https://waves.tech/waves-protocol). <br/> 
You can use it to build your own decentralized applications. Waves provides full blockchain ecosystem including smart contracts language called RIDE.



##  Getting started

A quick introduction of the minimal setup you need to get a running node. 

*Prerequisites:*
- configuration file for a needed network `natu.conf`
- `nbrc-all*.jar` file from [releases](https://github.com/natucash/natunode/releases) 

Linux systems:
```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre
java -jar node/target/natu-all*.jar path/to/config/natu.conf
```

Mac systems (assuming already installed homebrew):
```bash
brew cask install adoptopenjdk/openjdk/adoptopenjdk8
java -jar node/target/natu-all*.jar path/to/config/natu.conf
```

Windows systems (assuming already installed OpenJDK 8):
```bash
java -jar node/target/natu-all*.jar path/to/config/natu.conf
```


## 👨‍💻 Development

The node can be built and installed wherever Java can run. 
To build and test this project, you will have to follow these steps:

<details><summary><b>Show instructions</b></summary>

*1. Setup the environment.*
- Install Java for your platform:

```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre                     # Ubuntu
# or
# brew cask install adoptopenjdk/openjdk/adoptopenjdk8 # Mac
```

- Install SBT (Scala Build Tool)

Please follow the SBT installation instructions depending on your platform ([Linux](https://www.scala-sbt.org/1.0/docs/Installing-sbt-on-Linux.html), [Mac](https://www.scala-sbt.org/1.0/docs/Installing-sbt-on-Mac.html), [Windows](https://www.scala-sbt.org/1.0/docs/Installing-sbt-on-Windows.html))

*2. Clone this repo*

```bash
git clone https://github.com/natucash/natunode.git
cd nbrcnode
```

*3. Compile and run tests*

```bash
sbt checkPR
```

*4. Run integration tests (optional)*

Create a Docker image before you run any test: 
```bash
sbt node-it/docker
```

- Run all tests. You can increase or decrease number of parallel running tests by changing `waves.it.max-parallel-suites`
system property:
```bash
sbt -Dwaves.it.max-parallel-suites=1 node-it/test
```

- Run one test:
```bash
sbt node-it/testOnly *.TestClassName
# or 
# bash node-it/testOnly full.package.TestClassName
```

*5. Build packages* 

```bash
sbt packageAll                   # Mainnet
sbt -Dnetwork=testnet packageAll # Testnet
```

`sbt packageAll` ‌produces only `deb` package along with a fat `jar`. 

*6. Install DEB package*

`deb` package is located in target folder. You can replace '*' with actual package name:

```bash
sudo dpkg -i node/target/*.deb
```


*7. Run an extension project locally during development (optional)*

```bash
sbt "extension-module/run /path/to/configuration"
```

*8. Configure IntelliJ IDEA (optional)*

The majority of contributors to this project use IntelliJ IDEA for development, if you want to use it as well please follow these steps:

1. Click `Add configuration` (or `Edit configurations...`).
2. Click `+` to add a new configuration, choose `Application`.
3. Specify:
   - Main class: `com.wavesplatform.Application`
   - Program arguments: `/path/to/configuration`
   - Use classpath of module: `extension-module`
4. Click `OK`.
5. Run this configuration.

</details>

## 🤝 Contributing

If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

For major changes, please open an issue first to discuss what you would like to change. Please make sure to update tests as appropriate.

Please follow the [code of conduct](./CODE_OF_CONDUCT.md) during communication with the each other. 

## ℹ️ Support (get help)


- [Telegram Dev Chat - NATUCASH ](https://t.me/natucash)




## 📝 Licence

The code in this project is licensed under [MIT license](./LICENSE)

