Library ieee;
use ieee.std_logic_1164.all;
--------------------------------------------------------------------------------
entity ALUTEST is
end ALUTEST;
--------------------------------------------------------------------------------
architecture AR3000 of ALUTEST is 
component ALU
	port(A, B: in STD_LOGIC_VECTOR(7 downto 0);
         R: out STD_LOGIC_VECTOR(7 downto 0);
         C: in std_logic_vector (3 downto 0));
end component;
-- components
-----------------------------------------
  signal A : std_logic_vector(7 downto 0) := (others => '0');
  signal B : std_logic_vector(7 downto 0) := (others => '0');
  signal R : std_logic_vector(7 downto 0);
  signal C : std_logic_vector(3 downto 0):= (others => '0');
  
--signaling 
-----------------------------------------
begin
UUT : ALU port map (A => A, B => B, C => C, R => R);
process
	begin
       C <= "0001";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "0010";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "0011";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "0100";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "0110";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "0111";		wait for 50 ns;
       A <= "00000000"; wait for 10 ns; B <= "11111110"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "00110010"; wait for 10 ns;
       A <= "00110010"; wait for 10 ns; B <= "01001011"; wait for 10 ns;
       A <= "11001110"; wait for 10 ns; B <= "10110101"; wait for 10 ns;
       A <= "01100100"; wait for 10 ns; B <= "10011100"; wait for 10 ns;
       
       C <= "1000";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
       C <= "1001";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
       C <= "1010";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
       C <= "1011";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
       C <= "1100";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
       C <= "1101";		wait for 50 ns;
       A <= "11001101"; wait for 10 ns;
	   A <= "00110010"; wait for 10 ns; 
       A <= "11001101"; wait for 10 ns; 
       A <= "01010101"; wait for 10 ns; 
       
	end process;
end AR3000;
--------------------------------------------------------------------------------

