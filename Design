Library ieee;
use ieee.std_logic_1164.all;
--------------------------------------------------------------------------------
entity FA is
  port (A, B, CIN : in STD_LOGIC;
        R, COUT : out STD_LOGIC);
end FA; -- 1 bit full adder declaration 
-----------------------------------------
architecture Ar1 of FA is
begin
  R <= (A XOR B) XOR CIN ;
  Cout <= (A AND B) OR (A AND CIN) OR (B AND CIN);
end Ar1; -- 1 bit full adder architecture 
--------------------------------------------------------------------------------
Library ieee;
use ieee.std_logic_1164.all;
-----------------------------------------
entity FA8 is
  port (A8, B8 : in STD_LOGIC_VECTOR(7 downto 0);
        CIN : in STD_LOGIC;
        R8 : out STD_LOGIC_VECTOR(7 downto 0);
        COUT, OverF: out STD_LOGIC);
end FA8; -- 8 bit full adder entity declaration
-----------------------------------------
architecture Ar2 of FA8 is -- 8 bit full adder architecture
  component FA
    port (A, B, CIN : in STD_LOGIC;
          R, COUT : out STD_LOGIC);
end component; -- components
-----------------------------------------
signal SIG : std_logic_vector(0 to 8);
signal RSIG: std_logic_vector(7 downto 0); --signals
-----------------------------------------
begin
  G: for b in 0 to 7 generate
          U0: FA port map (A=>A8(b), B=>B8(b), CIN=> SIG(b), R=>RSIG(b), COUT=>SIG(b+1));
end generate; -- Generating adders
-----------------------------------------
R8 <=     RSIG;
SIG(0) <=  CIN; 
COUT <= SIG(8); 
OverF<='1' when  A8(7)=B8(7) and not RSIG(7)=A8(7) else '0'; -- checking for overflow
end Ar2;
--------------------------------------------------------------------------------
library ieee;
use ieee.std_logic_1164.all;
entity IncrA is
  port( A: in std_logic_vector(7 downto 0);
        Ai1: out std_logic_vector(7 downto 0)
       );
end IncrA;
----------------------------------------- Increment A by 1
architecture Ar5 of IncrA is
  component FA8
    port (A8, B8 : in STD_LOGIC_VECTOR(7 downto 0);
        CIN : in STD_LOGIC;
        R8 : out STD_LOGIC_VECTOR(7 downto 0);
        COUT, OverF: out STD_LOGIC);
  end component;
begin
  U: FA8 port map(A8 => A, B8 => "00000001" ,CIN => '0', R8 => Ai1);
end Ar5;
---------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;

entity COMPLEMENT is
port(VI: in std_logic_vector(7 downto 0);
	 VO: out std_logic_vector(7 downto 0));
end COMPLEMENT;
----------------------------------------- COMPLEMET
architecture Ar4 of COMPLEMENT is
begin
VO <= not VI;
end Ar4;
---------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity COMPLEMENT2S is
port (VI2: in STD_LOGIC_VECTOR(7 downto 0);
      VO2 : out STD_LOGIC_VECTOR(7 downto 0));
end COMPLEMENT2S;
----------------------------------------- 2'sCOMPLEMET
architecture Ar6 of COMPLEMENT2S is
  component COMPLEMENT
  port(VI: in std_logic_vector(7 downto 0);
	   VO: out std_logic_vector(7 downto 0));
  end component;
  component IncrA
    port(A: in std_logic_vector(7 downto 0);
         Ai1: out std_logic_vector(7 downto 0));
  end component;
Signal temp : std_logic_vector(7 downto 0);
begin
  U1: COMPLEMENT port map(VI => VI2, VO => temp);
  U2: IncrA port map( A => temp, Ai1 => VO2);
end Ar6;
---------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity AMinusB is
port (MA8,MB8 : in STD_LOGIC_VECTOR(7 downto 0);
      MR8 : out STD_LOGIC_VECTOR(7 downto 0);
      MCOUT: out STD_LOGIC);
end AMinusB;
----------------------------------------- A MINUS B
architecture Ar7 of AMinusB is
  component COMPLEMENT2S
	port (VI2: in STD_LOGIC_VECTOR(7 downto 0);
      	  VO2 : out STD_LOGIC_VECTOR(7 downto 0));
  end component;
  component FA8
    port (A8, B8 : in STD_LOGIC_VECTOR(7 downto 0);
        CIN : in STD_LOGIC;
        R8 : out STD_LOGIC_VECTOR(7 downto 0);
        COUT, OverF: out STD_LOGIC);
  end component;
Signal temp2 : std_logic_vector(7 downto 0);
begin
  U1: COMPLEMENT2S port map(VI2 => MB8, VO2 => temp2);
  U2:FA8 port map(A8 => MA8, B8 => temp2, CIN => '0', R8 => MR8, COUT => MCOUT);
end Ar7;
---------------------------------------------------------------------------------
library ieee;
use ieee.std_logic_1164.all;
entity DecA is
  port( A: in std_logic_vector(7 downto 0);
        Ad1: out std_logic_vector(7 downto 0);
        DCOUT: out std_logic);
end DecA;
----------------------------------------- Dncrement A by 1
architecture Ar9 of DecA is
  component AMinusB
    port (MA8,MB8 : in STD_LOGIC_VECTOR(7 downto 0);
          MR8 : out STD_LOGIC_VECTOR(7 downto 0);
          MCOUT: out STD_LOGIC);
  end component;
begin
  U: AMinusB port map(MA8 => A, MB8 => "00000001", MR8 => Ad1, MCOUT => DCOUT );
end Ar9;
---------------------------------------------------------------------------------
library ieee;
use ieee.std_logic_1164.all;
entity max is
port ( A, B: in STD_LOGIC_VECTOR(7 downto 0);
	   Max : out STD_LOGIC_VECTOR(7 downto 0));
end max;
----------------------------------------- Max of A
architecture Ar10 of max is 
begin
 process(A,B)
 begin
  if ((A(7)='1') and (B(7)='0')) then
    Max <= B;
    elsif ((B(7)='1') and (A(7)='0')) then
      Max <= A;
    else
      if (A>B) then
        Max <= A;
        else
          Max <= B;
        end if;
        end if;
    end process;
end Ar10;	
---------------------------------------------------------------------------------
library ieee;
use ieee.std_logic_1164.all;
entity min is 
port ( A, B: in STD_LOGIC_VECTOR(7 downto 0);
	   Min : out STD_LOGIC_VECTOR(7 downto 0));
end min;
----------------------------------------- Min of A
architecture Ar11 of min is 
begin
 process(A,B)
 begin
  if ((A(7)='1') and (B(7)='0')) then
    Min <= A;

    elsif ((B(7)='1') and (A(7)='0')) then
      min <= B;

    else
      if (A<B) then
        min <= A;
        else
          min <= B;
        end if;
          end if;
    end process;
end Ar11;	
---------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity CRS is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end CRS;
----------------------------------------- Circular right shift of A
architecture ar12 of CRS is 
signal temp: std_logic;
begin 
  u: for i in 6 downto 0 generate
  k: An(i) <= A(i+1);
end generate;
  temp <= A(0);
  An(7) <= temp;
end ar12;					
---------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity CLS is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end CLS;
----------------------------------------- Circular left shift of A
architecture ar12 of CLS is 
signal temp: std_logic;
begin 
  u: for i in 7 downto 1 generate
  k: An(i) <= A(i-1);
end generate;
  temp <= A(7);
  An(0) <= temp;
end ar12;
--------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
library IEEE;
use IEEE.std_logic_1164.all;
entity RS is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end RS;
----------------------------------------- Right shift of A
architecture ar13 of RS is 
begin 
  u: for i in 6 downto 0 generate
  k: An(i) <= A(i+1);
end generate;
  An(7) <= '0';
end ar13;
--------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity LS is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end LS;
----------------------------------------- Left shift of A
architecture ar14 of LS is 
begin 
  u: for i in 7 downto 1 generate
  k: An(i) <= A(i-1);
end generate;
  An(0) <= '0';
end ar14;
--------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity RSR is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end RSR;
----------------------------------------- Right shift R of A
architecture ar15 of RSR is 
begin 
u: for i in 6 downto 0 generate
k: An(i) <= A(i+1);
end generate;
An(7) <= An(6);
end ar15;
--------------------------------------------------------------------------------
library IEEE;
use IEEE.std_logic_1164.all;
entity LSR is 
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end LSR;
----------------------------------------- Left shift R of A
architecture ar15 of LSR is 
begin 
u: for i in 7 downto 1 generate
k: An(i) <= A(i-1);
end generate;
An(0) <= An(1);
end ar15;
--------------------------------------------------------------------------------
library IEEE;
use IEEE.STD_LOGIC_1164.all;

entity ALU is
	port(A, B: in STD_LOGIC_VECTOR(7 downto 0);
         R: out STD_LOGIC_VECTOR(7 downto 0);
         C: in std_logic_vector (3 downto 0));
end ALU;
----------------------------------------- 
architecture AR100 of ALU is
component FA8 --1
  port (A8, B8 : in STD_LOGIC_VECTOR(7 downto 0);
        CIN : in STD_LOGIC;
        R8 : out STD_LOGIC_VECTOR(7 downto 0);
        COUT, OverF: out STD_LOGIC);
end component;
----------------------------------------- 
component IncrA --2
  port( A: in std_logic_vector(7 downto 0);
        Ai1: out std_logic_vector(7 downto 0)
       );
end component;
----------------------------------------- 
component aminusb --3
port (MA8,MB8 : in STD_LOGIC_VECTOR(7 downto 0);
      MR8 : out STD_LOGIC_VECTOR(7 downto 0);
      MCOUT: out STD_LOGIC);
end component;
----------------------------------------- 
component deca --4
  port( A: in std_logic_vector(7 downto 0);
        Ad1: out std_logic_vector(7 downto 0);
        DCOUT: out std_logic);
end component;
----------------------------------------- 
component max --5
port ( A, B: in STD_LOGIC_VECTOR(7 downto 0);
	   Max : out STD_LOGIC_VECTOR(7 downto 0));
end component;
----------------------------------------- 
component min --6
port ( A, B: in STD_LOGIC_VECTOR(7 downto 0);
	   Min : out STD_LOGIC_VECTOR(7 downto 0));
end component;
----------------------------------------- 
component CRS --7
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
component CLS --8
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
component RS --9
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
component LS --10
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
component RSR --11
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
component LSR --12
port ( A : in std_logic_vector(7 downto 0);
       An: out std_logic_vector(7 downto 0));
end component;
----------------------------------------- 
signal R0,R1,R2,R3,R4,R5,R6,R7,R8,R9,R10,R11: std_logic_vector(7 downto 0);

begin 
 
  U0: FA8 port map (A8 => A,B8 => B,CIN => '0',R8 => R0); 

  U1: IncrA port map ( A => A, Ai1 => R1);

  U2: AminusB port map (MA8 => A, MB8 => B, MR8 => R2);

  U3: DecA port map ( A => A, Ad1 => R3); 

  U4: Max  port map ( A => A, B => B, Max =>R4);

  U5 : Min port map ( A => A, B => B, Min =>R5);

  U6 : CRS port map ( A => A, An => R6);

  U7 : CLS port map ( A => A, An => R7);

  U8 : RS  port map ( A => A, An => R8);

  U9 : LS port map ( A => A, An => R9);

  U10 :RSR port map ( A => A, An => R10);

  U11 :LSR port map ( A => A, An => R11);
  
  with C select R <=
	 
  R0 when "0001",

  R1 when "0010",

  R2 when "0011",

  R3 when "0100",

  R4 when "0111",

  R5 when "0110",

  R6 when "1000", 

  R7 when "1001",

  R8 when "1010",

  R9 when "1011",

  R10 when "1100",

  R11 when "1101",
  
  (others => '0') when others;
  
end AR100;
--------------------------------------------------------------------------------
