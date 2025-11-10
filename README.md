# JICA Scripts

Setup scripts and practices for JICA seminar by Taro Matsuzawa (@smellman).

## requirements

Install [niroku](https://github.com/unvt/niroku/) first.

## System setup (Raspberry Pi 4)

```bash
$ git clone https://github.com/smellman/jica_scripts.git
$ cd jica_scripts/system
$ sudo make
```

## Old setup (2024 version)

```bash
$ sudo apt install -y git make
$ git clone https://github.com/smellman/jica_scripts.git
$ cd jica_scripts
$ git checkout -b 2024 origin/2024
$ cd system
$ sudo make
```