================================================================================
    Population count comparison for Cortex A57 (AMD Opteron A1100)
================================================================================

Generated on: 2017-04-26

.. contents:: Contents


Specification
--------------------------------------------------

CPU: Cortex A57 (AMD Opteron A1100)

Compiler: clang 3.8.0 (tags/RELEASE_380/final 262553)

Instruction set: 64-bit

Number of runs: 5

All times are given in **seconds**.


Procedures
##############################

+---------------------------+--------------------------------------+
| procedure                 | description                          |
+===========================+======================================+
| lookup-8                  | lookup in std::uint8_t[256] LUT      |
+---------------------------+--------------------------------------+
| lookup-64                 | lookup in std::uint64_t[256] LUT     |
+---------------------------+--------------------------------------+
| bit-parallel              | naive bit parallel method            |
+---------------------------+--------------------------------------+
| bit-parallel-optimized    | a bit better bit parallel            |
+---------------------------+--------------------------------------+
| bit-parallel-mul          | bit-parallel with fewer instructions |
+---------------------------+--------------------------------------+
| bit-parallel32            | naive bit parallel method (32 bit)   |
+---------------------------+--------------------------------------+
| bit-parallel-optimized32  | a bit better bit parallel (32 bit)   |
+---------------------------+--------------------------------------+
| harley-seal               | Harley-Seal popcount (4th iteration) |
+---------------------------+--------------------------------------+
| builtin-popcnt            | builtin for popcnt                   |
+---------------------------+--------------------------------------+
| builtin-popcnt32          | builtin for popcnt (32-bit variant)  |
+---------------------------+--------------------------------------+
| builtin-popcnt-unrolled   | unrolled builtin-popcnt              |
+---------------------------+--------------------------------------+
| builtin-popcnt-unrolled32 | unrolled builtin-popcnt32            |
+---------------------------+--------------------------------------+
| neon-vcnt                 | ARM Neon using VCNT                  |
+---------------------------+--------------------------------------+
| neon-HS                   | Harley-Seal using Neon VCNT          |
+---------------------------+--------------------------------------+
| aarch64-cnt               | ARMv8 Neon using CNT                 |
+---------------------------+--------------------------------------+


Running time
--------------------------------------------------

+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| procedure                 | 32 B        | 64 B        | 128 B       | 256 B       | 512 B       | 1024 B      | 2048 B      | 4096 B      |
+===========================+=============+=============+=============+=============+=============+=============+=============+=============+
| lookup-8                  | 0.44138     | 0.49726     | 0.46049     | 0.44210     | 0.69265     | 0.68529     | 0.68163     | 0.67980     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| lookup-64                 | 0.45898     | 0.49726     | 0.46067     | 0.44217     | 0.69269     | 0.68537     | 0.68161     | 0.67988     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| bit-parallel              | 0.32935     | 0.31188     | 0.30306     | 0.29864     | 0.48610     | 0.47843     | 0.47461     | 0.47268     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| bit-parallel-optimized    | 0.24128     | 0.22655     | 0.21920     | 0.21552     | 0.35369     | 0.34634     | 0.34308     | 0.34080     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| bit-parallel-mul          | 0.24716     | 0.17115     | 0.19713     | 0.17433     | 0.26012     | 0.25070     | 0.24200     | 0.24331     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| bit-parallel32            | 0.35306     | 0.33542     | 0.32659     | 0.33837     | 0.52493     | 0.51670     | 0.51259     | 0.51050     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| bit-parallel-optimized32  | 0.30358     | 0.28204     | 0.27569     | 0.28175     | 0.43545     | 0.42812     | 0.42429     | 0.42250     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| harley-seal               | 0.60614     | 0.36679     | 0.12063     | 0.09305     | 0.12711     | 0.11607     | 0.11284     | 0.10909     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| builtin-popcnt            | 0.11769     | 0.09710     | 0.09415     | 0.10813     | 0.16182     | 0.15623     | 0.15344     | 0.15204     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| builtin-popcnt32          | 0.23575     | 0.23539     | 0.26480     | 0.25009     | 0.38838     | 0.38253     | 0.37955     | 0.37810     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| builtin-popcnt-unrolled   | **0.09268** | **0.09268** | 0.09268     | 0.09268     | 0.15535     | 0.15182     | 0.15006     | 0.14918     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| builtin-popcnt-unrolled32 | 0.22955     | 0.22928     | 0.22941     | 0.23761     | 0.37366     | 0.37043     | 0.36881     | 0.36800     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| neon-vcnt                 | 0.57668     | 0.46531     | **0.06547** | **0.05559** | 0.08295     | **0.07719** | 0.07783     | 0.07481     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| neon-HS                   | 0.71582     | 0.53949     | 0.46587     | 0.09106     | 0.12852     | 0.11652     | 0.11384     | 0.11087     |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+
| aarch64-cnt               | 0.57080     | 0.46488     | 0.42515     | 0.05689     | **0.08223** | 0.07738     | **0.07463** | **0.07334** |
+---------------------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+-------------+



Input size 32B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.44138  | ██████████████████████████████▊                    |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.45898  | ████████████████████████████████                   |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.32935  | ███████████████████████                            |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.24128  | ████████████████▊                                  |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.24716  | █████████████████▎                                 |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.35306  | ████████████████████████▋                          |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.30358  | █████████████████████▏                             |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.60614  | ██████████████████████████████████████████▎        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.11769  | ████████▏                                          |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.23575  | ████████████████▍                                  |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.09268  | ██████▍                                            |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.22955  | ████████████████                                   |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.57668  | ████████████████████████████████████████▎          |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.71582  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.57080  | ███████████████████████████████████████▊           |
+---------------------------+----------+----------------------------------------------------+



Input size 64B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.49726  | ██████████████████████████████████████████████     |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.49726  | ██████████████████████████████████████████████     |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.31188  | ████████████████████████████▉                      |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.22655  | ████████████████████▉                              |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.17115  | ███████████████▊                                   |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.33542  | ███████████████████████████████                    |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.28204  | ██████████████████████████▏                        |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.36679  | █████████████████████████████████▉                 |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.09710  | ████████▉                                          |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.23539  | █████████████████████▊                             |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.09268  | ████████▌                                          |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.22928  | █████████████████████▏                             |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.46531  | ███████████████████████████████████████████▏       |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.53949  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.46488  | ███████████████████████████████████████████        |
+---------------------------+----------+----------------------------------------------------+



Input size 128B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.46049  | █████████████████████████████████████████████████▍ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.46067  | █████████████████████████████████████████████████▍ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.30306  | ████████████████████████████████▌                  |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.21920  | ███████████████████████▌                           |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.19713  | █████████████████████▏                             |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.32659  | ███████████████████████████████████                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.27569  | █████████████████████████████▌                     |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.12063  | ████████████▉                                      |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.09415  | ██████████                                         |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.26480  | ████████████████████████████▍                      |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.09268  | █████████▉                                         |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.22941  | ████████████████████████▌                          |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.06547  | ███████                                            |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.46587  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.42515  | █████████████████████████████████████████████▋     |
+---------------------------+----------+----------------------------------------------------+



Input size 256B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.44210  | █████████████████████████████████████████████████▉ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.44217  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.29864  | █████████████████████████████████▊                 |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.21552  | ████████████████████████▎                          |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.17433  | ███████████████████▋                               |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.33837  | ██████████████████████████████████████▎            |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.28175  | ███████████████████████████████▊                   |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.09305  | ██████████▌                                        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.10813  | ████████████▏                                      |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.25009  | ████████████████████████████▎                      |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.09268  | ██████████▍                                        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.23761  | ██████████████████████████▊                        |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.05559  | ██████▎                                            |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.09106  | ██████████▎                                        |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.05689  | ██████▍                                            |
+---------------------------+----------+----------------------------------------------------+



Input size 512B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.69265  | █████████████████████████████████████████████████▉ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.69269  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.48610  | ███████████████████████████████████                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.35369  | █████████████████████████▌                         |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.26012  | ██████████████████▊                                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.52493  | █████████████████████████████████████▉             |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.43545  | ███████████████████████████████▍                   |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.12711  | █████████▏                                         |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.16182  | ███████████▋                                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.38838  | ████████████████████████████                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.15535  | ███████████▏                                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.37366  | ██████████████████████████▉                        |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.08295  | █████▉                                             |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.12852  | █████████▎                                         |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.08223  | █████▉                                             |
+---------------------------+----------+----------------------------------------------------+



Input size 1024B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.68529  | █████████████████████████████████████████████████▉ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.68537  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.47843  | ██████████████████████████████████▉                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.34634  | █████████████████████████▎                         |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.25070  | ██████████████████▎                                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.51670  | █████████████████████████████████████▋             |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.42812  | ███████████████████████████████▏                   |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.11607  | ████████▍                                          |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.15623  | ███████████▍                                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.38253  | ███████████████████████████▉                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.15182  | ███████████                                        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.37043  | ███████████████████████████                        |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.07719  | █████▋                                             |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.11652  | ████████▌                                          |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.07738  | █████▋                                             |
+---------------------------+----------+----------------------------------------------------+



Input size 2048B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.68163  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.68161  | █████████████████████████████████████████████████▉ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.47461  | ██████████████████████████████████▊                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.34308  | █████████████████████████▏                         |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.24200  | █████████████████▊                                 |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.51259  | █████████████████████████████████████▌             |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.42429  | ███████████████████████████████                    |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.11284  | ████████▎                                          |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.15344  | ███████████▎                                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.37955  | ███████████████████████████▊                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.15006  | ███████████                                        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.36881  | ███████████████████████████                        |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.07783  | █████▋                                             |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.11384  | ████████▎                                          |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.07463  | █████▍                                             |
+---------------------------+----------+----------------------------------------------------+



Input size 4096B
###########################################################

+---------------------------+----------+----------------------------------------------------+
| procedure                 | time [s] | relative time (less is better)                     |
+===========================+==========+====================================================+
| lookup-8                  | 0.67980  | █████████████████████████████████████████████████▉ |
+---------------------------+----------+----------------------------------------------------+
| lookup-64                 | 0.67988  | ██████████████████████████████████████████████████ |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel              | 0.47268  | ██████████████████████████████████▊                |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized    | 0.34080  | █████████████████████████                          |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-mul          | 0.24331  | █████████████████▉                                 |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel32            | 0.51050  | █████████████████████████████████████▌             |
+---------------------------+----------+----------------------------------------------------+
| bit-parallel-optimized32  | 0.42250  | ███████████████████████████████                    |
+---------------------------+----------+----------------------------------------------------+
| harley-seal               | 0.10909  | ████████                                           |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt            | 0.15204  | ███████████▏                                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt32          | 0.37810  | ███████████████████████████▊                       |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled   | 0.14918  | ██████████▉                                        |
+---------------------------+----------+----------------------------------------------------+
| builtin-popcnt-unrolled32 | 0.36800  | ███████████████████████████                        |
+---------------------------+----------+----------------------------------------------------+
| neon-vcnt                 | 0.07481  | █████▌                                             |
+---------------------------+----------+----------------------------------------------------+
| neon-HS                   | 0.11087  | ████████▏                                          |
+---------------------------+----------+----------------------------------------------------+
| aarch64-cnt               | 0.07334  | █████▍                                             |
+---------------------------+----------+----------------------------------------------------+




Speedup
--------------------------------------------------

+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| procedure                 | 32 B | 64 B | 128 B | 256 B | 512 B | 1024 B | 2048 B | 4096 B |
+===========================+======+======+=======+=======+=======+========+========+========+
| lookup-8                  | 1.00 | 1.00 | 1.00  | 1.00  | 1.00  | 1.00   | 1.00   | 1.00   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| lookup-64                 | 0.96 | 1.00 | 1.00  | 1.00  | 1.00  | 1.00   | 1.00   | 1.00   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| bit-parallel              | 1.34 | 1.59 | 1.52  | 1.48  | 1.42  | 1.43   | 1.44   | 1.44   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| bit-parallel-optimized    | 1.83 | 2.19 | 2.10  | 2.05  | 1.96  | 1.98   | 1.99   | 1.99   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| bit-parallel-mul          | 1.79 | 2.91 | 2.34  | 2.54  | 2.66  | 2.73   | 2.82   | 2.79   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| bit-parallel32            | 1.25 | 1.48 | 1.41  | 1.31  | 1.32  | 1.33   | 1.33   | 1.33   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| bit-parallel-optimized32  | 1.45 | 1.76 | 1.67  | 1.57  | 1.59  | 1.60   | 1.61   | 1.61   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| harley-seal               | 0.73 | 1.36 | 3.82  | 4.75  | 5.45  | 5.90   | 6.04   | 6.23   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| builtin-popcnt            | 3.75 | 5.12 | 4.89  | 4.09  | 4.28  | 4.39   | 4.44   | 4.47   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| builtin-popcnt32          | 1.87 | 2.11 | 1.74  | 1.77  | 1.78  | 1.79   | 1.80   | 1.80   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| builtin-popcnt-unrolled   | 4.76 | 5.37 | 4.97  | 4.77  | 4.46  | 4.51   | 4.54   | 4.56   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| builtin-popcnt-unrolled32 | 1.92 | 2.17 | 2.01  | 1.86  | 1.85  | 1.85   | 1.85   | 1.85   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| neon-vcnt                 | 0.77 | 1.07 | 7.03  | 7.95  | 8.35  | 8.88   | 8.76   | 9.09   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| neon-HS                   | 0.62 | 0.92 | 0.99  | 4.86  | 5.39  | 5.88   | 5.99   | 6.13   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+
| aarch64-cnt               | 0.77 | 1.07 | 1.08  | 7.77  | 8.42  | 8.86   | 9.13   | 9.27   |
+---------------------------+------+------+-------+-------+-------+--------+--------+--------+


CSV file
--------------------------------------------------

Download `arm-64bit-clang3.8.0.csv <arm-64bit-clang3.8.0.csv>`_
