# P24 Science Stimulator — Python Notebooks (Hasomed GmbH)

This repository contains two Jupyter notebooks that implement a **USB protocol interface** and **multi‑channel stimulation control** for the **Hasomed P24 Science Stimulator**. The code is written in Python and communicates with the device over USB using `pyusb`.

> **Disclaimer & Safety**  
> This project is **unofficial**. It is provided **as‑is** for research and development. **Electrical stimulation can be hazardous.** Only operate the stimulator if you understand the implications, have appropriate ethics/approvals, and have verified all parameters on a phantom/dummy load first. Start with **zero amplitude** and increase cautiously. You are responsible for compliance with local regulations and device manuals.

---

## Contents

- **`Messenger_05_13_24.ipynb`** — Protocol explorer & single/dual‑channel control

- **`Messenger_Eight_Channels.ipynb`** — 8‑channel controller & pattern generators


> **Vendor/Product ID**  
> The code searches for a USB device with **VID `0x0483`** and **PID `0x5740`**. Adjust if your unit exposes different IDs/driver mode.

---

## Installation

1. **Python**: 3.10+ recommended.
2. **System dependency**: `libusb` (Linux/macOS). On Windows, install a libusb‑compatible driver if needed.
3. **Python packages**:
   ```bash
   pip install pyusb numpy matplotlib keyboard
   ```
   `tkinter` ships with most Python distributions (on some Linux distros you may need `python3-tk`).


## Quickstart

1. Connect the **P24 Science Stimulator** via USB and power it on.
2. Open a notebook and run the setup cells. 

3. Build a **payload** with one of the `update_*` helpers, then wrap and send it:

4. For time‑varying patterns over multiple channels, use the vector helpers and the convenience sender.


> **Important**: Amplitude and pulse‑width units and allowed ranges are **device‑specific**. The code maps amplitudes and widths into bit‑fields (e.g., `int(2*amp)+300`, 12‑bit widths, 10‑bit amp fields, frequency blocks), but you must confirm the **exact physical units, limits, and safe operating ranges** in the official P24 documentation. Do **not** assume a default unit (mA/µs) without verifying.



## Copyright / License
© 2025 Reza Zolnouri. All rights reserved.  
No license granted—please contact the author for permissions.

