
# Read SHT31

A simple command line tool for Raspberry-Pi to read a SHT31 sensor over the I2C bus.

## Usage

There are a number of arguments you can use:

```
Usage: read_sht31 [arguments]
 -h|--help   Display this help.
 -s          Get the sensor status.
 -t1 -t0     Enable/disable heater.
 -a0 -a1     Select the chip address. 0 is the default.
 -b0 -b1     Select the bus. 1 is the default.
 -d          Show debugging messages.
```

If you call the command, you will get JSON output:

```
hbarta@bennu:~ $ read_sht31
{ "t":1772945400,"temp":69.8, "humid": 45.7, "device":"SHT31" }hbarta@bennu:~ $ 
hbarta@bennu:~ $ 
```

## Check for SHT31

```text
hbarta@bennu:~ $ i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
40: -- -- -- -- 44 -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- --                         
hbarta@bennu:~ $ 
```

## Requirements

```
sudo apt install gcc cmake i2c-tools
sudo raspi-config nonint do_i2c 0
```

## Build

```
mkdir -p build && cd build
cmake ..
make
sudo make install
```

## License (GPL v3)

Copyright (c) 2020 by Lucky Resistor.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

