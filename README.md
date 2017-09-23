Custom LEDE Patch For TL-WR1043ND (With Working Fast Path)
==========================================================

Dependencies
------------

* LEDE BuildRoot
* LEDE BuildRoot Dependencies
* Java Runtime

How to use
----------

* Install all the development packages required for LEDE BuildRoot
* Install Java Runtime
* Clone the LEDE Repository

```shell
git clone -b lede-17.01 https://github.com/lede-project/source.git lede
```

Clone this Repository and copy into the LEDE repository

```shell
git clone -b lede-17.01 https://github.com/gwlim/mips24k-lede-patch.git temp; mv temp/* lede/; rm -rf temp
```

Change directory into the LEDE Repository

```shell
cd lede
```

Run the script

```shell
./patch_LEDE.sh
```

> `make menuconfig` Default Target Profile is TP-LINK TL-WR1043ND (all the packages and config is inside)

If you want to enable Fast Path select all the fast path modules in

> Kernel Modules > Network Support > 

Select

> * kmod-fast-classifier

```shell
make menuconfig
```

Save and make

```shell
make V=s
```

FAQ
---

Cannot install packages with Kernel Dependencies?

Use `--nodeps` in opkg.


Where can I download the firmware for my Router?

https://github.com/gwlim/Fast-Path-LEDE-OpenWRT

The binaries in the link above will contain firmware build with this patchset
