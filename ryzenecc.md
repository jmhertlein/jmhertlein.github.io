# An AMD Ryzen server with ECC memory

I built a new home server recently, with the following goals:

1. ECC memory
2. Cost efficient (though admittedly not cheap)
3. 8 sATA ports on the motherboard

This ended up being a "pick two" kind of scenario, though I eventually ended up with something I was happy with. The biggest problem was combining 1 and 3 ended up with just a handful of boards to choose from. 

The thing I was most concerned about beforehand was 1. Prior to the Ryzen processors, ECC was primarily used as a feature for Intel to do market segmentation, and was intended for the kinds of CPUs and boards where the normal customer was an enterprise buying tens or hundreds of servers, and they were fully loading them to where the cost of the chips and pretty much every other component was dwarfed by the cost of the hard drives and (to a lesser extent) RAM. It was just totally cost-ineffective for a homelabber to buy one of these machines just to throw a measly 16/32GB of ram and a few TBs of disk space at them (when they are priced for the kind of customer who is putting 750GB of RAM and ~200TB of storage in them.)

In a post-ryzen world, ECC becomes less of a pipe dream and more of an exercise in caution. With the standard Ryzen lineup, ECC support isn't advertised at all, and motherboards are cagey about saying whether ECC will be supported in your setup. ECC RAM itself is also kind of hard to come by on Amazon. 

I ended up with this lineup:

### Part List

* CPU: [Ryzen 9 5950X](https://www.amazon.com/dp/B0815Y8J9N?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=cb1ece1208b93d8d56687a75e64118fa&camp=1789&creative=9325)
* RAM: 4x [Kingston DDR4 ECC 32GB](https://www.amazon.com/dp/B09N9TQ3B3?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=e8de63d259d3af88b017708ee3854a02&camp=1789&creative=9325)
* Motherboard: [ASUS X570-Plus (Wi-Fi)](https://www.amazon.com/dp/B07SXF8GY3?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=f4f4e84fde928c4ba1eb4beb67e797b7&camp=1789&creative=9325)
* GPU: [MSI RTX 3060Ti](https://www.amazon.com/MSI-GeForce-RTX-3060-8GD6X/dp/B0BXFQZZW1/ref=sr_1_5?crid=3RH73637QZBRX&amp;keywords=rtx+3060ti&amp;qid=1681868003&amp;s=electronics&amp;sprefix=rtx+3060ti%252Celectronics%252C111&amp;sr=1-5&amp;ufe=app_do%253Aamzn1.fos.c3015c4a-46bb-44b9-81a4-dc28e6d374b3&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=13ab4156c7867399f7ea292651434e34&camp=1789&creative=9325)
* OS drive: [Samsung 990 PRO MZ-V9P2T0B/AM](https://www.amazon.com/dp/B0BHJJ9Y77?ref=ppx_yo2ov_dt_b_product_details&amp;th=1&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=f03eb99daddefc6e0f778056c30d2c7a&camp=1789&creative=9325)
* Bulk Storage: 4x [WD Red Pro 18TB](https://www.amazon.com/dp/B07YFGW736?ref=ppx_yo2ov_dt_b_product_details&amp;th=1&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=efe19392b90766261335b338c40dd761&camp=1789&creative=9325)
* Case: [Rosewill 4U 15-bay](https://www.amazon.com/dp/B01JBG0LW0?ref=ppx_yo2ov_dt_b_product_details&amp;th=1&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=ea79321194f645a23431065ba21ce34f&camp=1789&creative=9325)
* PSU: [EVGA 1000W](https://www.amazon.com/dp/B09J5FC6CC?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=bd20fd1d235c02c2c4c8e5f221d0590e&camp=1789&creative=9325)
* Cooler: [CoolerMaster 240mm Closed Loop](https://www.amazon.com/dp/B086BYYFG5?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=88d25230e900d0ad57571cbedbba9964&camp=1789&creative=9325)
* Rails: [Shelf rails](https://www.amazon.com/dp/B0060RUVBA?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=b3361c570df3eae518cd5248b37aa911&camp=1789&creative=9325)

### Some considerations to note:

* The X570-Plus does NOT boot without either integrated graphics on the CPU or a discrete GPU in the first PCIe slot. I had found some post on Reddit suggesting otherwise, but they were incorrect. So at least some kind of GPU is required.
* I picked the 3060Ti because it was right in the sweet spot of performance per dollar. If this were going to play video games I would have gone for a beefier card, but if the only difference a thousand dollars gets me is that stable diffusion will run like *maybe* 2x faster, well, that's a bit less compelling for me, especially since the 3060Ti is still 2-3x faster than the GTX 1080 I spend a grand on in 2017ish. Also GPU prices are still stupid right now and are further driven up by limited supply for the RTX 4000 series cards. 
* I just do shelf rails for these Rosewill cases. They make sliding rails for them but I won't even affiliate link to them because they are awful. I would put these on an IKEA shelf before I bothered with non-Dell rails again. 
* You don't need to connect the RGB cords on the cooler. I just picked this one because it was a 240mm closed-loop that was in-stock at a decent price. 
* I did not want to use an HBA if I could help it, hence the 8x sATA ports. I've done the whole "buy a dubiously sourced LSI card off amazon and then flash IT mode firmware on it" and I would rather just buy enough sATA ports to get me through to the next time intel or AMD decide to release an interesting processor line. 
* We're right on the cusp of DDR5 and Ryzen 7xxx processors. I decided to take advantage of the fact that the Ryzen 5xxx processors were actually in stock at a competitive price, and the fact that ECC DDR4 RAM actually exists (I couldn't find a single listing for DDR5 ECC RAM).

### Things I would consider changing if I did it over again:

* I might buy 2x [WD Gold 18TB](https://www.amazon.com/dp/B089S3CZ41?psc=1&amp;ref=ppx_yo2ov_dt_b_product_details&_encoding=UTF8&tag=joshdotcafe0e-20&linkCode=ur2&linkId=34c94616d2f0f7f96ef6608b24f27c3f&camp=1789&creative=9325) instead of two of the Reds above. Then I'd pair each Gold with a Red in my ZFS array. It'd make me feel better about the probability of two of the drives failing simultenously being lower - as-is I'm slightly nervous about how close the serial numbers of the drives I got are. But alas, this is why we have backups.
* I might go for a 1200W PSU just to future-proof if I ever wanted to upgrade the GPU. 
* The GPU, my God, is the length of an EATX motherboard. Thankfully the 4U Rosewill case is an EATX motherboard case (though has mounting holes for smaller boards too). But I ended up having to remount my CPU cooler to have the pump tubes out of the way to make room for the GPU, which was annoying because that's like half the screws in the entire build. I might go for a slightly different card with a shorter length. Even shaving off a few mm would've make it a lot easier to put the CPU cooler where I wanted it originally. 

### Software

* I opted for Debian stable (bullseye) with a kernel and ZFS from bullseye-backports.
* I set up the WD Reds as `zpool create mypool mirror drive1 drive2 mirror drive3 drive4`. So basically RAID10. 
* You need to remember to use `-o ashift=12` during `zpool create` with these drives. They use 4k blocks internally but for compatibility lie to software about it, which stymies zfs trying to probe for the right value.

### So how did it turn out?

Great. I will now spend the rest of this post talking about ECC.

```
# dmesg | grep edac
[    3.003246] EDAC MC0: Giving out device to module amd64_edac controller F19h_M20h: DEV 0000:00:18.3 (INTERRUPT)
[    3.003268] EDAC PCI0: Giving out device to module amd64_edac controller EDAC PCI controller: DEV 0000:00:18.0 (POLLED)
```

The edac module found ecc controllers. Good sign.

```
# dmidecode -t memory | grep Error
  Error Correction Type: Multi-bit ECC
  Error Information Handle: 0x0032
  Error Information Handle: 0x003A
  Error Information Handle: 0x003D
  Error Information Handle: 0x0040
  Error Information Handle: 0x0043
```

That "Error Correction Type: Multi-bit ECC" seems to be the most definitive indicator that ECC is on and working that I can tell.

edac-utils being able to probe ECC stats is also encouraging:

```
# edac-util --status
edac-util: EDAC drivers are loaded. 1 MC detected
```

```
# edac-util -vvv --report
mc0: 0 Uncorrected Errors with no DIMM info
mc0: 0 Corrected Errors with no DIMM info
mc0: csrow0: 0 Uncorrected Errors
mc0: csrow0: mc#0csrow#0channel#0: 0 Corrected Errors
mc0: csrow0: mc#0csrow#0channel#1: 0 Corrected Errors
mc0: csrow1: 0 Uncorrected Errors
mc0: csrow1: mc#0csrow#1channel#0: 0 Corrected Errors
mc0: csrow1: mc#0csrow#1channel#1: 0 Corrected Errors
mc0: csrow2: 0 Uncorrected Errors
mc0: csrow2: mc#0csrow#2channel#0: 0 Corrected Errors
mc0: csrow2: mc#0csrow#2channel#1: 0 Corrected Errors
mc0: csrow3: 0 Uncorrected Errors
mc0: csrow3: mc#0csrow#3channel#0: 0 Corrected Errors
mc0: csrow3: mc#0csrow#3channel#1: 0 Corrected Errors
edac-util: No errors to report.
```

I was thrilled to see all this panning out. It all matches what I see on my R515 that I *know* has working error correction. 
