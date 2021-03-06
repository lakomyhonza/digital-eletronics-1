<<<<<<< HEAD
# Lab 2: YOUR_FIRSTNAME LASTNAMEE
=======
# Lab 2: Jan Lakomý
>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742

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
<<<<<<< HEAD
  | **11** |   0    |   0    |   0    |   1    |
=======
  | **11** |   0    |   0    |   0    |   0    |
>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742
  | **10** |   0    |   0    |   1    |   0    |
   

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

<<<<<<< HEAD
   ![Logic functions](images/vzorce.PNG)
=======
 ![CodeCogsEqn](https://user-images.githubusercontent.com/99681304/156056635-685423e0-441d-40d9-848e-48340f536305.svg)

>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **13**

```vhdl
<<<<<<< HEAD
    p_stimulus : process
=======
p_stimulus : process
>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
<<<<<<< HEAD
        s_b <= "BCD_OF_YOUR_SECOND_LAST_ID_DIGIT"; -- Such as "0101" if ID = xxxx56
        s_a <= "BCD_OF_YOUR_LAST_ID_DIGIT";        -- Such as "0110" if ID = xxxx56
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = 'WRITE_CORRECT_VALUE_HERE') and
                (s_B_equals_A  = 'WRITE_CORRECT_VALUE_HERE') and
                (s_B_less_A    = 'WRITE_CORRECT_VALUE_HERE'))
        -- If false, then report an error
        report "Input combination COMPLETE_THIS_TEXT FAILED" severity error;

=======
        s_b <= "0001"; 		-- Such as "0001" if ID = xxxx13
        s_a <= "0011";      -- Such as "0011" if ID = xxxx13
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0001, 0111 FAILED" severity error;

 		-- Second test case
        s_b <= "0011"; 		-- Such as "0011" if ID = xxxx31
        s_a <= "0001";      -- Such as "0001" if ID = xxxx31
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination 0011, 0001 FAILED" severity error;
        
         -- Third test case
        s_b <= "0011"; 		-- Such as "0011" if ID = xxxx33
        s_a <= "0011";      -- Such as "0011" if ID = xxxx33
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0011, 0011 FAILED" severity error;
>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742
        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

<<<<<<< HEAD
   ![your figure]()

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/...](https://www.edaplayground.com/...)
=======
   ![image](https://user-images.githubusercontent.com/99681304/156056978-e536140e-d00e-47de-b88f-5ee9f5efc59b.png)

3. Link to your public EDA Playground example:

   https://www.edaplayground.com/x/p35K
>>>>>>> 3ef80ab86d7abdb38a68190918ff460797b43742
