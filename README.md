# Formal Verification of fpga-font

I added the [top.sby](./top.sby) file. There's a dependency on [BRAM_8.list](./BRAM_8.list),
specfically [here, using `$readmemb`](https://github.com/gojimmypi/fpga-font/blob/643d9cb8f954ab9f4d33e45c896d8678dd4890da/font.v#L34) that I'm not sure how to specify in the `sby` file

There are some interesting observations in the [symbiyosys logfile](./top_prove/logfile.txt), 
even without assert/assume/cover. Such as:

* [top.v:92: identifier 'counter' is used before its declaration](https://github.com/gojimmypi/fpga-font/blob/643d9cb8f954ab9f4d33e45c896d8678dd4890da/top_prove/logfile.txt#L11)
* [vga_sync.v:122: expression size 11 truncated to fit in target size 10](https://github.com/gojimmypi/fpga-font/blob/643d9cb8f954ab9f4d33e45c896d8678dd4890da/top_prove/logfile.txt#L16)
* [input port 'waddr[8]' remains unconnected for this instance](https://github.com/gojimmypi/fpga-font/blob/643d9cb8f954ab9f4d33e45c896d8678dd4890da/top_prove/logfile.txt#L21)

This would seem to be quite valuable, even without yet defining the FV parameters! :)

