# FlatCAM-Python3.12-Fix
FlatCAM fork patched for Python 3.12+, NumPy 2.x, and modern Linux distributions (Ubuntu 24.04+, Linux Mint 22+).
## What was fixed & changed in this fork:

This repository contains critical compatibility patches to run FlatCAM on modern Linux systems with **Python 3.12+** and **NumPy 2.x**, bypassing deep architectural deprecations from the original source.

### Key Changes:
* **Python 3.12 Import Engine Fix:** Replaced the completely removed `importlib` legacy methods (`find_module` and `load_module`) with modern dynamic plugin loading architecture (`find_spec`, `module_from_spec`, and `exec_module`) inside `tclCommands` and `appTools`.
* **NumPy 2.x Compatibility:** Patched obsolete uppercase `np.Inf` constant references to the modern, standard lowercase `np.inf` across all geometry modules.
* **Modern VisPy & OpenGL Patching:** Bypassed broken legacy custom marker patches in `FlatCAM.py` that were crashing due to internal refactoring (`_marker_dict` removal) in newer versions of the VisPy 3D rendering engine.
* **Missing Dependencies Added:** Explicitly isolated and declared modern requirements such as `qrcode`, `pyserial`, `svg.path`, `PyOpenGL`, and `PyQt5`.
