# Lab 7 - FFS

### Characteristic equations and tables for D, JK, T flip-flops

#### D-ff
Ta tabulka je asi špatně, moc ji nerozumím
   | **clk** | **d** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![rising](Images/eq_uparrow.png) | 0 | 0 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 0 | 1 | 0 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 0 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 1 | 0 |  |

#### JK-ff
   | **clk** | **j** | **k** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-: | :-- |
   | ![rising](Images/eq_uparrow.png) | 0 | 0 | 0 | 0 | No change |
   | ![rising](Images/eq_uparrow.png) | 0 | 0 | 1 | 1 | No change |
   | ![rising](Images/eq_uparrow.png) | 0 | 1 | 0 | 0 |  |
   | ![rising](Images/eq_uparrow.png) | 0 | 1 | 1 | 0 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 0 | 0 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 0 | 1 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 1 | 0 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 1 | 1 | 0 |  |
   
#### T-ff
   | **clk** | **t** | **q(n)** | **q(n+1)** | **Comments** |
   | :-: | :-: | :-: | :-: | :-- |
   | ![rising](Images/eq_uparrow.png) | 0 | 0 | 0 |  |
   | ![rising](Images/eq_uparrow.png) | 0 | 1 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 0 | 1 |  |
   | ![rising](Images/eq_uparrow.png) | 1 | 1 | 0 |  |


## D latch

### VHDL code listing of the proces p_d_latch

### Listing of VHDL reset and stimulus processes from the testbench tb_d_latch

### Screenshot of time waveforms

## Flip-flops

### VHDL code listing of the processes p_d_ff_arst, p_d_ff_rst, p_jk_ff_rst, p_t_ff_rst

### Listing of VHDL clock, reset and stimulus processes from the testbench

### Screenshot of time waveforms

## Shift register

### Image of the shift register







