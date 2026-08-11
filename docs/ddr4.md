---
layout: page
title: DDR4
parent: Documentation
nav_order: 5
---
# DDR4 

{: .note-title}
 > Note
 >
 > You will have to provide your own board files to use DDR4. See [getting started](/docs/getting-started).


## DDR4 parameters 
To use the tile memory manager, set the parameter below in your Perl script:

``` perl
#- ddr4 parameters
$param{'ddr4_flag'} = 1;   
```

### Vivado IP DRAM
```perl
$param{'vivado_ip_dram'} = 1;
```
Adds your provided DDR4 files to the project. 
See:
- `mosaic_2x2_ddr4_8cache_vivado.pl` and `mosaic_2x2_ddr4_pkt_vivado.pl` for an example WITH this param enabled.
- `mosaic_2x2_tile_mem_mgr_vivado.pl` for an example WITHOUT this param enabled. 


Optionally, you can also set:

``` perl
#- Yes, Tile memory manager
$param{'ddr_cache_lines'} = 8;
$param{'ddr_init_file'} = 'test_tile_nop.hex';
``` 
`ddr_init_file` allows you to provide hex file firmware for the tile memory manager. 

<div style="display: flex; justify-content: space-between;">
  <a href="{{ '/docs/existing-accelerators/sne' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-left-long"></i> Go back</a>
  <a href="{{ '/docs/boards' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-right-long"></i> Continue</a>
</div>
