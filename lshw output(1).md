       resources: irq:42 memory:fca00000-fca03fff memory:fca04000-fca040ff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:0e:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc900000-fc903fff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:11:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc800000-fc803fff
  *-storage
       description: Non-Volatile memory controller
       product: WD Black SN750 / PC SN730 NVMe SSD
       vendor: Sandisk Corp
       physical id: 0
       bus info: pci@0000:12:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc700000-fc703fff memory:fc704000-fc7040ff
  *-sata
       description: SATA controller
       product: FCH SATA Controller [AHCI mode]
       vendor: Advanced Micro Devices, Inc. [AMD]
       physical id: 0.2
       bus info: pci@0000:14:00.2
       version: 51
       width: 32 bits
       clock: 33MHz
       capabilities: sata ahci_1.0 bus_master cap_list
       configuration: driver=ahci latency=0
       resources: irq:60 memory:fce08000-fce08fff
WARNING: output may be incomplete or inaccurate, you should run this program as super-user.
bkaler@host4:~$ lshw
WARNING: you should run this program as super-user.
host4                       
    description: Computer
    width: 64 bits
    capabilities: smp vsyscall32
  *-core
       description: Motherboard
       physical id: 0
     *-memory
          description: System memory
          physical id: 0
          size: 16GiB
     *-cpu
          product: AMD Ryzen 5 1600X Six-Core Processor
          vendor: Advanced Micro Devices [AMD]
          physical id: 1
          bus info: cpu@0
          size: 2957MHz
          capacity: 3600MHz
          width: 64 bits
          capabilities: fpu fpu_exception wp vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt pdpe1gb rdtscp x86-64 constant_tsc rep_good nopl nonstop_tsc cpuid extd_apicid aperfmperf rapl pni pclmulqdq monitor ssse3 fma cx16 sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand lahf_lm cmp_legacy svm extapic cr8_legacy abm sse4a misalignsse 3dnowprefetch osvw skinit wdt tce topoext perfctr_core perfctr_nb bpext perfctr_llc mwaitx cpb hw_pstate ssbd ibpb vmmcall fsgsbase bmi1 avx2 smep bmi2 rdseed adx smap clflushopt sha_ni xsaveopt xsavec xgetbv1 clzero irperf xsaveerptr arat npt lbrv svm_lock nrip_save tsc_scale vmcb_clean flushbyasid decodeassists pausefilter pfthreshold avic v_vmsave_vmload vgif overflow_recov succor smca sme sev cpufreq
     *-pci:0
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Root Complex
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 100
          bus info: pci@0000:00:00.0
          version: 00
          width: 32 bits
          clock: 33MHz
        *-generic UNCLAIMED
             description: IOMMU
             product: Family 17h (Models 00h-0fh) I/O Memory Management Unit
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 0.2
             bus info: pci@0000:00:00.2
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: cap_list
             configuration: latency=0
        *-pci:0
             description: PCI bridge
             product: Family 17h (Models 00h-0fh) PCIe GPP Bridge
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 1.1
             bus info: pci@0000:00:01.1
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: pci normal_decode bus_master cap_list
             configuration: driver=pcieport
             resources: irq:26 memory:fcf00000-fcffffff
           *-storage
                description: Non-Volatile memory controller
                product: XG6 NVMe SSD Controller
                vendor: Toshiba Corporation
                physical id: 0
                bus info: pci@0000:01:00.0
                version: 00
                width: 64 bits
                clock: 33MHz
                capabilities: storage nvm_express bus_master cap_list
                configuration: driver=nvme latency=0
                resources: irq:52 memory:fcf00000-fcf03fff
        *-pci:1
             description: PCI bridge
             product: Family 17h (Models 00h-0fh) PCIe GPP Bridge
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 1.2
             bus info: pci@0000:00:01.2
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: pci normal_decode bus_master cap_list
             configuration: driver=pcieport
             resources: irq:27 ioport:b000(size=20480) memory:c0000000-c0afffff
           *-usb
                description: USB controller
                product: Advanced Micro Devices, Inc. [AMD]
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0
                bus info: pci@0000:02:00.0
                version: 00
                width: 64 bits
                clock: 33MHz
                capabilities: xhci bus_master cap_list
                configuration: driver=xhci_hcd latency=0
                resources: irq:228 memory:c0aa0000-c0aa7fff
           *-sata
                description: SATA controller
                product: Advanced Micro Devices, Inc. [AMD]
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.1
                bus info: pci@0000:02:00.1
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: sata ahci_1.0 bus_master cap_list rom
                configuration: driver=ahci latency=0
                resources: irq:55 memory:c0a80000-c0a9ffff memory:c0a00000-c0a7ffff
           *-pci
                description: PCI bridge
                product: Advanced Micro Devices, Inc. [AMD]
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.2
                bus info: pci@0000:02:00.2
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: pci normal_decode bus_master cap_list
                configuration: driver=pcieport
                resources: irq:33 ioport:b000(size=20480) memory:c0000000-c09fffff
              *-pci:0
                   description: PCI bridge
                   product: Advanced Micro Devices, Inc. [AMD]
                   vendor: Advanced Micro Devices, Inc. [AMD]
                   physical id: 0
                   bus info: pci@0000:03:00.0
                   version: 00
                   width: 32 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: irq:35 ioport:f000(size=4096) memory:c0000000-c05fffff
                 *-sas
                      description: Serial Attached SCSI controller
                      product: SAS2008 PCI-Express Fusion-MPT SAS-2 [Falcon]
                      vendor: Broadcom / LSI
                      physical id: 0
                      bus info: pci@0000:04:00.0
                      version: 03
                      width: 64 bits
                      clock: 33MHz
                      capabilities: sas bus_master cap_list rom
                      configuration: driver=mpt3sas latency=0
                      resources: irq:34 ioport:f000(size=256) memory:c0440000-c0443fff memory:c0000000-c003ffff memory:c0444000-c0483fff memory:c0040000-c043ffff
              *-pci:1
                   description: PCI bridge
                   product: Advanced Micro Devices, Inc. [AMD]
                   vendor: Advanced Micro Devices, Inc. [AMD]
                   physical id: 1
                   bus info: pci@0000:03:01.0
                   version: 00
                   width: 32 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: irq:37 ioport:b000(size=8192) memory:c0600000-c07fffff
                 *-pci
                      description: PCI bridge
                      product: PES12N3A 12-lane 3-Port PCI Express Switch
                      vendor: Microsemi / PMC / IDT
                      physical id: 0
                      bus info: pci@0000:05:00.0
                      version: 0e
                      width: 32 bits
                      clock: 33MHz
                      capabilities: pci normal_decode bus_master cap_list
                      resources: ioport:b000(size=8192) memory:c0600000-c07fffff
                    *-pci:0
                         description: PCI bridge
                         product: PES12N3A 12-lane 3-Port PCI Express Switch
                         vendor: Microsemi / PMC / IDT
                         physical id: 2
                         bus info: pci@0000:06:02.0
                         version: 0e
                         width: 32 bits
                         clock: 33MHz
                         capabilities: pci normal_decode bus_master cap_list
                         configuration: driver=pcieport
                         resources: irq:40 ioport:c000(size=4096) memory:c0600000-c06fffff
                       *-network:0
                            description: Ethernet interface
                            product: 82571EB/82571GB Gigabit Ethernet Controller (Copper)
                            vendor: Intel Corporation
                            physical id: 0
                            bus info: pci@0000:07:00.0
                            logical name: enp7s0f0
                            version: 06
                            serial: 00:15:17:df:ab:25
                            capacity: 1Gbit/s
                            width: 32 bits
                            clock: 33MHz
                            capabilities: bus_master cap_list rom ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
                            configuration: autonegotiation=on broadcast=yes driver=e1000e driverversion=5.15.104-1-pve firmware=5.10-2 latency=0 link=no multicast=yes port=twisted pair
                            resources: irq:61 memory:c0600000-c061ffff memory:c0620000-c063ffff ioport:c020(size=32)
                       *-network:1
                            description: Ethernet interface
                            product: 82571EB/82571GB Gigabit Ethernet Controller (Copper)
                            vendor: Intel Corporation
                            physical id: 0.1
                            bus info: pci@0000:07:00.1
                            logical name: enp7s0f1
                            version: 06
                            serial: 00:15:17:df:ab:24
                            size: 1Gbit/s
                            capacity: 1Gbit/s
                            width: 32 bits
                            clock: 33MHz
                            capabilities: bus_master cap_list rom ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
                            configuration: autonegotiation=on broadcast=yes driver=e1000e driverversion=5.15.104-1-pve duplex=full firmware=5.10-2 ip=172.16.0.125 latency=0 link=yes multicast=yes port=twisted pair speed=1Gbit/s
                            resources: irq:223 memory:c0640000-c065ffff memory:c0660000-c067ffff ioport:c000(size=32)
                    *-pci:1
                         description: PCI bridge
                         product: PES12N3A 12-lane 3-Port PCI Express Switch
                         vendor: Microsemi / PMC / IDT
                         physical id: 4
                         bus info: pci@0000:06:04.0
                         version: 0e
                         width: 32 bits
                         clock: 33MHz
                         capabilities: pci normal_decode bus_master cap_list
                         configuration: driver=pcieport
                         resources: irq:41 ioport:b000(size=4096) memory:c0700000-c07fffff
                       *-network:0
                            description: Ethernet interface
                            product: 82571EB/82571GB Gigabit Ethernet Controller (Copper)
                            vendor: Intel Corporation
                            physical id: 0
                            bus info: pci@0000:08:00.0
                            logical name: enp8s0f0
                            version: 06
                            serial: 00:15:17:df:ab:27
                            size: 1Gbit/s
                            capacity: 1Gbit/s
                            width: 32 bits
                            clock: 33MHz
                            capabilities: bus_master cap_list rom ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
                            configuration: autonegotiation=on broadcast=yes driver=e1000e driverversion=5.15.104-1-pve duplex=full firmware=5.10-2 ip=172.16.0.126 latency=0 link=yes multicast=yes port=twisted pair speed=1Gbit/s
                            resources: irq:224 memory:c0700000-c071ffff memory:c0720000-c073ffff ioport:b020(size=32)
                       *-network:1
                            description: Ethernet interface
                            product: 82571EB/82571GB Gigabit Ethernet Controller (Copper)
                            vendor: Intel Corporation
                            physical id: 0.1
                            bus info: pci@0000:08:00.1
                            logical name: enp8s0f1
                            version: 06
                            serial: 00:15:17:df:ab:26
                            size: 1Gbit/s
                            capacity: 1Gbit/s
                            width: 32 bits
                            clock: 33MHz
                            capabilities: bus_master cap_list rom ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
                            configuration: autonegotiation=on broadcast=yes driver=e1000e driverversion=5.15.104-1-pve duplex=full firmware=5.10-2 ip=172.16.0.127 latency=0 link=yes multicast=yes port=twisted pair speed=1Gbit/s
                            resources: irq:225 memory:c0740000-c075ffff memory:c0760000-c077ffff ioport:b000(size=32)
              *-pci:2
                   description: PCI bridge
                   product: Advanced Micro Devices, Inc. [AMD]
                   vendor: Advanced Micro Devices, Inc. [AMD]
                   physical id: 8
                   bus info: pci@0000:03:08.0
                   version: 00
                   width: 32 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: irq:38 ioport:e000(size=4096) memory:c0800000-c08fffff
                 *-network
                      description: Wireless interface
                      product: RTL8821CE 802.11ac PCIe Wireless Network Adapter
                      vendor: Realtek Semiconductor Co., Ltd.
                      physical id: 0
                      bus info: pci@0000:09:00.0
                      logical name: wlo1
                      version: 00
                      serial: 10:68:38:06:f1:69
                      width: 64 bits
                      clock: 33MHz
                      capabilities: bus_master cap_list ethernet physical wireless
                      configuration: broadcast=yes driver=rtw_8821ce driverversion=5.15.104-1-pve firmware=N/A ip=192.168.4.159 latency=0 link=yes multicast=yes wireless=IEEE 802.11
                      resources: irq:231 ioport:e000(size=256) memory:c0800000-c080ffff
              *-pci:3
                   description: PCI bridge
                   product: Advanced Micro Devices, Inc. [AMD]
                   vendor: Advanced Micro Devices, Inc. [AMD]
                   physical id: 9
                   bus info: pci@0000:03:09.0
                   version: 00
                   width: 32 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: irq:39 ioport:d000(size=4096) memory:c0900000-c09fffff
                 *-network
                      description: Ethernet interface
                      product: RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller
                      vendor: Realtek Semiconductor Co., Ltd.
                      physical id: 0
                      bus info: pci@0000:0a:00.0
                      logical name: enp10s0
                      version: 15
                      serial: 74:56:3c:6f:79:b2
                      size: 1Gbit/s
                      capacity: 1Gbit/s
                      width: 64 bits
                      clock: 33MHz
                      capabilities: bus_master cap_list ethernet physical tp mii 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
                      configuration: autonegotiation=on broadcast=yes driver=r8169 driverversion=5.15.104-1-pve duplex=full firmware=rtl8168h-2_0.0.2 02/26/15 ip=172.16.0.129 latency=0 link=yes multicast=yes port=twisted pair speed=1Gbit/s
                      resources: irq:36 ioport:d000(size=256) memory:c0904000-c0904fff memory:c0900000-c0903fff
        *-pci:2
             description: PCI bridge
             product: Family 17h (Models 00h-0fh) PCIe GPP Bridge
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 3.1
             bus info: pci@0000:00:03.1
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: pci normal_decode bus_master cap_list
             configuration: driver=pcieport
             resources: irq:28 memory:fc700000-fcafffff
           *-pci
                description: PCI bridge
                product: ASMedia Technology Inc.
                vendor: ASMedia Technology Inc.
                physical id: 0
                bus info: pci@0000:0b:00.0
                version: 01
                width: 32 bits
                clock: 33MHz
                capabilities: pci normal_decode bus_master cap_list
                configuration: driver=pcieport
                resources: irq:43 memory:fc700000-fcafffff
              *-pci:0
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: 0
                   bus info: pci@0000:0c:00.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:44 memory:fca00000-fcafffff
                 *-storage
                      description: Non-Volatile memory controller
                      product: WD Black SN750 / PC SN730 NVMe SSD
                      vendor: Sandisk Corp
                      physical id: 0
                      bus info: pci@0000:0d:00.0
                      version: 00
                      width: 64 bits
                      clock: 33MHz
                      capabilities: storage nvm_express bus_master cap_list
                      configuration: driver=nvme latency=0
                      resources: irq:42 memory:fca00000-fca03fff memory:fca04000-fca040ff
              *-pci:1
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: 4
                   bus info: pci@0000:0c:04.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:45 memory:fc900000-fc9fffff
                 *-storage
                      description: Non-Volatile memory controller
                      product: NVMe SSD Controller SM981/PM981/PM983
                      vendor: Samsung Electronics Co Ltd
                      physical id: 0
                      bus info: pci@0000:0e:00.0
                      version: 00
                      width: 64 bits
                      clock: 33MHz
                      capabilities: storage nvm_express bus_master cap_list
                      configuration: driver=nvme latency=0
                      resources: irq:42 memory:fc900000-fc903fff
              *-pci:2
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: 6
                   bus info: pci@0000:0c:06.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:47
              *-pci:3
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: 7
                   bus info: pci@0000:0c:07.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:49
              *-pci:4
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: 8
                   bus info: pci@0000:0c:08.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:50 memory:fc800000-fc8fffff
                 *-storage
                      description: Non-Volatile memory controller
                      product: NVMe SSD Controller SM981/PM981/PM983
                      vendor: Samsung Electronics Co Ltd
                      physical id: 0
                      bus info: pci@0000:11:00.0
                      version: 00
                      width: 64 bits
                      clock: 33MHz
                      capabilities: storage nvm_express bus_master cap_list
                      configuration: driver=nvme latency=0
                      resources: irq:42 memory:fc800000-fc803fff
              *-pci:5
                   description: PCI bridge
                   product: ASMedia Technology Inc.
                   vendor: ASMedia Technology Inc.
                   physical id: c
                   bus info: pci@0000:0c:0c.0
                   version: 01
                   width: 64 bits
                   clock: 33MHz
                   capabilities: pci normal_decode bus_master cap_list
                   configuration: driver=pcieport
                   resources: iomemory:1f10-1f0f irq:51 memory:fc700000-fc7fffff
                 *-storage
                      description: Non-Volatile memory controller
                      product: WD Black SN750 / PC SN730 NVMe SSD
                      vendor: Sandisk Corp
                      physical id: 0
                      bus info: pci@0000:12:00.0
                      version: 00
                      width: 64 bits
                      clock: 33MHz
                      capabilities: storage nvm_express bus_master cap_list
                      configuration: driver=nvme latency=0
                      resources: irq:42 memory:fc700000-fc703fff memory:fc704000-fc7040ff
        *-pci:3
             description: PCI bridge
             product: Family 17h (Models 00h-0fh) Internal PCIe GPP Bridge 0 to Bus B
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 7.1
             bus info: pci@0000:00:07.1
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: pci normal_decode bus_master cap_list
             configuration: driver=pcieport
             resources: irq:29 memory:fcb00000-fcdfffff
           *-generic:0 UNCLAIMED
                description: Non-Essential Instrumentation
                product: Zeppelin/Raven/Raven2 PCIe Dummy Function
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0
                bus info: pci@0000:13:00.0
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: cap_list
                configuration: latency=0
           *-generic:1
                description: Encryption controller
                product: Family 17h (Models 00h-0fh) Platform Security Processor
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.2
                bus info: pci@0000:13:00.2
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: bus_master cap_list
                configuration: driver=ccp latency=0
                resources: irq:232 memory:fcc00000-fccfffff memory:fcd00000-fcd01fff
           *-usb
                description: USB controller
                product: Family 17h (Models 00h-0fh) USB 3.0 Host Controller
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.3
                bus info: pci@0000:13:00.3
                version: 00
                width: 64 bits
                clock: 33MHz
                capabilities: xhci bus_master cap_list
                configuration: driver=xhci_hcd latency=0
                resources: irq:230 memory:fcb00000-fcbfffff
        *-pci:4
             description: PCI bridge
             product: Family 17h (Models 00h-0fh) Internal PCIe GPP Bridge 0 to Bus B
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 8.1
             bus info: pci@0000:00:08.1
             version: 00
             width: 32 bits
             clock: 33MHz
             capabilities: pci normal_decode bus_master cap_list
             configuration: driver=pcieport
             resources: irq:31 memory:fce00000-fcefffff
           *-generic UNCLAIMED
                description: Non-Essential Instrumentation
                product: Zeppelin/Renoir PCIe Dummy Function
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0
                bus info: pci@0000:14:00.0
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: cap_list
                configuration: latency=0
           *-sata
                description: SATA controller
                product: FCH SATA Controller [AHCI mode]
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.2
                bus info: pci@0000:14:00.2
                version: 51
                width: 32 bits
                clock: 33MHz
                capabilities: sata ahci_1.0 bus_master cap_list
                configuration: driver=ahci latency=0
                resources: irq:60 memory:fce08000-fce08fff
           *-multimedia
                description: Audio device
                product: Family 17h (Models 00h-0fh) HD Audio Controller
                vendor: Advanced Micro Devices, Inc. [AMD]
                physical id: 0.3
                bus info: pci@0000:14:00.3
                version: 00
                width: 32 bits
                clock: 33MHz
                capabilities: bus_master cap_list
                configuration: driver=snd_hda_intel latency=0
                resources: irq:236 memory:fce00000-fce07fff
        *-serial UNCLAIMED
             description: SMBus
             product: FCH SMBus Controller
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 14
             bus info: pci@0000:00:14.0
             version: 59
             width: 32 bits
             clock: 66MHz
             configuration: latency=0
        *-isa
             description: ISA bridge
             product: FCH LPC Bridge
             vendor: Advanced Micro Devices, Inc. [AMD]
             physical id: 14.3
             bus info: pci@0000:00:14.3
             version: 51
             width: 32 bits
             clock: 66MHz
             capabilities: isa bus_master
             configuration: latency=0
     *-pci:1
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 101
          bus info: pci@0000:00:01.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:2
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 102
          bus info: pci@0000:00:02.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:3
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 103
          bus info: pci@0000:00:03.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:4
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 104
          bus info: pci@0000:00:04.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:5
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 105
          bus info: pci@0000:00:07.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:6
          description: Host bridge
          product: Family 17h (Models 00h-1fh) PCIe Dummy Host Bridge
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 106
          bus info: pci@0000:00:08.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:7
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 0
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 107
          bus info: pci@0000:00:18.0
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:8
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 1
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 108
          bus info: pci@0000:00:18.1
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:9
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 2
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 109
          bus info: pci@0000:00:18.2
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:10
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 3
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 10a
          bus info: pci@0000:00:18.3
          version: 00
          width: 32 bits
          clock: 33MHz
          configuration: driver=k10temp
          resources: irq:0
     *-pci:11
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 4
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 10b
          bus info: pci@0000:00:18.4
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:12
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 5
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 10c
          bus info: pci@0000:00:18.5
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:13
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 6
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 10d
          bus info: pci@0000:00:18.6
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pci:14
          description: Host bridge
          product: Family 17h (Models 00h-0fh) Data Fabric: Device 18h; Function 7
          vendor: Advanced Micro Devices, Inc. [AMD]
          physical id: 10e
          bus info: pci@0000:00:18.7
          version: 00
          width: 32 bits
          clock: 33MHz
     *-pnp00:00
          product: PnP device PNP0c01
          physical id: 2
          capabilities: pnp
          configuration: driver=system
     *-pnp00:01
          product: PnP device PNP0b00
          physical id: 3
          capabilities: pnp
          configuration: driver=rtc_cmos
     *-pnp00:02
          product: PnP device PNP0c02
          physical id: 4
          capabilities: pnp
          configuration: driver=system
     *-pnp00:03
          product: PnP device PNP0c02
          physical id: 5
          capabilities: pnp
          configuration: driver=system
  *-network
       description: Ethernet interface
       physical id: 1
       logical name: zt3jntm3be
       serial: 92:04:26:1e:42:29
       size: 10Mbit/s
       capabilities: ethernet physical
       configuration: autonegotiation=off broadcast=yes driver=tun driverversion=1.6 duplex=full ip=10.241.208.165 link=yes multicast=yes port=twisted pair speed=10Mbit/s
WARNING: output may be incomplete or inaccurate, you should run this program as super-user.
bkaler@host4:~$ clear
bkaler@host4:~$ lshw -class disk -class storage
WARNING: you should run this program as super-user.
  *-storage                 
       description: Non-Volatile memory controller
       product: XG6 NVMe SSD Controller
       vendor: Toshiba Corporation
       physical id: 0
       bus info: pci@0000:01:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:52 memory:fcf00000-fcf03fff
  *-sata
       description: SATA controller
       product: Advanced Micro Devices, Inc. [AMD]
       vendor: Advanced Micro Devices, Inc. [AMD]
       physical id: 0.1
       bus info: pci@0000:02:00.1
       version: 00
       width: 32 bits
       clock: 33MHz
       capabilities: sata ahci_1.0 bus_master cap_list rom
       configuration: driver=ahci latency=0
       resources: irq:55 memory:c0a80000-c0a9ffff memory:c0a00000-c0a7ffff
  *-sas
       description: Serial Attached SCSI controller
       product: SAS2008 PCI-Express Fusion-MPT SAS-2 [Falcon]
       vendor: Broadcom / LSI
       physical id: 0
       bus info: pci@0000:04:00.0
       version: 03
       width: 64 bits
       clock: 33MHz
       capabilities: sas bus_master cap_list rom
       configuration: driver=mpt3sas latency=0
       resources: irq:34 ioport:f000(size=256) memory:c0440000-c0443fff memory:c0000000-c003ffff memory:c0444000-c0483fff memory:c0040000-c043ffff
  *-storage
       description: Non-Volatile memory controller
       product: WD Black SN750 / PC SN730 NVMe SSD
       vendor: Sandisk Corp
       physical id: 0
       bus info: pci@0000:0d:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fca00000-fca03fff memory:fca04000-fca040ff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:0e:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc900000-fc903fff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:11:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc800000-fc803fff
  *-storage
       description: Non-Volatile memory controller
       product: WD Black SN750 / PC SN730 NVMe SSD
       vendor: Sandisk Corp
       physical id: 0
       bus info: pci@0000:12:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc700000-fc703fff memory:fc704000-fc7040ff
  *-sata
       description: SATA controller
       product: FCH SATA Controller [AHCI mode]
       vendor: Advanced Micro Devices, Inc. [AMD]
       physical id: 0.2
       bus info: pci@0000:14:00.2
       version: 51
       width: 32 bits
       clock: 33MHz
       capabilities: sata ahci_1.0 bus_master cap_list
       configuration: driver=ahci latency=0
       resources: irq:60 memory:fce08000-fce08fff
WARNING: output may be incomplete or inaccurate, you should run this program as super-user.
bkaler@host4:~$ lshw -C disk
WARNING: you should run this program as super-user.
WARNING: output may be incomplete or inaccurate, you should run this program as super-user.
bkaler@host4:~$ su root
Password: 
root@host4:/home/bkaler# lshw -class disk -class storage
  *-storage                 
       description: Non-Volatile memory controller
       product: XG6 NVMe SSD Controller
       vendor: Toshiba Corporation
       physical id: 0
       bus info: pci@0000:01:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage pciexpress pm msi msix nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:52 memory:fcf00000-fcf03fff
  *-sata
       description: SATA controller
       product: Advanced Micro Devices, Inc. [AMD]
       vendor: Advanced Micro Devices, Inc. [AMD]
       physical id: 0.1
       bus info: pci@0000:02:00.1
       version: 00
       width: 32 bits
       clock: 33MHz
       capabilities: sata msi pm pciexpress ahci_1.0 bus_master cap_list rom
       configuration: driver=ahci latency=0
       resources: irq:55 memory:c0a80000-c0a9ffff memory:c0a00000-c0a7ffff
  *-sas
       description: Serial Attached SCSI controller
       product: SAS2008 PCI-Express Fusion-MPT SAS-2 [Falcon]
       vendor: Broadcom / LSI
       physical id: 0
       bus info: pci@0000:04:00.0
       logical name: scsi7
       version: 03
       width: 64 bits
       clock: 33MHz
       capabilities: sas pm pciexpress vpd msi msix bus_master cap_list rom
       configuration: driver=mpt3sas latency=0
       resources: irq:34 ioport:f000(size=256) memory:c0440000-c0443fff memory:c0000000-c003ffff memory:c0444000-c0483fff memory:c0040000-c043ffff
     *-disk:0
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.0.0
          bus info: scsi@7:0.0.0
          logical name: /dev/sda
          version: CC49
          serial: S1DJK0PE
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=58f82062-d4cb-4fb5-b7d7-c8160c80b1d0 logicalsectorsize=512 sectorsize=4096
     *-disk:1
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.1.0
          bus info: scsi@7:0.1.0
          logical name: /dev/sdb
          version: CC47
          serial: S1DDP9HS
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=6e5e6ec0-57c6-4c3c-8e01-1639278baba0 logicalsectorsize=512 sectorsize=4096
     *-disk:2
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.2.0
          bus info: scsi@7:0.2.0
          logical name: /dev/sdc
          version: CC47
          serial: S1DE01XH
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=860d7c34-73c5-4c50-bcdb-7805d55c0be5 logicalsectorsize=512 sectorsize=4096
     *-disk:3
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.3.0
          bus info: scsi@7:0.3.0
          logical name: /dev/sdd
          version: CC47
          serial: S1DDYC5D
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=db889333-f7cd-41f1-b2dc-76ba04d09ddf logicalsectorsize=512 sectorsize=4096
     *-disk:4
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.4.0
          bus info: scsi@7:0.4.0
          logical name: /dev/sde
          version: CC49
          serial: S1DJG81J
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=75b8857f-70b3-4ab4-a79b-cfad4eb239c9 logicalsectorsize=512 sectorsize=4096
     *-disk:5
          description: ATA Disk
          product: WDC WD15EADS-00P
          vendor: Western Digital
          physical id: 0.5.0
          bus info: scsi@7:0.5.0
          logical name: /dev/sdf
          version: 0A01
          serial: WD-WMAVU1632449
          size: 1397GiB (1500GB)
          capacity: 1397GiB (1500GB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=76f42fed-9fb1-49ca-8383-47a71c4ba3b9 logicalsectorsize=512 sectorsize=512
     *-disk:6
          description: ATA Disk
          product: ST31000524AS
          physical id: 0.6.0
          bus info: scsi@7:0.6.0
          logical name: /dev/sdg
          version: JC4B
          serial: 9VPDQLWF
          size: 931GiB (1TB)
          capacity: 931GiB (1TB)
          capabilities: 15000rpm gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=e30ff707-30fc-4b15-a7a2-a08789074d43 logicalsectorsize=512 sectorsize=512
     *-disk:7
          description: ATA Disk
          product: ST1000DM003-1CH1
          physical id: 0.7.0
          bus info: scsi@7:0.7.0
          logical name: /dev/sdh
          version: CC47
          serial: S1DE05RJ
          size: 931GiB (1TB)
          capabilities: gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=6 guid=2a1fd4eb-605e-437f-8c54-dadda1f579fd logicalsectorsize=512 sectorsize=4096
  *-storage
       description: Non-Volatile memory controller
       product: WD Black SN750 / PC SN730 NVMe SSD
       vendor: Sandisk Corp
       physical id: 0
       bus info: pci@0000:0d:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage pm msi msix pciexpress nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fca00000-fca03fff memory:fca04000-fca040ff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:0e:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage pm msi pciexpress msix nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc900000-fc903fff
  *-storage
       description: Non-Volatile memory controller
       product: NVMe SSD Controller SM981/PM981/PM983
       vendor: Samsung Electronics Co Ltd
       physical id: 0
       bus info: pci@0000:11:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage pm msi pciexpress msix nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc800000-fc803fff
  *-storage
       description: Non-Volatile memory controller
       product: WD Black SN750 / PC SN730 NVMe SSD
       vendor: Sandisk Corp
       physical id: 0
       bus info: pci@0000:12:00.0
       version: 00
       width: 64 bits
       clock: 33MHz
       capabilities: storage pm msi msix pciexpress nvm_express bus_master cap_list
       configuration: driver=nvme latency=0
       resources: irq:42 memory:fc700000-fc703fff memory:fc704000-fc7040ff
  *-sata
       description: SATA controller
       product: FCH SATA Controller [AHCI mode]
       vendor: Advanced Micro Devices, Inc. [AMD]
       physical id: 0.2
       bus info: pci@0000:14:00.2
       version: 51
       width: 32 bits
       clock: 33MHz
       capabilities: sata pm pciexpress msi ahci_1.0 bus_master cap_list
       configuration: driver=ahci latency=0
       resources: irq:60 memory:fce08000-fce08fff
root@host4:/home/bkaler# 
