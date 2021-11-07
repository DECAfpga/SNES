# SNES - DECA port 

DECA Top level for SNES by Somhic (07/11/21) adapted from Neptuno port https://github.com/neptuno-fpga/SNES  by DistWave.

**(THIS PORT REQUIRES AN SDRAM MODULE WITH SEPARATED DQMH/L SIGNALS - 3 pins old MiSTer memory modules should work)**

**Features:**

* ~~HDMI video output~~ (need to solve synchronism problems)
* VGA 444 video output is available through GPIO (see pinout below). 
* Line out (3.5 jack green connector) and HDMI audio output
* PWM audio is available through GPIO (see pinout below)
* Joystick available through GPIO  (see pinout below).  **Joystick power pin must be 2.5 V**
  * **DANGER: Connecting power pin above 2.6 V may damage the FPGA**
  * This core is prepared for Megadrive 6 button gamepads as it outputs a permanent high level on pin 7 of DB9

**Additional hardware required**:

- SDRAM module. Tested with a dual memory module v1.3 with 3 pins ([see connections](https://github.com/SoCFPGA-learning/DECA/tree/main/Projects/sdram_mister_deca) + [3pins](https://github.com/DECAfpga/DECA_board/blob/main/Sdram_mister_deca/README_3pins.md))
- PS/2 Keyboard connected to GPIO  (see pinout below)

**Versions**:

- current version: 0.24
- see changelog in top level file DECA/snes_deca.sv

**Compiling:**

* Load project  in DECA/snes_deca.qpf
* sof/svf files already included in DECA/output_files/

**Pinout connections:**

![pinout_deca](pinout_deca.png)

Audio L/R pins have changed due to using 3 pins memory modules (check location at snes_deca.qsf file).

Mouse pinout is not used in this core. 

**Others:**

* Button KEY0 is a reset button

### STATUS

* Working fine

* ~~HDMI video outputs special resolution, so does not work in all monitors.~~



Follows original README from NeptUNO.





# SNES NeptUNO

Port from MiST to NeptUNO by DistWave

# Controles del teclado

..* Esc / F12: Oculta / muestra el menú
..* Cursores: Control en el menú
..* Intro: selecciona la opción
..* Bloq Desp: Cambio VGA 31.5 kHz / RGB 15 kHz

## Jugador 1

..* Mando: Cursores
..* Start: 8
..* Select: 9
..* A: .
..* B: ,
..* X: l
..* Y: k
..* L: i
..* R: o

## Jugador 2

..* Mando: W, A, S/X, D
..* Start: 1
..* Select: 2
..* A: n
..* B: b
..* X: h
..* Y: g
..* L: t
..* R: y