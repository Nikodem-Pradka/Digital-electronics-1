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

```vhdl
    p_d_latch : process (d, arst, en)
    begin
        if(arst = '1') then
            q     <= '0';
            q_bar <= '1';
            
        elsif (en =  '1') then
            q     <= d;
            q_bar <= not d;    
            
        end if;
    end process p_d_latch;
```

### Listing of VHDL reset and stimulus processes from the testbench tb_d_latch
```vhdl
    p_reset_gen : process
    begin
        s_arst <= '0';
        wait for 38 ns;
        
        -- Reset activated
        s_arst <= '1';
        wait for 53 ns;

        -- Reset deactivated
        s_arst <= '0';
        
        wait for 300 ns;
        s_arst <= '1';

        wait;
    end process p_reset_gen;
    --------------------------------------------------------------------
    -- Data generation process
    --------------------------------------------------------------------
    --- WRITE YOUR CODE HERE
        p_stimulus : process
    begin
        report "Stimulus process started" severity note;
        s_d <= '0';
        s_en <= '0';
        
        assert(s_q = '0')
        report "s_q = 0 " severity error;
        
        --d sekv
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        --/d sekv
        
        assert(s_q = '0' and s_q_bar = '1')
        report "s_q = '0' and s_q_bar = '1'" severity error;
        
        s_en <= '1';
        
        --d sekv
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_en <= '0';       
        wait for 200 ns;
        s_d <= '0';
        --/d sekv
        
        --d sekv
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        --/d sekv
        
        --d sekv
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        wait for 10 ns;
        s_d <= '1';
        wait for 10 ns;
        s_d <= '0';
        --/d sekv
        

        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```
### Screenshot of time waveforms

## Flip-flops

### VHDL code listing of the processes p_d_ff_arst, p_d_ff_rst, p_jk_ff_rst, p_t_ff_rst
#### d_ff_arst
```vhdl

```
#### d_ff_rst
```vhdl

```
#### jk_ff_rst
```vhdl

```
#### t_ff_rst
```vhdl

```

### Listing of VHDL clock, reset and stimulus processes from the testbench
```vhdl

```
### Screenshot of time waveforms

## Shift register

### Image of the shift register







