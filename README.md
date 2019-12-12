# Sally-CF
Sally-CF - IDE Compact Flash card interface for 8-bit Atari XL/XE computers.

Design assumptions:
- Identical functionality to XEL-CF
- Easy DIY assembly thanks to THT components
- Compatibility with as many CF cards as possible (and SD/microSD card adapters)
- Possibility to use the shortest possible IDE 44 cable thanks to the conveniently placed connector
- CPU output signals for U1MB (Phi2, R/W, RST, HLT) with the same pinout as in Ulitmate 1MB module
- Connector for: Activity LED, Swap Button, Swap LED (optional)
- Connector for signals from motherboard: /$D1xx and B02
- PCB versions matching XL and XE series (Atari 800 XL, Atari 65/130/800 XE with ECI port)
- Probably future adaptation to 600/1200 XL

## BOM
```
Reference  Quantity Value             Info
C1 C2 C3   3        0.1uF             Capacitor THT 2.54mm 10%
D1         1        1N914             Diode THT DO-35/SOD-25 (1N914 or 1N4148)
J1         1        DIL40             40-pin Precision Socket W15.24mm
J2         1        SWITCH/LED CONN   1x6 Pin Header 2.54mm
J3         1        IDE HEADER        2x22 Pin Header 2mm
J4         1        Wires             1x2 Pin Header 2.54mm
J5         1        U1MB Conn         1x4 Pin Header 2.54mm
Q1         1        PN2222            Transistor NPN 40V 0.8A TO-92
R2 R1      2        1K                Resistor THT 0207 5%
R3 R4      2        390R              Resistor THT 0207 5%
RN2 RN1    2        3 * 75R           Resistor Network 6-pin SIP (or 6 x 75R Resistors THT)
U1         1        SN74F138          IC DIP16 W7.62mm 74F138 - 1-of-8 Decoder/Demultimplexer
U2         1        SN74F32N          IC DIP14 W7.62mm 74F32  - Quad NOR Gates
U3         1        SN74F00N          IC DIP14 W7.62mm 74F00  - Quad NAND Gates
U4         1        SN74F245N         IC DIP20 W7.62mm 74F245 - Octal Transceiver with 3-state outputs
```

## PCB


## Assembly

B02 - CPU Phase 2 Clock Output, /D1xx - Chip select at area $D100 - $D1FF

XL:
```
B02   - PBI connector - pin 31 / Cartridge port - pin S (30)
/D1xx - U2 (74L138) - pin 14 (not connected)
```

XE:
```
B02   - Cartridge port - pin S (30)
/D1XX - ECI port - pin 3
```

Reference:
http://www.hardwarebook.info/Enhanced_Cartridge_Interface
http://www.hardwarebook.info/Atari_Parallel_Bus_Interface
http://www.hardwarebook.info/Atari_8-bit_Cartridge


## Partitioning CF card
