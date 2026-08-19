---
layout: page
title: RegIO
parent: Documentation
nav_order: 8
---
# RegIO
*By: Angelos Ioannou*

## Python Venv
Run the script below. Here's what it does:
1. Creates & activates a virtual environment.
2. Installs the needed python modules. 

``` bash
source python_modules.sh
```

## Setup

Run the next script from the main directory where you want to build your regio top file.


```bash
./custom_scripts/build_regBlock_top.py <num_of_rows> <num_of_columns>  >  regBlock_top.yaml
```

In case your execution rights for this script are not set right out of the box you might need:

``` bash
chmod u+x custom_scripts/build_regBlock_top.py
```

The output is based on `./custom_scripts/regBlock_top_yaml_header.txt` and adds to it the register space description.

If needed, alter the start of the `regBlock_top_yaml_header.txt` file to match your PCI system. 

Next, run 

```bash
make elaborate
```

This will create your `regBlock_top_ir.yaml` needed by the regio tool, based off the `regBlock_top.yaml`.

## Update your firmware filenames
1. Grab the hex files for your Picos from MoSAIC 
  - For the basic MoSAIC 2x2, they should be in `src/Tile.HDL/picorv32_tile/firmware`
  - Generated hex files will be found in `tools/picorv_c/<your c directory>`
2. Update the `firmware_filenames.py` to match the appropriate firmware for each pico. 

## Setting the system!

We are now ready to run:

``` bash
sudo python3 set_system.py
```
**Important:** This script starts with creating an object that is used to manipulate the PCI connection. You may need to edit the line that created this *rio.RegIO* based object to match your PCI mapping!

## Reading back

Let's read back the memory. 

``` bash
sudo python3 read_mem.py 
```

The script *mosaic_setup.sh* executes both aforementioned python scripts and filters the output to two log files (*read_mem_counters.log* for counters and *read_mem.log* for data). Run:

``` bash
./mosaic_setup.sh <num_of_rows> <num_of_cols>
```
to use. 

For more notes, see RegIO's `README.md`.

<div style="display: flex; justify-content: space-between;">
  <a href="{{ '/docs/open-nic-shell' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-left-long"></i> Go back</a>
  <a href="{{ '/research' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-right-long"></i> Continue</a>
</div>
