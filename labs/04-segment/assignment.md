
# Lab 4: Jan Lakomý

### Seven-segment display decoder

1. Listing of VHDL stimulus process from testbench file (`tb_hex_7seg.vhd`) with asserts. Verify all input combinations. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
p_stimulus : process
   begin
       
       report "Stimulus process started" severity note;

        assert (s_seg = "0000001") -- 0
        report "Input combination 0000 FAILED" severity error;
        s_hex <= "0001"; wait for 50 ns;
        assert (s_seg = "1001111") -- 1
        report "Input combination 0001 FAILED" severity error;
        s_hex <= "0010"; wait for 50 ns;
        assert (s_seg = "0010010") -- 2
        report "Input combination 0010 FAILED" severity error;
        s_hex <= "0011"; wait for 50 ns;
        assert (s_seg = "0000110") -- 3
        report "Input combination 0011 FAILED" severity error; 
        s_hex <= "0100"; wait for 50 ns;
        assert (s_seg = "1001100") -- 4
        report "Input combination 0100 FAILED" severity error;
        s_hex <= "0101"; wait for 50 ns;
        assert (s_seg = "0100100") -- 5
        report "Input combination 0101 FAILED" severity error;
        s_hex <= "0110"; wait for 50 ns;
        assert (s_seg = "0100000") -- 6
        report "Input combination 0110 FAILED" severity error;
        s_hex <= "0111"; wait for 50 ns;
        assert (s_seg = "0001111") -- 7
        report "Input combination 0111 FAILED" severity error; 
        s_hex <= "1000"; wait for 50 ns;
        assert (s_seg = "0000000") -- 8
        report "Input combination 1000 FAILED" severity error; 
        s_hex <= "1001"; wait for 50 ns;
        assert (s_seg = "0000100") -- 9
        report "Input combination 1001 FAILED" severity error;
        s_hex <= "1010"; wait for 50 ns;
        assert (s_seg = "0001000") -- A
        report "Input combination 1010 FAILED" severity error; 
        s_hex <= "1011"; wait for 50 ns;
        assert (s_seg = "1100000") -- b
        report "Input combination 1011 FAILED" severity error; 
        s_hex <= "1100"; wait for 50 ns;
        assert (s_seg = "0110001") -- C
        report "Input combination 1100 FAILED" severity error; 
        s_hex <= "1101"; wait for 50 ns;
        assert (s_seg = "1000010") -- d
        report "Input combination 1101 FAILED" severity error; 
        s_hex <= "1110"; wait for 50 ns;
        assert (s_seg = "0110000") -- E
        report "Input combination 1110 FAILED" severity error;
        s_hex <= "1111"; wait for 50 ns;
        assert (s_seg = "0111000") -- F
        report "Input combination 1111 FAILED" severity error;

        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Screenshot with simulated time waveforms. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![image](https://user-images.githubusercontent.com/99681304/157415283-5b5f3b42-e11a-4edf-b7d6-ae8a1bb4ade3.png)

### LED(7:4) indicators

1. Listing of LEDs(7:4) part of VHDL architecture from source file `top.vhd`. Try to write logic functions as simple as possible. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   ```vhdl
   --------------------------------------------------------------------
   -- Experiments on your own: LED(7:4) indicators

   -- Turn LED(4) on if input value is equal to 0, ie "0000"
      LED(4) <= '1' when SW = "0000";

   -- Turn LED(5) on if input value is greater than "1001", ie 10, 11, 12, ...
      LED(5) <= '1' when SW > "1001";

   -- Turn LED(6) on if input value is odd, ie 1, 3, 5, ...
      LED(6) <= '1' when SW(0) = '1';

   -- Turn LED(7) on if input value is a power of two, ie 1, 2, 4, or 8
      LED(7) <= '1' when SW = "0001" or SW = "0010" or SW = "0100" or SW = "1000";
