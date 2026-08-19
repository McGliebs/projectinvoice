# Third-Party Notices — Gerador Faturas para SSM

Gerador Faturas para SSM is distributed as a single Windows executable built with
PyInstaller. That executable embeds the components listed below, each licensed
by its own owner under its own terms. Those terms apply to those components and
prevail over the Gerador Faturas para SSM licence in respect of them.

All components listed here are distributed under permissive licences that
allow inclusion in a commercial, closed-source product, provided the copyright
notices are retained — which this file does.

---

## Runtime and graphical interface

### Python (CPython runtime and standard library)

- Copyright © 2001–2026 Python Software Foundation. All Rights Reserved.
- Licence: PSF License Agreement (BSD-style, permits redistribution in
  proprietary products provided the copyright notice is retained).
- <https://docs.python.org/3/license.html>

### Tcl/Tk (via the `tkinter` graphical interface)

- Copyright © the Regents of the University of California, Sun Microsystems,
  Inc., Scriptics Corporation, and other parties.
- Licence: Tcl/Tk licence (BSD-style).
- <https://www.tcl.tk/software/tcltk/license.html>

### tkinterdnd2 (drag-and-drop support) — 0.4.3

- Licence: MIT. Wraps the `tkdnd` Tk extension (BSD-style licence).
- <https://github.com/pmgagne/tkinterdnd2>

---

## PDF reading (EasyJet and Porto Santo Line documents)

### pdfplumber — 0.11.9

- Copyright © Jeremy Singer-Vine and contributors.
- Licence: MIT.
- <https://github.com/jsvine/pdfplumber>

### pdfminer.six — 20251230

- Copyright © Yusuke Shinyama, Philippe Guglielmetti and contributors.
- Licence: MIT.
- <https://github.com/pdfminer/pdfminer.six>

### Pillow — 12.2.0

- Copyright © 1997–2011 by Secret Labs AB, © 1995–2011 by Fredrik Lundh,
  © 2010–2026 by Jeffrey A. Clark and contributors.
- Licence: MIT-CMU (HPND-style).
- <https://github.com/python-pillow/Pillow/blob/main/LICENSE>

### pypdfium2 — 5.7.0

- Licence: BSD-3-Clause and Apache-2.0 (dual), plus dependency licences.
- Embeds **PDFium** (Copyright © The PDFium Authors / Google LLC),
  licensed BSD-3-Clause.
- <https://github.com/pypdfium2-team/pypdfium2>

### cryptography — 46.0.7

- Copyright © The Python Cryptographic Authority and individual contributors.
- Licence: Apache-2.0 OR BSD-3-Clause (dual-licensed; either may be chosen).
- Pulled in as a dependency of the PDF stack for encrypted-PDF support.
- <https://github.com/pyca/cryptography>

### charset-normalizer — 3.4.7

- Copyright © Ahmed R. TAHRI.
- Licence: MIT.
- <https://github.com/jawah/charset_normalizer>

---

## Build tool

### PyInstaller (bootloader embedded in the executable)

- Copyright © 2005–2026 PyInstaller Development Team.
- Licence: GPL 2.0 or later, **with an explicit exception** permitting the
  bootloader to be linked into, and distributed with, applications that are not
  themselves open source. This exception is what allows Gerador Faturas para SSM to
  be distributed commercially.
- <https://github.com/pyinstaller/pyinstaller/blob/develop/COPYING.txt>

---

## Services accessed at runtime (not embedded)

**GitHub Releases** — the application checks for and downloads its own updates
from the Licensor's public release repository. No licensee data is sent; the
request is an anonymous, read-only HTTPS call to the public GitHub API.
<https://github.com>

**Microsoft Windows Credential Manager** — used only by the developer-side
publishing tool (`publish.py`) to store the GitHub token locally. Part of the
operating system; not redistributed, and not used by the end-user application.

---

## Data processed locally

Booking data, ticket records, and PDF documents supplied by the licensee are
processed entirely on the local machine. They are not transmitted to the
Licensor or to any third party by the Software.

---

*For strict distribution compliance, ship the full licence texts of the
components above alongside the executable (or reproduce them in this file) if
your distribution channel requires the complete texts rather than these notices
and links.*
