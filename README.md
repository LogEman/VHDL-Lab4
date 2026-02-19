| A | B | C | Y | MATCH |
| :---- | :---- | :---- | :---- | :---- |
| 0 | 0 | 0 | 1 | X |
| 0 | 0 | 1 | 1 | X |
| 0 | 1 | 0 | 1 | X |
| 0 | 1 | 1 | 0 | X |
| 1 | 0 | 0 | 0 | X |
| 1 | 0 | 1 | 1 | X |
| 1 | 1 | 0 | 1 | X |
| 1 | 1 | 1 | 0 | X |

For Y =A'B' + BC' + B'C  
**Inputs**: A, B, C  
**Output**: Y  
**Match**: Tested on hardware and matches table    

Running **Should** be as simple as downloading folder(as zip **using the giant green code button**), extracting, and running "lab4.xpr" (Vivado Project File). Code can be seen directly in .srcs

## Design Sources Code
**Path**: lab4_github/lab4.srcs/sources_1/new/lab_4.vhd

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity lab_4 is
    Port ( A : in STD_LOGIC;
           B : in STD_LOGIC;
           C : in STD_LOGIC;
           Y : out STD_LOGIC);
end lab_4;

architecture Behavioral of lab_4 is

begin
    Y <= ((NOT A) AND (NOT B)) OR ((B) AND (NOT C)) OR ((NOT B) AND (C));

end Behavioral;
```

## Constraints Code
**Path**: lab4_github/lab4.srcs/constrs_1/new/lab_4.xdc

```tcl
set_property PACKAGE_PIN V17 [get_ports {A}]				
	set_property IOSTANDARD LVCMOS33 [get_ports {A}]
set_property PACKAGE_PIN V16 [get_ports {B}]				
set_property IOSTANDARD LVCMOS33 [get_ports {B}]
set_property PACKAGE_PIN W16 [get_ports {C}]				
set_property IOSTANDARD LVCMOS33 [get_ports {C}]

set_property PACKAGE_PIN U16 [get_ports {Y}]				
set_property IOSTANDARD LVCMOS33 [get_ports {Y}]
```