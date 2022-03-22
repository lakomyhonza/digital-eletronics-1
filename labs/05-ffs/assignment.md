# Lab 5: Jan Lakomý

### Flip-flops

1. Listing of VHDL architecture for T-type flip-flop. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture Behavioral of t_ff_rst is
    signal s_q : std_logic;
begin
    --------------------------------------------------------
    -- p_t_ff_rst:
    -- T type flip-flop with a high-active synchro reset,
    -- rising-edge clk.
    -- q(n+1) = t./q(n) + /t.q(n)
    -- q(n+1) =  q(n) if t = 0 (no change)
    -- q(n+1) = /q(n) if t = 1 (inversion)
    --------------------------------------------------------
    p_d_ff_rst : process(clk)
    begin
        if rising_edge(clk) then 
                if (rst = '1')then               
                    q <= '0';
                    q_bar <= '1';  
                    s_q <= '0';                              
                else
                    s_q <= ((not t) and s_q) or ( t and (not s_q));
                    q <= s_q;
                    q_bar <= not s_q;
                end if;
        end if;
    end process p_d_ff_rst;
end architecture Behavioral;
```

2. Screenshot with simulated time waveforms. Try to simulate both flip-flops in a single testbench with a maximum duration of 200 ns, including reset. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![image](https://user-images.githubusercontent.com/99763701/159455378-f333a770-aa3d-4d94-af59-411fcf49ce5f.png)

### Shift register

1. Image of the shift register `top` level schematic. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

  ![image](https://user-images.githubusercontent.com/99681304/159545255-84d8d6fa-a5d5-43b7-aba5-3ef7c2a3aa84.png)

