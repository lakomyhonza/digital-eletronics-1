# Lab 2: Jan Lakomý

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

  |B1B0/A1A0| **00** | **01** | **11** | **10** |
  | :-:    | :-:    | :-:    | :-:    | :-:    |
  | **00** |   0    |   0    |   0    |   0    |
  | **01** |   1    |   0    |   0    |   0    |
  | **11** |   1    |   1    |   0    |   1    |
  | **10** |   1    |   1    |   0    |   0    |
  
   Less than:
   
  |B1B0/A1A0| **00** | **01** | **11** | **10** |
  | :-:    | :-:    | :-:    | :-:    | :-:    |
  | **00** |   0    |   1    |   1    |   1    |
  | **01** |   0    |   0    |   1    |   1    |
  | **11** |   0    |   0    |   0    |   0    |
  | **10** |   0    |   0    |   1    |   0    |
   

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

 

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **13**

```vhdl
p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "0001"; 		-- Such as "0001" if ID = xxxx13
        s_a <= "0011";      -- Such as "0011" if ID = xxxx13
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0000, 0111 FAILED" severity error;

 		-- Second test case
        s_b <= "0011"; 		-- Such as "0011" if ID = xxxx31
        s_a <= "0001";      -- Such as "0001" if ID = xxxx31
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination 0000, 0111 FAILED" severity error;
        
         -- Third test case
        s_b <= "0011"; 		-- Such as "0011" if ID = xxxx33
        s_a <= "0011";      -- Such as "0011" if ID = xxxx33
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0000, 0111 FAILED" severity error;
        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure]()

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/...](https://www.edaplayground.com/...)
