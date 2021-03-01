# How to Programming AVR on Ubuntu Linux

## Install Code::Blocks
```make
sudo apt-get update
sudo apt-get install codeblocks
```

## Install Avrdude
```make
#sudo add-apt-repository ppa:pmjdebruijn/avrdude-release
sudo apt-get update
sudo apt-get install libc6-dev-i386
sudo apt-get install binutils-avr gcc-avr avr-libc avrdude libc6-dev-i386
```

## Check ISP Programmer
```make
dmesg
```

## Start codeblocks
```make
codeblocks
```

## Prepare to run AVR Project
```make
In Console -
cd ~
mkdir -p proj/avr

In codeblocks -
File -> New -> Project -> AVR Project

Next

Project title: blink
Folder to create project in: /home/oem/proj/avr
Project filename: blink.cbp
Resulting filename: /home/oem/proj/avr/blink/blink.cbp
Next

Uncheck: Create "Debug" configuration
Next

Please choose a processor for this project...: atmega328p
Uncheck: Create Fuse, Lock, Signature files (.fuse .lock .sig)
Finish
```

## Write Code
```make
main.c

#include <avr/io.h>

#define F_CPU       16000000L
#include <util/delay.h>

int main(void)
{

    // Insert code
    DDRB = 0x20;

    while(1)
    {
        PORTB = 0x00;
        _delay_ms(500);
        PORTB = 0x20;
        _delay_ms(500);
    }

    return 0;
}
```
