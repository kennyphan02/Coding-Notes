### SSDS
- SSDs have blocks and pages 
- writing too often to a page will cause the ssd to wear out
- Flash chips store bits
- flash chips are organized into banks/planes which consist of large # of cells
- banks are accessed in 2 dif units: blocks and pages
- when a block is erased and programmed, it slowly accruses a little bit of extra charge. over time, charge builds up. cant differentiate between a 0 and a 1 
- SSD contains numer of flash chips. contains sram (nonpersistent memory). contains control logic to orchestrate device operation

### FTL
flash transition layer does the reads and writes on logical blocks and turns them into low-level read, erase and program commands on the physical blocks/pages.
FTL delivers good performance and high realiability