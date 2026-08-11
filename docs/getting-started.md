---
layout: page
title: Getting Started
parent: Documentation
permalink: /docs/getting-started
nav_order: 1
---
# Getting Started
## Pulling submodules 
In the project directory, run 

```
source pull_submodules.sh
```

You should notice a new directory `externals` with a new submodule open-nic-shell-lbnl.

If you need DRAM support, you'll need to provide your own board files. Clone your repo into `externals` and name it `xilinx_dram_model`.


## Verifying Proper Installation
1. Go to `/tools/generate`
2. Execute `perl mosaic_2x2_vivado.pl` in the command line.

If successful, you should see `INFO: Finish without errors`.

{: .note-title}
> Note
>
> If you are not using our servers, you may need to reset the tools path as specified by the `$MosaicGlobal` param in `tools/generate/gen_mosaic.pm`. 
>
> You may also need to change the path of the tools as indicated by line 25 in `vivado/launch_sim.sh`.


## Using Vivado

### 1. Access a remote graphical desktop. 
If using our servers. 
[Guide here.](https://lbnlcomputerarch.github.io/docs/) 
### 2. Run the Commands
In your remote desktop, run:
```
source /tools/source-vitis.sh 2022.2
```
If the above was successful, run:
```
vivado
```

### 3. Top level file
Open `Simulation sources → sim_1`. If `tb_mosaic.sv` is not the top level file, set it as the top level file (right click → set as top)


<div style="display: flex; justify-content: space-between;">
  <a href="{{ '/docs/dependencies' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-left-long"></i> Go back</a>
  <a href="{{ '/docs/using-mosaic' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-right-long"></i> Continue</a>
</div>
