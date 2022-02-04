# awesome-hardware-hacking

## A humble list of hardware hacking tools and resources curated by yours truly

---

_Are you new to the wonderful world of hardware hacking? Swamped with resources and different tools and don't know where to turn?_

Have I got the solution for you!

This compendium was born out of my initial confusion, and overwhelming from all the various types of hardware hacking tools, resources, and types that are out there. I intend for this to track which tools are available for each aspect of hardware tinkering, as well as various resources that may come in handy.

Happy hacking!

---

## Table of Contents

1. [**UART/SPI/I2C/JTAG**](#1)
2. [**USB**](#2)
3. [**RF**](#3)
4. [**Automotive**](#4)
5. [**Glitching/Cracking**](#5)
6. [**Analysis/Measurement**](#6)
7. [**Soldering/Rework/Programming**](#7)
8. [**Development**](#8)
9. [**Other Resources**](#9)

---

## 1. UART/SPI/I2C/JTAG

- What is [UART](https://www.arrow.com/en/research-and-events/articles/what-is-uart-protocol-uart-communication-explained)/[SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface)/[I2C](https://en.wikipedia.org/wiki/I%C2%B2C)/[JTAG](https://en.wikipedia.org/wiki/JTAG)?

### Hardware

- [Tigard](https://github.com/tigard-tools/tigard) (All 4)
- [GreatFET One](https://greatscottgadgets.com/greatfet/one/) (All 4 + USB)
- [HydraBus](https://hydrabus.com/?v=0f177369a3b7) (All 4 and more!)
- [Shikra](https://int3.cc/products/the-shikra) (All 4)
- [Attify Badge](https://www.attify-store.com/products/attify-badge-uart-jtag-spi-i2c) (All 4)
- [Bus Pirate](http://dangerousprototypes.com/docs/Bus_Pirate) (All 4, outdated, use something else)
- Arduino [Uno](https://www.arduino.cc/en/pmwiki.php?n=Main/arduinoBoardUno)/[Nano](https://www.arduino.cc/en/pmwiki.php?n=Main/ArduinoBoardNano) (JTAG enumeration, UART)
- [Seeeduino Nano](https://www.seeedstudio.com/Seeeduino-Nano-p-4111.html) (see above)
- Generic FT2232 Serial-USB breakout board ([Micro-USB](https://www.sparkfun.com/products/12731))
- [JTAGulator](http://www.grandideastudio.com/jtagulator/) (JTAG/UART Enumeration)
- [Segger J-Link Edu](https://www.adafruit.com/product/1369) (JTAG debugger)

### Software

- [OpenOCD](https://openocd.org/) (JTAG/SWD debugging)
- [JTAGenum](https://github.com/cyphunk/JTAGenum) (JTAG enumeration)
  - [JTAGulator vs. JTAGenum](https://www.praetorian.com/blog/jtagulator-vs-jtagenum-tools-for-identifying-jtag-pins-in-iot-devices/)
- [UrJTAG](http://urjtag.org/) (low-level JTAG interface)
- [picocom](https://github.com/npat-efault/picocom)/[minicom](https://wiki.emacinc.com/wiki/Getting_Started_With_Minicom)/[screen](https://www.gnu.org/software/screen/)/[PuTTY](https://www.putty.org/) (UART interface)
  - _Tip: Stick to picocom, PuTTY for Windows. Minicom and Screen are ancient._
- [flashrom](https://www.flashrom.org/Flashrom) (SPI flashing)
- [pyftdi](https://eblot.github.io/pyftdi/)/[spiflash](https://github.com/eblot/pyspiflash) (programmatic SPI/I2C via FTDI)
- [libmpsse](https://github.com/devttys0/libmpsse) (programmatic SPI)

---

## 2. USB

### Hardware

- [PhyWhisperer](https://github.com/newaetech/phywhispererusb) (sniffing/triggering)
- [GreatFET One](https://greatscottgadgets.com/greatfet/one/) (USB interface)
- [LUNA](https://greatscottgadgets.com/luna/) (protocol sniffer/analyzer)
- [FaceDancer 21](https://int3.cc/products/facedancer21) (supplanted by GreatFET)

### Software

- [FaceDancer](https://github.com/greatscottgadgets/Facedancer) (USB device emulation)
- [PhyWhisperer](https://phywhispererusb.readthedocs.io/en/latest/) (Python library)

---

## 3. RF (WIP)

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

## 4. Automotive (WIP)

### Hardware

- [Microchip CAN Analyzer](https://www.microchip.com/en-us/development-tool/apgdt002)
- [USB2CAN](https://www.8devices.com/products/usb2can_korlan) (CAN Bus sniffer)

### Software

- [Wireshark](https://www.wireshark.org/) (CAN packet analyser)

---

## 5. Glitching/Cracking

### Hardware

- [ChipWhisperer](https://github.com/newaetech/chipwhisperer) (Glitching, SCA, DPA)

### Software

- [ChipWhisperer](https://chipwhisperer.readthedocs.io/en/latest/) (ipynb)
- [Hashcat](https://hashcat.net/hashcat/) (bruteforce password cracker)
- [John the Ripper](https://www.openwall.com/john/) (see above)

---

## 6. Analysis/Measurement

### Hardware

- _Oscilloscopes_
  - [Rigol DS1000Z-series Oscilloscopes](https://int.rigol.com/products/detail/DS1000Z) (Desktop)
  - [Picoscope 2000-series Oscilloscopes](https://www.picotech.com/oscilloscope/2000/picoscope-2000-overview) (USB)
  - [ChipWhisperer](https://github.com/newaetech/chipwhisperer)
  - [Hantek 6022be](http://www.hantek.com/products/detail/31) (Not great, but it's cheap)
- _Logic Analyzers_
  - [Saleae Logic Pro Logic Analyzers](https://www.saleae.com/) (8-16ch, 25-100MHz/100-500MS/s)
  - [DSLogic Plus Logic Analyzer](https://www.dreamsourcelab.com/shop/logic-analyzer/dslogic-plus/) (16ch, up to 400MHz)
  - [BitMagic Basic Logic Analyzer](https://1bitsquared.com/products/bitmagic-basic) (8ch 24MHz)
  - [Generic USB Saleae Logic 8 Clone](https://www.aliexpress.com/item/1005003812410259.html) (8ch 24MHz)
- _Multimeters_
  - [Mastech 8268](https://www.amazon.com/Mastech-MS8268-Digital-Manual-Multimeter/dp/B000JQ4O2U)
  - [UNI-T UT61E+ True RMS](https://www.uni-trend.com/meters/html/product/General_Meters/Digital_Multimeters/UT61%20161%20Series/UT61E+.html)
  - [Klein Tools MM600](https://www.amazon.com/dp/B018CLOSTC?tag=healthyhandyman-20&linkCode=osi&th=1&psc=1)
  - [EEVblog BM235](https://www.eevblog.com/product/bm235/)
  - [Brymen BM869S](https://brymenmeter.com/brymen-bm869s-multimeter.html)
  - [Fluke 115](https://www.fluke.com/en-us/product/electrical-testing/digital-multimeters/fluke-115)
  - [Fluke 87V](https://www.fluke.com/en-us/product/electrical-testing/digital-multimeters/fluke-87v)
- _Function Generators_ (WIP) (UNI-T)
- _Power Supply Units_ (WIP) (Tenma)

### Software

- [Picoscope Software](https://www.picotech.com/downloads)
- [Saleae Logic Pro](https://www.saleae.com/downloads/) (use with _legit_ Saleaes only)
- [DSView](https://www.dreamsourcelab.com/download/) (works best with DSLogic Plus)
- [Sigrok](https://github.com/sigrokproject/libsigrok) ([CLI](http://sigrok.org/wiki/Sigrok-cli)/[Pulseview](https://github.com/sigrokproject/pulseview)) (Open-source option)
  - [Supported hardware](https://sigrok.org/wiki/Supported_hardware)

### Accessories

- [A good pair of test leads](https://www.digikey.sg/en/products/filter/test-clips-grabbers-hooks/620?s=N4IgTCBcDaIKYC8AEALA9mg1iAugXyA)

---

## 7. Soldering/Rework/Programming (WIP)

### Soldering Irons

- _Mains Powered Irons_
  - [KSGER T12 Soldering Iron](https://www.aliexpress.com/item/32971888371.html)
  - [Aixun T3A](https://www.aliexpress.com/item/1005002983155657.html)
  - [XTronic 3020-XTS](https://www.amazon.com/dp/B01DGZFSNE/)
  - [Hakko 888D](https://www.amazon.com/dp/B00ANZRT4M/)
  - [Weller WE-1010](https://www.amazon.com/Weller-WE1010NA-Digital-Soldering-Station/dp/B077JDGY1J/)
- _USB-Powered Irons_
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

- Flux Pen
- Solder
  - _Tip: Get good rosin core solder. Anything below $10 isn't worth it._
- Solder Wick
- Desoldering Pump
- Helping Hands
- Fume Extractor (a must if your bench isn't well-ventilated)
  - [Generic Fume Extractor](https://www.aliexpress.com/item/32921948569.html)
  - [ANAVI Smart Fume Extractor](https://www.crowdsupply.com/anavi-technology/fume-extractor)
- Breadboard/Perfboard
- Various electronic components

### Programmers and Sockets (WIP)

These are used to program non-volatile memory such as EEPROMS. Normally used with SPI.

Generally, you should have a programmer capable of writing to most (E)EPROMS, and adapters for non-DIP form factors like SOIC or TSOP. Most sellers will add on these accessories at a cost.

An SOIC8 clip is usually a must.

- [Generic CH341A Programmer](https://www.aliexpress.com/item/1005003515809868.html)
- [TL866II EEPROM Programmer](https://www.aliexpress.com/item/32963724045.html)

---

## 8. Development (WIP)

### Hardware

- [Arduino](https://store.arduino.cc/) (and [compatible boards](https://thepihut.com/collections/arduino-compatible-boards))
- [Raspberry Pi](https://www.raspberrypi.com/products/)
- [ESP32](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20220204051728&SearchText=esp32) (Good for wireless dev)
- [STM32F103C8T6 "Blue Pill"](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20220204052238&SearchText=stm32f103c8t6)
  - You may need an [ST-Link V2 programmer](https://www.st.com/en/development-tools/st-link-v2.html) (or [clone](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20220204052346&SearchText=st+link+v2))
- [Put your own board together :P](https://www.pcbway.com/orderonline.aspx)

### Software

- [Arduino IDE](https://www.arduino.cc/en/software)
- [STM32duino](https://github.com/stm32duino/Arduino_Core_STM32) (program your STM32 board with the Arduino IDE)
- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (or not, I'm not your boss)
- [KiCAD](https://www.kicad.org/) (Roll your own PCB)
- [Verilog](https://www.chipverify.com/verilog/verilog-tutorial) (Hardware Description Language)

---

## 9. Other Resources

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
