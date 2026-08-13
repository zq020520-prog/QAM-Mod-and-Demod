# QPSK/16-QAM/64-QAM Modulation and Soft Demodulation

Implementation of **QPSK, 16-QAM and 64-QAM modulation and soft demodulation** for digital wireless communication systems.

## Overview

This project provides modulation and soft demodulation implementations for several commonly used digital modulation schemes:

* QPSK
* 16-QAM
* 64-QAM

The project focuses on the implementation of the modulation process and **soft-output demodulation**, which can provide soft information for subsequent channel decoding algorithms such as **LDPC** and **Turbo Codes**.

## Supported Modulation Schemes

| Modulation | Modulation Order | Bits/Symbol |
| ---------- | ---------------- | ----------- |
| QPSK       | 4                | 2           |
| 16-QAM     | 16               | 4           |
| 64-QAM     | 64               | 6           |

## Processing Flow

```text
Binary Bits
     │
     ▼
Bit Grouping
     │
     ▼
Modulation
     │
     ▼
QPSK / 16-QAM / 64-QAM
     │
     ▼
Complex Symbols
     │
     ▼
Wireless Channel
     │
     ▼
Received Symbols
     │
     ▼
Soft Demodulation
     │
     ▼
Soft Bits / LLRs
```

## Modulation

The input binary sequence is grouped according to the modulation order.

For example:

```text
QPSK   → 2 bits / symbol
16-QAM → 4 bits / symbol
64-QAM → 6 bits / symbol
```

The grouped bits are mapped to complex constellation points.

### QPSK

QPSK maps every 2 input bits to one complex symbol.

```text
2 bits → QPSK symbol
```

### 16-QAM

16-QAM maps every 4 input bits to one complex symbol.

```text
4 bits → 16-QAM symbol
```

### 64-QAM

64-QAM maps every 6 input bits to one complex symbol.

```text
6 bits → 64-QAM symbol
```

## Soft Demodulation

Unlike hard-decision demodulation, soft demodulation does not directly output `0` or `1`.

Instead, it calculates the reliability of each received bit and produces **Log-Likelihood Ratios (LLRs)** or equivalent soft information.

```text
Received Symbol
      │
      ▼
Constellation Distance
      │
      ▼
Bit Reliability Calculation
      │
      ▼
Soft Bits / LLRs
```

The soft information can then be passed to channel decoding algorithms.

## Application

The implemented modulation and soft demodulation modules can be used as building blocks in digital communication systems, including:

* OFDM
* LDPC-coded communication systems
* Physical Layer Security
* Software Defined Radio (SDR)
* Wireless communication simulations

## Features

* QPSK modulation
* 16-QAM modulation
* 64-QAM modulation
* QPSK soft demodulation
* 16-QAM soft demodulation
* 64-QAM soft demodulation
* Soft-bit / LLR generation
* Suitable for channel coding and decoding

## Project Structure

```text
.
├── QPSK/
│   ├── modulation
│   └── soft_demodulation
├── 16QAM/
│   ├── modulation
│   └── soft_demodulation
├── 64QAM/
│   ├── modulation
│   └── soft_demodulation
└── README.md
```

## Technologies

* MATLAB
* Digital Modulation
* QPSK
* QAM
* Soft Demodulation
* LLR
* Digital Communications


## License

This project is for research and educational purposes.

