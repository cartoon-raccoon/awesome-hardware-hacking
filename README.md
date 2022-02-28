# awesome-hardware-hacking

## A humble list of hardware hacking tools and resources curated by yours truly

---

_Are you new to the wonderful world of hardware hacking? Swamped with resources and different tools and don't know where to turn?_

Have I got the solution for you!

This compendium was born out of my initial confusion, and overwhelming from all the various types of hardware hacking tools, resources, and types that are out there. I intend for this to track which tools are available for each aspect of hardware tinkering, as well as various resources that may come in handy.

Several sections are still a work in progress, and I hope to add items to them as I branch out into those fields.

Happy hacking!

---

## Table of Contents

1. [**Serial Protocols**](#1-serial-protocols)
2. [**USB**](#2-usb)
3. [**RF**](#3-rf)
4. [**Automotive**](#4-automotive)
5. [**Glitching and Fault Injection**](#5-glitching-and-fault-injection)
6. [**Reverse Engineering and Emulation**](#6-reverse-engineering-and-emulation)
7. [**Programmers and Sockets**](#7-programmers-and-sockets)
8. [**Soldering and Rework**](#8-soldering-and-rework)
9. [**Development**](#9-development)
10. [**Other Resources**](#10-other-resources)

---

## 1. Serial Protocols

The one thing every hardware enthusiast must have in their toolkit is a way of communicating via serial protocols. The most common are UART, SPI and I2C. Luckily, people have realized that an interface board for each protocol is a pain, and have created multitool boards that speak these 3 protocols, plus an additional protocol called JTAG, which isn't technically serial communication but is so common it's included anyway. These boards don't natively speak the protocol; instead they are driven by software tools that help them speak the protocol.

- What is [UART](https://www.arrow.com/en/research-and-events/articles/what-is-uart-protocol-uart-communication-explained)/[SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface)/[I2C](https://en.wikipedia.org/wiki/I%C2%B2C)/[JTAG](https://en.wikipedia.org/wiki/JTAG)?

### Hardware

_Multitools_

- [Tigard](https://github.com/tigard-tools/tigard) (All 4)
- [GreatFET One](https://greatscottgadgets.com/greatfet/one/) (All 4 + USB)
- [HydraBus](https://hydrabus.com/?v=0f177369a3b7) (All 4 and [more](https://github.com/hydrabus/hydrafw/wiki/HydraFW-console-commands)!)
- [Shikra](https://int3.cc/products/the-shikra) (All 4)
- [Attify Badge](https://www.attify-store.com/products/attify-badge-uart-jtag-spi-i2c) (All 4)
- [Bus Pirate](http://dangerousprototypes.com/docs/Bus_Pirate) (All 4, outdated, use something else)
- Generic FT2232 Serial-USB breakout board ([Micro-USB](https://www.sparkfun.com/products/12731))
_Other Tools_
- Arduino [Uno](https://www.arduino.cc/en/pmwiki.php?n=Main/arduinoBoardUno)/[Nano](https://www.arduino.cc/en/pmwiki.php?n=Main/ArduinoBoardNano) (JTAG enumeration, UART)
- [Seeeduino Nano](https://www.seeedstudio.com/Seeeduino-Nano-p-4111.html) (see above)
- [JTAGulator](http://www.grandideastudio.com/jtagulator/) (JTAG/UART Enumeration)
- [Segger J-Link Edu](https://www.adafruit.com/product/1369) (JTAG debugger)

### Software

- [OpenOCD](https://openocd.org/) (JTAG/SWD debugging)
- [JTAGenum](https://github.com/cyphunk/JTAGenum) (JTAG enumeration)
  - [JTAGulator vs. JTAGenum](https://www.praetorian.com/blog/jtagulator-vs-jtagenum-tools-for-identifying-jtag-pins-in-iot-devices/)
- [UrJTAG](http://urjtag.org/) (low-level JTAG interface)
- [picocom](https://github.com/npat-efault/picocom)/[minicom](https://wiki.emacinc.com/wiki/Getting_Started_With_Minicom)/[screen](https://www.gnu.org/software/screen/)/[PuTTY](https://www.putty.org/) (UART interface)
  - _Tip: Stick to picocom, PuTTY for Windows. Minicom and Screen are ancient._
- [flashrom](https://www.flashrom.org/Flashrom) (SPI flashing/reading)
- [pyftdi](https://eblot.github.io/pyftdi/)/[spiflash](https://github.com/eblot/pyspiflash) (programmatic SPI/I2C via FTDI)
- [libmpsse](https://github.com/devttys0/libmpsse) (programmatic SPI)

---

## 2. USB

Even though USB is technically a serial communication/data transfer protocol, it is a lot more complex than UART/SPI, involving device descriptors, polling, and differential signalling, and thus is usually treated differently than the other serial protocols. Fewer tools exist for USB hacking, but it is an equally rewarding field.

### Hardware

- [PhyWhisperer](https://github.com/newaetech/phywhispererusb) (sniffing/triggering)
- [GreatFET One](https://greatscottgadgets.com/greatfet/one/) (USB interface)
- [LUNA](https://greatscottgadgets.com/luna/) (protocol sniffer/analyzer/MitM)
- [FaceDancer 21](https://int3.cc/products/facedancer21) (supplanted by GreatFET)

### Software

- [FaceDancer](https://github.com/greatscottgadgets/Facedancer) (USB device emulation)
- [PhyWhisperer](https://phywhispererusb.readthedocs.io/en/latest/) (Python library)

---

## 3. RF

RF hacking is usually concerned with the Internet of Things (IoT). Since so many IoT devices communicate via wireless technology, there ought to be a way to compromise them through hacking their communications, right?

Of course, you don't have to take it that far. Why not just try hijacking the connection with your wireless USB mouse instead?

### Hardware

- [HackRF One](https://greatscottgadgets.com/hackrf/one/) (General RF, TX/RX, 1-6Ghz)
- [YARD Stick One](https://greatscottgadgets.com/yardstickone/) (General RF, TX/RX, <1Ghz)
- [Ubertooth One](https://greatscottgadgets.com/ubertoothone/) (Bluetooth)
- [WiFi Pineapple](https://shop.hak5.org/products/wifi-pineapple) (Wifi hacking)
- [NooElec Ham It Up](https://www.nooelec.com/store/ham-it-up-plus.html) (HF Upconverter)
- Any 2.4GHz & 5GHz Wi-Fi adapter with promiscuous/monitor mode

### Software

- [Wireshark](https://www.wireshark.org/) (Packet analyser)
- [GNU Radio](https://www.gnuradio.org/) (SDR toolkit)
- [Aircrack-ng](https://www.aircrack-ng.org/) (Wifi attack toolsuite)

---

## 4. Automotive

Cars are hackable too! Each component is wired up to form a Controller Area Network (CAN), which all components communicate on. From the ECU to the stereo system, everything communicates via the CAN bus. You could always find a way in and inject some malicious traffic, couldn't you?

### Hardware

- [Microchip CAN Analyzer](https://www.microchip.com/en-us/development-tool/apgdt002)
- [USB2CAN](https://www.8devices.com/products/usb2can_korlan) (CAN Bus sniffer)

### Software

- [Wireshark](https://www.wireshark.org/) (CAN packet analyser)

---

## 5. Glitching and Fault Injection

This is for the real hardware tinkerers. Screw software folks and their binary exploitation and instruction sets, let's just hit everything with fault injection or SCA. Here, you can use differential power analysis (DPA) to break AES encryption, or use fault injection to glitch a chip into bypassing the login prompt straight into a root shell.

### Hardware

- [ChipWhisperer](https://github.com/newaetech/chipwhisperer) (Glitching, SCA, DPA)
- [Homemade EMFI Tool](https://hackaday.com/2022/01/29/blast-chips-with-this-bbq-lighter-fault-injection-tool/)

### Software

- [ChipWhisperer](https://chipwhisperer.readthedocs.io/en/latest/) (ipynb)
- [Hashcat](https://hashcat.net/hashcat/) (bruteforce password cracker)
- [John the Ripper](https://www.openwall.com/john/) (see above)

---

## 6. Reverse Engineering and Emulation

How can you tell what black magic the board you're targeting is up to? Every hardware enthusiast needs some analysis tools to see what's going on under the hood. Oscilloscopes can tell you about the power draw on various pins, while logic analyzers can help you decode a mystery protocol some data lines are communicating on. The trusty multimeter can help you find GND, or if a mysterious desoldered pad is in fact a JTAG header.

On the software side, you've found a mysterious binary on the target system. How are you gonna run/debug it? QEMU and various kernel builders can help you craft the perfect emulation environment, complete with GDB and debugging symbols, to help you figure out what that weird program is doing.

### Hardware

_Oscilloscopes_

_Tip: Get an oscilloscope with good memory depth. The ones listed here aren't great in that regard, but they have great value._

- [Hantek DSO2000-series Oscilloscopes](http://www.hantek.com/products/detail/17182) (Great value for money)
- [Hantek DSO4004-series Oscilloscopes](http://www.hantek.com/products/detail/12167) (Good starter for those with bigger budgets, comes with AWG)
- [FNIRSI 1014D Oscilloscope](https://www.aliexpress.com/item/1005002340647364.html) (Good entry level scope)
- [Rigol DS1000Z-series Oscilloscopes](https://int.rigol.com/products/detail/DS1000Z) (Standard entry-level scopes also great value)
- [Picoscope 2000-series Oscilloscopes](https://www.picotech.com/oscilloscope/2000/picoscope-2000-overview) (USB scope)
- [ChipWhisperer](https://github.com/newaetech/chipwhisperer)
- [Hantek 6022BE](http://www.hantek.com/products/detail/31) (Not great, but it's cheap)
- Anything by Keysight/Tektronix is excellent. Only problem is they cost as much as a mid-tier sedan.
  - The [Keysight DSO1204G](https://www.keysight.com/sg/en/support/DSOX1204G/oscilloscope-70-100-200-mhz-4-analog-channels-waveform-generator.html) is pretty good value, however, and is a good upgrade from a Hantek.
_Logic Analyzers_
- [Saleae Logic Pro Logic Analyzers](https://www.saleae.com/) (8-16ch, 25-100MHz/100-500MS/s)
- [DSLogic Plus Logic Analyzer](https://www.dreamsourcelab.com/shop/logic-analyzer/dslogic-plus/) (16ch, up to 400MHz, best value)
- [BitMagic Basic Logic Analyzer](https://1bitsquared.com/products/bitmagic-basic) (8ch 24MHz)
- [Generic USB Saleae Logic 8 Clone](https://www.aliexpress.com/item/1005003812410259.html) (8ch 24MHz)
_Multimeters_
- [Mastech 8268](https://www.amazon.com/Mastech-MS8268-Digital-Manual-Multimeter/dp/B000JQ4O2U)
- [UNI-T UT61E+ True RMS](https://www.uni-trend.com/meters/html/product/General_Meters/Digital_Multimeters/UT61%20161%20Series/UT61E+.html)
- [Klein Tools MM600](https://www.amazon.com/dp/B018CLOSTC?tag=healthyhandyman-20&linkCode=osi&th=1&psc=1)
- [EEVblog BM235](https://www.eevblog.com/product/bm235/)
- [Brymen BM869S](https://brymenmeter.com/brymen-bm869s-multimeter.html)
- [Fluke 115](https://www.fluke.com/en-us/product/electrical-testing/digital-multimeters/fluke-115)
- [Fluke 87V](https://www.fluke.com/en-us/product/electrical-testing/digital-multimeters/fluke-87v)
    - _Tip: avoid Flukes. They're great, but they're priced so high because they're designed for professional electricians and government/corporate applications, where trust and a long chain of auditing is required. You can get a multimeter with an almost equal feature set and build quality as a Fluke for a lot cheaper._
_Microscopes_
- [Unbranded 600X Digital Microscope](https://www.aliexpress.com/item/32846603691.html)
- [Celestron Digital Microscope](https://www.amazon.sg/Celestron-MicroDirect-Handheld-Microscope-44316/dp/B01MF5KMBL/)
- [ANNLOV 1-1200X 7in Digital Microscope](https://www.amazon.com/Microscope-ANNLOV-Maginfication-Electronic-Adjustable/dp/B087311SKR/)
- [Andonstar](https://www.aliexpress.com/store/700244) is a fairly reputable brand, available on AliExpress/Banggood.
_Function Generators_ (WIP) (UNI-T)
  - _Not as important for hardware hacking, but useful if you're tinkering with electronics in general. Some oscilloscopes come with a built-in function generator, so you can look out for those._
  _Power Supply Units_
- [MDP-P905 Mini Power Supply](https://www.aliexpress.com/item/33056122346.html)
- [Hantek Power Supply](https://www.aliexpress.com/item/1005003642478236.html)
- [Wanptek Power Supply](https://www.aliexpress.com/item/1005001798369404.html)
- [Build Your Own Variable Lab Bench Power Supply](https://www.youtube.com/watch?v=wI-KYRdmx-E)
- [Simple Power Supply That Anyone Can Build](https://dronebotworkshop.com/simple-supply/)

### Software

- [Picoscope Software](https://www.picotech.com/downloads)
- [Saleae Logic Pro](https://www.saleae.com/downloads/) (use with _legit_ Saleaes only)
- [DSView](https://www.dreamsourcelab.com/download/) (works best with DSLogic Plus)
- [Sigrok](https://sigrok.org/wiki/Libsigrok) ([CLI](http://sigrok.org/wiki/Sigrok-cli)/[Pulseview](https://sigrok.org/wiki/PulseView)) (Open-source option)
  - [Supported hardware](https://sigrok.org/wiki/Supported_hardware)
  - [Pulseview User Manual](https://sigrok.org/doc/pulseview/0.4.1/manual.html)
  - [Sigrok GitHub mirror](https://github.com/sigrokproject)
- _Emulation and Environment Building_
  - [QEMU](https://www.qemu.org/) ([documentation](https://qemu-project.gitlab.io/qemu/))
  - [Yocto Project](https://www.yoctoproject.org/) (building the target environment to emulate on QEMU)
  - [Buildroot](https://buildroot.org/) (like Yocto but simpler, builds kernel and root FS only)
  - [OpenWRT](https://openwrt.org/) (similar but targeted at routers)

### Accessories

- [A good set of test leads](https://www.digikey.sg/en/products/filter/test-clips-grabbers-hooks/620?s=N4IgTCBcDaIKYC8AEALA9mg1iAugXyA)

---

## 7. Programmers and Sockets

These are used to program non-volatile memory such as EEPROMS. Normally used with SPI.

Generally, you should have a programmer capable of writing to most (E)EPROMS, and adapters for non-DIP form factors like SOIC or TSOP. Most sellers will add on these accessories at a cost.

An SOIC8 clip is usually a good start to a collection that you can build up over time.

- [Generic CH341A Programmer](https://www.aliexpress.com/item/1005003515809868.html)
- [TL866II EEPROM Programmer](https://www.aliexpress.com/item/32963724045.html)

---

## 8. Soldering and Rework

How else are you gonna get that TSOP48 flash chip off the PCB? A flathead screwdriver and a prayer?

### Soldering Irons

Soldering irons have two main methods of driving the tip: through a ceramic heating element directly below the tip, or direct drive, where the entire tip is a self-contained cartridge containing the heating element and thermocouple. The latter is more advanced, as it is more responsive and has better temperature regulation, but costs more. The former method is older, cheaper and generally found on entry-level irons like the Hakko 888D or Weller WE-1010, but there are a whole range of cheap and good Chinese irons employing direct drive technology. Direct drive technology is also employed by portable irons like the TS100 or Pinecil.

_Standard Irons_

- [KSGER T12 Soldering Iron](https://www.aliexpress.com/item/32971888371.html) (Great value direct-drive)
- [Aixun T3A](https://www.aliexpress.com/item/1005002983155657.html) (Smart direct-drive iron, get the stand as well)
- [XTronic 3020-XTS](https://www.amazon.com/dp/B01DGZFSNE/) (Great value low-cost set)
- [Hakko 888D](https://www.amazon.com/dp/B00ANZRT4M/) (_The_ beginner's iron)
- [Weller WE-1010](https://www.amazon.com/Weller-WE1010NA-Digital-Soldering-Station/dp/B077JDGY1J/) (Pretty good value)

_Portable Irons_

- [TS100](https://www.aliexpress.com/item/32860309312.html)
- [TS80P](https://www.aliexpress.com/item/32904980528.html)
- [Pinecil](https://pine64.com/product/pinecil-smart-mini-portable-soldering-iron/)

### Hot Air Guns

- [Yarboly 8858D](https://banggood.com/Yarboly-8858D-Hot-Air-Gun-BGA-Rework-Solder-Station-Hair-Dryer-for-Soldering-SMD-SMT-Welding-Repair-Tools-p-1880309.html)
- [PG8018LCD Hot Air Gun](https://www.aliexpress.com/item/4000183129636.html)
- [Handskit Micro Rework Station](https://www.aliexpress.com/item/1005002890887241.html)

### Rework Stations

- [2 in 1 ESD Soldering Station](https://www.aliexpress.com/item/32969863227.html)
- [Yihua 995D Soldering Rework Station](https://www.aliexpress.com/item/1794837776.html)
- [JCD 8898 2 in 1](https://banggood.com/JCD-8898-2-in-1-750W-Soldering-Station-Hot-Air-Gun-Heater-LCD-Digital-Display-Soldering-Iron-Welding-Rework-Station-for-Cell-phone-BGA-SMD-PCB-IC-Repair-p-1721250.html)

### Accessories

I don't think I need to link these, right? Google is your friend.

- Solder Flux
  - [Flux Comparison](https://www.youtube.com/watch?v=iKDAmY9Rdag)
- Solder Wire
  - _Tip: Get good rosin core solder. Anything below $10 isn't worth it. Good brands include Kester and Multicore, but some cheap Chinese brands are equally good._
  - _Another tip: Get a few rolls of different gauges. 0.4-5mm is good for SMD soldering, while 0.6-8mm is better suited for through-hole soldering._
  - [Solder Comparison](https://www.youtube.com/watch?v=zZ9wxs6xuYU)
- Solder Wick
- Desoldering Pump
- Helping Hands
- Fume Extractor (a must if your bench isn't well-ventilated)
  - [Generic Fume Extractor](https://www.aliexpress.com/item/32921948569.html)
  - [ANAVI Smart Fume Extractor](https://www.crowdsupply.com/anavi-technology/fume-extractor)
- Breadboard/Perfboard
- Various electronic components

---

## 9. Development

Sometimes the tools you have just aren't doing the exact job you need them to, or maybe there's the perfect tool out there but you need to cough up a neat pile of Benjamins to get your hands on it _cough_ <sub>JTAGulator</sub> _cough_. Just trade spending your money for using your precious time to create your own tool for the job instead!

### Hardware

- [Arduino](https://store.arduino.cc/) (and [compatible boards](https://thepihut.com/collections/arduino-compatible-boards))
- [Raspberry Pi 4/Zero](https://www.raspberrypi.com/products/) (full Linux system)
- [Raspberry Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) (ARM-based microcontroller)
- [ESP32](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20220204051728&SearchText=esp32) (Good for wireless dev)
- [STM32F103C8T6 "Blue Pill"](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20220204052238&SearchText=stm32f103c8t6)
  - You may need an [ST-Link V2 programmer](https://www.st.com/en/development-tools/st-link-v2.html) (or [clone](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20220204052346&SearchText=st+link+v2))
- [Put your own board together :P](https://www.pcbway.com/orderonline.aspx)

### Software

- [Arduino IDE](https://www.arduino.cc/en/software)
- [STM32duino](https://github.com/stm32duino/Arduino_Core_STM32) (program your STM32 board with the Arduino IDE)
- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (or not, I'm not your boss)
- [PlatformIO](https://platformio.org/) (like Arduino IDE on steroids)
- [libopencm3](https://libopencm3.org/) (ARM Cortex development library)
- [Pi Pico SDK](https://github.com/raspberrypi/pico-sdk)
- [rp2040_hal](https://docs.rs/rp2040-hal/latest/rp2040_hal/) (if you like Rust)
- [KiCAD](https://www.kicad.org/) (Roll your own PCB)
- [Altium CircuitMaker](https://www.altium.com/circuitmaker) (Windows only)
- [Verilog](https://www.chipverify.com/verilog/verilog-tutorial) (Hardware Description Language)

---

## 10. Other Resources

A lot of hacking isn't just tinkering around with boards and tools. Yes, that's what it is a lot of the time, but we also should learn from the best in our field, who were generous enough to share their knowledge in writing. The following is some of the best work put out by the best hacking heroes, and their contributions should not go unnnoticed.

### Publications

- [PoC||GTFO](https://unpack.debug.su/pocorgtfo/) ([What is it?](https://hackaday.com/2017/08/14/bibles-you-should-read-poc-gtfo/))
  - Want the dead tree edition? ([Vol 1](https://nostarch.com/gtfo) | [Vol 2](https://nostarch.com/gtfo2) | [Vol 3](https://nostarch.com/gtfo3))
  - Mirrors can be found [here](https://greatscottgadgets.com/pocorgtfo/), [here](http://pociigtfo.com/), and [here](https://github.com/angea/pocorgtfo)
- [Hacking: The Art of Exploitation 2nd Edition](https://nostarch.com/hacking2.htm)
- [The Hardware Hacking Handbook](https://nostarch.com/hardwarehacking)
- [Hardware Hacking: Have Fun While Voiding Your Warranty](http://www.grandideastudio.com/hardware-hacking-have-fun-while-voiding-your-warranty/)
- [Practical IoT Hacking](https://nostarch.com/practical-iot-hacking)
- [The Car Hacker's Handbook](https://nostarch.com/carhacking)
- [The Hardware Hacker](https://nostarch.com/hardwarehackerpaperback)
- [Hacking the Xbox](https://bunniefoo.com/nostarch/HackingTheXbox_Free.pdf) (An [open letter](https://nostarch.com/xboxfree) from the author)
- [Phrack Magazine](http://www.phrack.org/)
- [Colin O'Flynn](https://colinoflynn.com/research/publications/)
- USENIX ;login; ([Old](https://www.usenix.org/publications/login) | [New](https://www.usenix.org/publications/loginonline))

### Blogs and Web Content

- [Travis Goodspeed](http://travisgoodspeed.blogspot.com/)
- [Joe Grand](https://www.youtube.com/c/joegrand)
- [Colin O'Flynn](https://colinoflynn.com/) ([YouTube](https://www.youtube.com/channel/UCqc9MJwX_R1pQC6A353JmJg))
- [Andrew "bunnie" Huang](https://www.bunniestudios.com/)
- [Kate Temkin](https://www.ktemkin.com/)
- [Micah Scott](https://www.youtube.com/channel/UCaEgw3321ct_PE4PJvdhXEQ) ([scanlime](https://scanlime.org/))
- [wrongbaud](https://wrongbaud.github.io/)
- [Make Me Hack](https://www.youtube.com/c/MakeMeHack)
- [Ben Eater](https://www.youtube.com/c/beneater) ([Website](https://eater.net/))
- [LiveOverflow](https://www.youtube.com/channel/UClcE-kVhqyiHCcjYwcpfj9w)
- [Hackaday](https://hackaday.com/)
- [EEVblog](https://www.eevblog.com/)
- [Black Hat](https://www.youtube.com/user/BlackHatOfficialYT)
- [DEF CON](https://www.youtube.com/user/DEFCONConference)
- [Azeria Labs](https://azeria-labs.com/)

### Courses

- [Electronics and PCB Design](https://www.udemy.com/course/crash-course-electronics-and-pcb-design/) (Udemy)
- [ChipWhisperer.io Courses](https://learn.chipwhisperer.io/collections)
- [The Definitive Guide to ARM Exploitation](https://www.attify-store.com/products/the-definite-guide-to-arm-exploitation?variant=17929555443781)
- [IoT Exploitation Learning Kit](https://www.attify-store.com/products/iot-exploitation-learning-kit?variant=40984240585)
- [Offensive IoT Exploitation](https://www.attify-store.com/products/offensive-iot-exploitation)

### Stores

- Grand Idea Studio
- Dangerous Prototypes
- Crowd Supply (like Kickstarter, but for hardware)
- NewAE Technologies
- Great Scott Gadgets
- Attify
- Adafruit (good for Arduino/Raspi accessories)
- Sparkfun (also good for those)
- Digi-Key
- Seeed Studio
- AliExpress
- Amazon
- Lazada/Shopee (SEAsia only)
- Cytron.io (SEAsia only)

### Examples and Talks

- [How I hacked a hardware crypto wallet and recovered $2 million](https://www.youtube.com/watch?v=dT9y-KQbqi4)
- [Introduction to Hardware Hacking](https://www.youtube.com/watch?v=HuCbr2588-w)
- [Hardware Hacking with Joe Grand](https://www.youtube.com/watch?v=AQpv_6Se6VM)
- [Introduction to Side-Channel Power Analysis](https://www.youtube.com/watch?v=OlX-p4AGhWs)
- [Don't Whisper My Chips: Sidechannel and Glitching for Fun and Profit](https://www.youtube.com/watch?v=BHqrA8lzz2o)
- [Reversing and Exploiting Embedded Devices](https://www.youtube.com/watch?v=r4XntiyXMnA)
- [Glitchy Descriptor Firmware Grab](https://www.youtube.com/watch?v=TeCQatNcF20)
- [Hardware Power Glitch Attack](https://www.youtube.com/watch?v=6Pf3pY3GxBM)
- [Breaking AES with ChipWhisperer](https://www.youtube.com/watch?v=FktI4qSjzaE)
- [Achieving Linux Kernel Code Execution Through a Malicious USB Device](https://www.youtube.com/watch?v=ZEZIcjhsZEk)
- River Loop Security's Hardware Hacking 101 Series
  - [Getting a Root Shell via UART](https://www.riverloopsecurity.com/blog/2020/01/hw-101-uart/)
  - [Interfacing with SPI](https://www.riverloopsecurity.com/blog/2020/02/hw-101-spi/)
  - [Introduction to JTAG](https://www.riverloopsecurity.com/blog/2021/05/hw-101-jtag/)
  - [Identifying and Verifying JTAG on a Device](https://www.riverloopsecurity.com/blog/2021/05/hw-101-jtag-part2/)
  - [Communicating with JTAG via OpenOCD](https://www.riverloopsecurity.com/blog/2021/07/hw-101-jtag-part3/)
  - [Glitching into Privileged Shells](https://www.riverloopsecurity.com/blog/2020/10/hw-101-glitching/)
  - [Identifying and Dumping eMMC Flash](https://www.riverloopsecurity.com/blog/2020/03/hw-101-emmc/)
- [Hacking Huawei HG8012 ONT](https://github.com/logon84/Hacking_Huawei_HG8012H_ONT)

## Contributing

...is absolutely welcome! If I missed anything or you have something to add, just shoot a PR my way.
