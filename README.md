<h1 align="center">🔷 Waves Pizza Node</h1>

> Waves Pizza is an open source [blockchain protocol]. <br/>
> You can use it to build your own decentralized applications. Waves Pizza provides full blockchain ecosystem including smart contracts language called RIDE.

## ✨ Demo

Waves Pizza node is a host connected to the blockchain network with the following functions:

## 🚀️ Getting started

A quick introduction of the minimal setup you need to get a running node.

_Prerequisites:_

Linux systems:

```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre
java -jar node/target/waves-all*.jar path/to/config/waves-{network}.conf
```

Mac systems (assuming already installed homebrew):

```bash
brew cask install adoptopenjdk/openjdk/adoptopenjdk8
java -jar node/target/waves-all*.jar path/to/config/waves-{network}.conf
```

Windows systems (assuming already installed OpenJDK 8):

```bash
java -jar node/target/waves-all*.jar path/to/config/waves-{network}.conf
```

The node can be built and installed wherever Java can run.
To build and test this project, you will have to follow these steps:

<details><summary><b>Show instructions</b></summary>

_1. Setup the environment._

- Install Java for your platform:

```bash
sudo apt-get update
sudo apt-get install openjdk-8-jre                     # Ubuntu
# or
# brew cask install adoptopenjdk/openjdk/adoptopenjdk8 # Mac
```

- Install SBT (Scala Build Tool)

_2. Clone this repo_

```bash
cd Waves Pizza
```

_3. Compile and run tests_

```bash
sbt checkPR
```

_4. Run integration tests (optional)_

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

_5. Build packages_

```bash
sbt packageAll                   # Mainnet
sbt -Dnetwork=testnet packageAll # Testnet
```

`sbt packageAll` ‌produces only `deb` package along with a fat `jar`.

_6. Install DEB package_

`deb` package is located in target folder. You can replace '\*' with actual package name:

```bash
sudo dpkg -i node/target/*.deb
```

_7. Run an extension project locally during development (optional)_

```bash
sbt "extension-module/run /path/to/configuration"
```

_8. Configure IntelliJ IDEA (optional)_

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

## 📝 Licence

The code in this project is licensed under [MIT license](./LICENSE)
