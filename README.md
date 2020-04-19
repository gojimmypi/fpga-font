# Formal Verification of fpga-font

I added the [top.sby](./top.sby) file. There's a dependency on [BRAM_8.list](./BRAM_8.list) that
I'm not sure how to specify.

There are some interesting observations in the [./top_prove/logfile.txt](symbiyosys logfile), 
even without assert/assume/cover.