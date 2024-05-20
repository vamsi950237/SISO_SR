# SISO_SR
# The shift register, which allows serial input (one bit after the other through a single data line) and produces a serial output is known as a Serial-In Serial-Out shift register. Since there is only one output, the data leaves the shift register one bit at a time in a serial pattern, thus the name Serial-In Serial-Out Shift Register. The logic circuit given below shows a serial-in serial-out shift register. The circuit consists of four D flip-flops which are connected in a serial manner. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip-flop. 
![image](https://github.com/RESMIRNAIR/SISO_SR/assets/154305926/778bf654-f276-4c56-ab9b-33de0e21eac9)
# Program
~~~
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity sipo is
 Port (clk,rst,s_in:in std_logic; 
       p_out: out std_logic_vector(3 downto 0));
end sipo;

architecture Behavioral of sipo is
signal temp_reg: std_logic_vector(3 downto 0):=(others=>'0');
begin
process(clk,rst)
begin
if rst='1' then 
   temp_reg<=(others=>'0');
elsif rising_edge(clk) then 

          temp_reg <= temp_reg(2 downto 0) & s_in;

      end if;
end process;
end Behavioral;
~~~
### Output:
![Screenshot 2024-05-19 175533](https://github.com/Shaiksushma123/SISO_SR/assets/159005642/01f2fd12-52e6-4f26-86a6-3631264e6fed)
