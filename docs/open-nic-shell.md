---
layout: page
title: OpenNIC Shell
parent: Documentation
nav_order: 7
---
# OpenNIC Shell

Guide on using the OpenNIC Shell for interacting with the MoSAIC system.

## Packing MoSAIC IP

1. Open design sources In the Vivado project.
2. Set `mosaic` (inside `tb_mosaic`) as the top level file.
3. Go to Tools → Create and Package new IP.
4. Set the name as USS and the version as 2.0.  

## Putting the goodies inside open-nic-shell-lbnl

1. In a new directory, [clone this repo](https://github.com/lbnlmosaic/open-nic-shell-lbnl)
2. Inside, `mkdir newly_created_IP`. Copy these files from MoSAIC into this directory:

```
open-nic-shell-lbnl/
├─ newly_created_IP/
│  ├─ component.xml/
│  ├─ build/
│  ├─ src/
│  ├─ xgui/
├
```

## Setting up for implementation

### Building the project

In `script/`, run:

```bash
vivado -mode batch -source build.tcl -tclargs -board au250 -jobs 8
```

Pick one of two options below. Both do the same thing, one is through the GUI and the other is through the helper scripts (see `helper_notes/building_new_vivado_project_README.md`)

## Generating the IP

### Option 1: helper scripts

In the tcl console, run:

```bash
source ~/open-nic-shell-lbnl/mosaic_ip/helper_scripts/all_at_once_2022_2.tcl
```

If you're brave, uncomment the last two lines to generate the bitstream.

{: .warning-title }
> Warning
> 
> If you are NOT using the memory controller, comment out lines 19-20

``` tcl
# adding memory controller
source $project_path/../../../helper_scripts/memory_ctrl_etc_2022_2.tcl
update_compile_order -fileset sources_1
```

### Option 2: GUI

Work in Progress

<div style="display: flex; justify-content: space-between;">
  <a href="{{ '/docs/boards' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-left-long"></i> Go back</a>
  <a href="{{ '/docs/reg-io' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-right-long"></i> Continue</a>
</div>
