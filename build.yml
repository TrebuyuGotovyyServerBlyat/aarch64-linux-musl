#!/usr/bin/env bash

sudo git clone https://github.com/pmmp/musl-cross-make
sudo mv musl-cross-make/* .

TARGET="aarch64-linux-musl"
OUTPUT="/opt/cross/"

sudo mkdir -p $OUTPUT

echo """
TARGET = $TARGET
OUTPUT = $OUTPUT
COMMON_CONFIG += CFLAGS=\"-g0 -Os\" CXXFLAGS=\"-g0 -Os\" LDFLAGS=\"-s\"
""" >> config.mak

sudo make &>> ./process.log
sudo make install &>> ./process.log

sudo cp ./process.log $OUTPUT
sudo tar -czvf $TARGET.tar.gz -C $OUTPUT .
