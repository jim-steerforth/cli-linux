---
title: 'Server Benchmarking'
---

I am using the server benchmark nench available here https://github.com/n-st/nench
The first is a www.hostvhds.com server on their 79 cent a month plan on Ubuntu, the second on alibaba.com running Aliyun, a derivative of Centos,
<html>
    <body>
<code>
    <pre>

$ ./nench.sh

 nench.sh v2019.07.20 -- https://git.io/nench.sh
 benchmark timestamp:    2020-09-13 03:01:43 UTC


Processor:    06/55
CPU cores:    1
Frequency:    1800.000 MHz
RAM:          985M
Swap:         1.0G
Kernel:       Linux 4.15.0-88-generic x86_64

Disks:
sda     10G  HDD

CPU: SHA256-hashing 500 MB
    4.475 seconds
CPU: bzip2-compressing 500 MB
    7.204 seconds
CPU: AES-encrypting 500 MB
    1.411 seconds

ioping: seek rate
    min/avg/max/mdev = 93.9 us / 422.4 us / 7.81 ms / 383.8 us
ioping: sequential read speed
    generated 4.37 k requests in 5.00 s, 1.07 GiB, 873 iops, 218.5 MiB/s

dd: sequential write speed
    1st run:    399.59 MiB/s
    2nd run:    370.03 MiB/s
    3rd run:    382.42 MiB/s
    average:    384.01 MiB/s

IPv4 speedtests
    your IPv4:    45.156.24.xxxx

    Cachefly CDN:         5.23 MiB/s
    Leaseweb (NL):        3.62 MiB/s
    Softlayer DAL (US):   3.76 MiB/s
    Online.net (FR):      5.19 MiB/s
    OVH BHS (CA):         4.17 MiB/s

No IPv6 connectivity detected

-------------------------------------------------
 nench.sh v2019.07.20 -- https://git.io/nench.sh
 benchmark timestamp:    2020-09-13 04:06:11 UTC
-------------------------------------------------

Processor:    06/55
CPU cores:    1
Frequency:    1800.000 MHz
RAM:          985M
Swap:         1.0G
Kernel:       Linux 4.15.0-88-generic x86_64

Disks:
sda     10G  HDD

CPU: SHA256-hashing 500 MB
    4.836 seconds
CPU: bzip2-compressing 500 MB
    8.190 seconds
CPU: AES-encrypting 500 MB
    1.503 seconds

ioping: seek rate
    min/avg/max/mdev = 84.0 us / 466.7 us / 13.7 ms / 532.5 us
ioping: sequential read speed
    generated 3.99 k requests in 5.00 s, 998.2 MiB, 798 iops, 199.6 MiB/s

dd: sequential write speed
    1st run:    462.53 MiB/s
    2nd run:    447.27 MiB/s
    3rd run:    502.59 MiB/s
    average:    470.80 MiB/s

IPv4 speedtests
    your IPv4:    45.156.24.xxxx

    Cachefly CDN:         5.18 MiB/s
    Leaseweb (NL):        5.11 MiB/s
    Softlayer DAL (US):   4.06 MiB/s
    Online.net (FR):      5.19 MiB/s
    OVH BHS (CA):         4.80 MiB/s

No IPv6 connectivity detected
-------------------------------------------------



</pre>
</code>
        </body>
        </html>
    
