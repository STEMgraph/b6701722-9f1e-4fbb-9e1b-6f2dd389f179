<!---
{
  "depends_on": ["https://github.com/STEMgraph/8fd3f76a-24d1-460b-9f88-9ff63809e8f5"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-03-31",
  "keywords": ["signal", "encoding", "transmission", "electrons"]
}
--->

# Current Based Wired Transmission

## 1) Introduction

One of the main limitations of [the lake-based information transmission](https://github.com/STEMgraph/8fd3f76a-24d1-460b-9f88-9ff63809e8f5) experiment is the physical mass that must be moved to represent changes in signal levels. A more efficient approach involves the movement of electrons through metal—this is the foundation of wired communication.

In wired systems, we distinguish between two types of signal representation:
- **Voltage-based signals**
- **Current-based signals**

Let’s first explore current-based transmission.

After **Alessandro Volta** discovered the battery-electric effect in 1800, and **Hans Christian Ørsted** revealed the magnetic properties of electric current, **Carl Friedrich Gauss** and **Wilhelm Eduard Weber** devised a practical application: the first *electromagnetic telegraph*. It connected the **astronomical observatory** and the **physics institute in Göttingen** via two copper wires, each roughly [3 km long](https://earth.google.com/earth/d/1dlpSrjbz7LeSfz2X91r8uH9JxkDAH3C9?usp=sharing).

At the astronomical institute, a coil could be moved vertically around a magnet to induce a current. Using a switch, this current was injected into the wire in either a forward or reverse direction. On the receiving side—at the physics institute—a coil sat beneath a suspended magnet. When current flowed through the coil, it produced a magnetic field whose orientation depended on the current direction. This caused the hanging magnet to swing either clockwise or counterclockwise.

To visualize this movement, a mirror was attached to the magnet, and a light beam was directed at it. As the magnet turned, the reflection of the light would shift left or right across a distant surface. These directional movements formed a visual signal, which Gauss and Weber used to encode letters of the alphabet.

---

Even 130 years later, when the teletypewriter became the standard interface for minicomputers, **current loops** were still used for signal transmission.  
In 1963, the **ASCII code** was standardized, laying the foundation for modern digital communication.


<details>

  <summary>The ASCII Table</summary>

  | Dec | Hex  | Bin       | Char | Description         |
|-----|------|-----------|------|---------------------|
|  0  | 0x00 | 0000000   | NUL  | Null                |
|  1  | 0x01 | 0000001   | SOH  | Start of Header     |
|  2  | 0x02 | 0000010   | STX  | Start of Text       |
|  3  | 0x03 | 0000011   | ETX  | End of Text         |
|  4  | 0x04 | 0000100   | EOT  | End of Transmission |
|  5  | 0x05 | 0000101   | ENQ  | Enquiry             |
|  6  | 0x06 | 0000110   | ACK  | Acknowledge         |
|  7  | 0x07 | 0000111   | BEL  | Bell                |
|  8  | 0x08 | 0001000   | BS   | Backspace           |
|  9  | 0x09 | 0001001   | TAB  | Horizontal Tab      |
| 10  | 0x0A | 0001010   | LF   | Line Feed           |
| 11  | 0x0B | 0001011   | VT   | Vertical Tab        |
| 12  | 0x0C | 0001100   | FF   | Form Feed           |
| 13  | 0x0D | 0001101   | CR   | Carriage Return     |
| 14  | 0x0E | 0001110   | SO   | Shift Out           |
| 15  | 0x0F | 0001111   | SI   | Shift In            |
| 16  | 0x10 | 0010000   | DLE  | Data Link Escape    |
| 17  | 0x11 | 0010001   | DC1  | Device Control 1    |
| 18  | 0x12 | 0010010   | DC2  | Device Control 2    |
| 19  | 0x13 | 0010011   | DC3  | Device Control 3    |
| 20  | 0x14 | 0010100   | DC4  | Device Control 4    |
| 21  | 0x15 | 0010101   | NAK  | Negative Ack        |
| 22  | 0x16 | 0010110   | SYN  | Synchronous Idle    |
| 23  | 0x17 | 0010111   | ETB  | End of Transmit Blk |
| 24  | 0x18 | 0011000   | CAN  | Cancel              |
| 25  | 0x19 | 0011001   | EM   | End of Medium       |
| 26  | 0x1A | 0011010   | SUB  | Substitute          |
| 27  | 0x1B | 0011011   | ESC  | Escape              |
| 28  | 0x1C | 0011100   | FS   | File Separator      |
| 29  | 0x1D | 0011101   | GS   | Group Separator     |
| 30  | 0x1E | 0011110   | RS   | Record Separator    |
| 31  | 0x1F | 0011111   | US   | Unit Separator      |
| 32  | 0x20 | 0100000   | (space) | Space            |
|  33 | 0x21 | 0100001   |  !   | Exclamation mark    |
|  34 | 0x22 | 0100010   |  "   | Quotation mark      |
|  35 | 0x23 | 0100011   |  #   | Number sign         |
|  36 | 0x24 | 0100100   |  $   | Dollar sign         |
|  37 | 0x25 | 0100101   |  %   | Percent sign        |
|  38 | 0x26 | 0100110   |  &   | Ampersand           |
|  39 | 0x27 | 0100111   |  '   | Apostrophe          |
|  40 | 0x28 | 0101000   |  (   | Left parenthesis    |
|  41 | 0x29 | 0101001   |  )   | Right parenthesis   |
|  42 | 0x2A | 0101010   |  *   | Asterisk            |
|  43 | 0x2B | 0101011   |  +   | Plus sign           |
|  44 | 0x2C | 0101100   |  ,   | Comma               |
|  45 | 0x2D | 0101101   |  -   | Hyphen-minus        |
|  46 | 0x2E | 0101110   |  .   | Period              |
|  47 | 0x2F | 0101111   |  /   | Slash               |
|  48 | 0x30 | 0110000   |  0   | Digit zero          |
|  49 | 0x31 | 0110001   |  1   | Digit one           |
|  50 | 0x32 | 0110010   |  2   | Digit two           |
|  51 | 0x33 | 0110011   |  3   | Digit three         |
|  52 | 0x34 | 0110100   |  4   | Digit four          |
|  53 | 0x35 | 0110101   |  5   | Digit five          |
|  54 | 0x36 | 0110110   |  6   | Digit six           |
|  55 | 0x37 | 0110111   |  7   | Digit seven         |
|  56 | 0x38 | 0111000   |  8   | Digit eight         |
|  57 | 0x39 | 0111001   |  9   | Digit nine          |
|  58 | 0x3A | 0111010   |  :   | Colon               |
|  59 | 0x3B | 0111011   |  ;   | Semicolon           |
|  60 | 0x3C | 0111100   |  <   | Less-than sign      |
|  61 | 0x3D | 0111101   |  =   | Equals sign         |
|  62 | 0x3E | 0111110   |  >   | Greater-than sign   |
|  63 | 0x3F | 0111111   |  ?   | Question mark       |
|  64 | 0x40 | 1000000   |  @   | At sign             |
|  65 | 0x41 | 1000001   |  A   | Uppercase A         |
|  66 | 0x42 | 1000010   |  B   | Uppercase B         |
|  67 | 0x43 | 1000011   |  C   | Uppercase C         |
|  68 | 0x44 | 1000100   |  D   | Uppercase D         |
|  69 | 0x45 | 1000101   |  E   | Uppercase E         |
|  70 | 0x46 | 1000110   |  F   | Uppercase F         |
|  71 | 0x47 | 1000111   |  G   | Uppercase G         |
|  72 | 0x48 | 1001000   |  H   | Uppercase H         |
|  73 | 0x49 | 1001001   |  I   | Uppercase I         |
|  74 | 0x4A | 1001010   |  J   | Uppercase J         |
|  75 | 0x4B | 1001011   |  K   | Uppercase K         |
|  76 | 0x4C | 1001100   |  L   | Uppercase L         |
|  77 | 0x4D | 1001101   |  M   | Uppercase M         |
|  78 | 0x4E | 1001110   |  N   | Uppercase N         |
|  79 | 0x4F | 1001111   |  O   | Uppercase O         |
|  80 | 0x50 | 1010000   |  P   | Uppercase P         |
|  81 | 0x51 | 1010001   |  Q   | Uppercase Q         |
|  82 | 0x52 | 1010010   |  R   | Uppercase R         |
|  83 | 0x53 | 1010011   |  S   | Uppercase S         |
|  84 | 0x54 | 1010100   |  T   | Uppercase T         |
|  85 | 0x55 | 1010101   |  U   | Uppercase U         |
|  86 | 0x56 | 1010110   |  V   | Uppercase V         |
|  87 | 0x57 | 1010111   |  W   | Uppercase W         |
|  88 | 0x58 | 1011000   |  X   | Uppercase X         |
|  89 | 0x59 | 1011001   |  Y   | Uppercase Y         |
|  90 | 0x5A | 1011010   |  Z   | Uppercase Z         |
|  91 | 0x5B | 1011011   |  [   | Left square bracket |
|  92 | 0x5C | 1011100   |  \\  | Backslash           |
|  93 | 0x5D | 1011101   |  ]   | Right square bracket|
|  94 | 0x5E | 1011110   |  ^   | Caret               |
|  95 | 0x5F | 1011111   |  _   | Underscore          |
|  96 | 0x60 | 1100000   |  `   | Grave accent        |
|  97 | 0x61 | 1100001   |  a   | Lowercase a         |
|  98 | 0x62 | 1100010   |  b   | Lowercase b         |
|  99 | 0x63 | 1100011   |  c   | Lowercase c         |
| 100 | 0x64 | 1100100   |  d   | Lowercase d         |
| 101 | 0x65 | 1100101   |  e   | Lowercase e         |
| 102 | 0x66 | 1100110   |  f   | Lowercase f         |
| 103 | 0x67 | 1100111   |  g   | Lowercase g         |
| 104 | 0x68 | 1101000   |  h   | Lowercase h         |
| 105 | 0x69 | 1101001   |  i   | Lowercase i         |
| 106 | 0x6A | 1101010   |  j   | Lowercase j         |
| 107 | 0x6B | 1101011   |  k   | Lowercase k         |
| 108 | 0x6C | 1101100   |  l   | Lowercase l         |
| 109 | 0x6D | 1101101   |  m   | Lowercase m         |
| 110 | 0x6E | 1101110   |  n   | Lowercase n         |
| 111 | 0x6F | 1101111   |  o   | Lowercase o         |
| 112 | 0x70 | 1110000   |  p   | Lowercase p         |
| 113 | 0x71 | 1110001   |  q   | Lowercase q         |
| 114 | 0x72 | 1110010   |  r   | Lowercase r         |
| 115 | 0x73 | 1110011   |  s   | Lowercase s         |
| 116 | 0x74 | 1110100   |  t   | Lowercase t         |
| 117 | 0x75 | 1110101   |  u   | Lowercase u         |
| 118 | 0x76 | 1110110   |  v   | Lowercase v         |
| 119 | 0x77 | 1110111   |  w   | Lowercase w         |
| 120 | 0x78 | 1111000   |  x   | Lowercase x         |
| 121 | 0x79 | 1111001   |  y   | Lowercase y         |
| 122 | 0x7A | 1111010   |  z   | Lowercase z         |
| 123 | 0x7B | 1111011   |  {   | Left curly brace    |
| 124 | 0x7C | 1111100   |  \|   | Vertical bar        |
| 125 | 0x7D | 1111101   |  }   | Right curly brace   |
| 126 | 0x7E | 1111110   |  ~   | Tilde               |
| 127 | 0x7F | 1111111   | DEL  | Delete              |

  

</details>

The earliest teletypes used **current loops**, where the sender controlled a current source that could be interrupted by a switch.  
A terminal on the teletype, labeled `TX` (for **transmit**), was connected to this switch. This `TX` terminal could be wired to the `RX` (for **receive**) terminal of a second teletype.

Inside the receiving teletype, a circuit monitored the **interruptions in the current flow**. These were interpreted as digital signals and used to position a type lever onto the paper.

The same principle applied in the reverse direction: the `TX` of the second machine was connected to the `RX` of the first, enabling full two-way communication.

> ⚠️ Even today, the `TX` and `RX` labels cause frequent confusion in electrical engineering—especially when dealing with RS-232 or microcontroller UART connections.  
> Always remember: **`TX` and `RX` refer to the device's terminals, not the wire itself!**

<figure>
  <div style="display: flex; gap: 12px; align-items: center; justify-content: center;">
    <img src="https://maxclerkwell.github.io/svg_storage/fundamentals/transmission/single_wire_current_loop/closed.svg" alt="Logic 0 - current flows" width="40%"/>
    <img src="https://maxclerkwell.github.io/svg_storage/fundamentals/transmission/single_wire_current_loop/open.svg" alt="Logic 1 - no current" width="40%"/>
  </div>
  <figcaption style="text-align: center; margin-top: 8px;">
    Single transmission line sending a 0 (switch closed, current flows) and 1 (switch open, no current).
  </figcaption>
</figure>



### 1.1) Further Readings and Other Sources

- [The Telegraph That Brought Down the Iron Curtain](https://spectrum.ieee.org/gauss-weber-telegraph)  
  *IEEE Spectrum* article exploring the historical impact and technical design of the Gauss-Weber electromagnetic telegraph.

- [The ASCII Table and Standard Explained](https://www.asciitable.com/)  
  A detailed and interactive reference for ASCII, including control codes and printable characters, useful for understanding teletype encoding.

- *Code: The Hidden Language of Computer Hardware and Software* by Charles Petzold  
  A highly accessible book that walks through the evolution from relays to logic gates and encoding systems like ASCII and Unicode.

- [Current Loops: The Forgotten Interface](https://www.eetimes.com/current-loops-the-forgotten-interface/)  
  A technical reflection on current loop interfaces, their role in early computing, and their continued use in industrial applications.


## 2) Tasks

1. **Signal Path Sketch**: Draw and label the complete current-loop signal path between two teletypes, including TX, RX, switch, and type mechanism.

2. **ASCII Value Match**: Find the ASCII binary code for the letters in the word `SIGNAL` and explain what would happen in the current loop for each bit.

3. **Error Simulation**: Modify one bit in an ASCII character and explain how it would affect the printed character on a teletype.

4. **TX/RX Pairing Task**: Given a set of four teletype machines, connect their TX/RX ports for bidirectional communication in pairs and justify your wiring.

5. **Design Your Code**: Create your own 5-bit character set (like Baudot-Code) and define shift states to represent both letters and numbers.

6. **Historical Comparison**: Compare the Gauss-Weber telegraph with a modern UART system in a two-column table.


## 3) Questions
1. How does the direction of current in the Gauss-Weber telegraph influence the position of the mirror and the resulting light deflection?
2. Why was it necessary to define a standardized character set like ASCII for communication between teletypes?
3. What are the advantages of using current-based signaling over voltage-based signaling in early long-distance transmission systems?
4. How did the `TX` and `RX` labels help (or confuse) when wiring two teletypes together for bidirectional communication?

## 4) Advice

Although current loops have largely vanished from mainstream digital communication, their legacy lives on—not just in industrial control systems using 4–20 mA analog transmission, but also in the mindset they helped shape: clear physical causality between signal and action. They remind us that information is always embedded in physical systems, whether it's a swinging magnet in Göttingen, a type lever striking inked paper, or electrons moving through silicon gates.

As we move forward into protocols, wireless systems, and software-defined signals, don’t forget the foundational importance of understanding how things are connected—literally. Signals aren’t abstract: they travel through wires, across air, and between devices with defined roles.

And finally, always double-check your `TX` and `RX` lines—because even seasoned engineers still get them backwards.
