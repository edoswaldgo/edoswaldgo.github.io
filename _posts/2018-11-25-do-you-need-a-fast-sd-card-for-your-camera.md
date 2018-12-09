---
title: "A Fast SD Card for Your Camera: Do You Need One?"
excerpt: "Having freezing problems with your camera? Learn why I bought a SanDisk Extreme PRO and how I tested its performance for my Fujifilm X-A10 camera to help overcome the performance bottleneck."
last_modified_at: "2018-12-09T19:00:00+08:00"
toc: true
toc_label: "Table of Contents"
categories:
- photography
tags:
- fujifilm
- sandisk
splash_teaser: /assets/img/blog/sd-card/sd-cards-thumb-600x450.jpg
---

## Introduction

[SD (Secure Digital)][sd] cards are the common storage media being used by modern digital cameras. They are very important to a camera setup because they are like analog camera films where the pictures are stored in. Having a reliable storage medium is a must for preventing data loss and corruption, but how about the performance of the SD card?

When taking pictures before, there were times when my camera froze due to some write delays. My camera did not let me take another shot without waiting for the write operation to finish. You might have heard that you need a class 10 SD card at the minimum in order not to encounter some bottleneck when taking pictures. But, I was already using a class 10 card! How come I was still encountering some bottleneck?

I usually take pictures in RAW + JPEG mode using my [Fujifilm X-A10][fuji-xa10]. The approximate size of my camera's output is 24 MB for RAW and 5MB for JPEG. Given the numbers, I might be hitting the maximum write speed of my SD card and might be needing an SD card that is faster in writing ~30 MB at a given time frame.

**Tip:** JPEGS are quite handy because whenever I am lazy to do some RAW editing, I can just easily transfer the photos to my smartphone and upload to some social media platform.
{: .notice--info}

## Choosing an SD Card

In case you are not yet familiar with the SD card speed classes, you will usually see classes 2, 4, 6, and 10; the numbers indicate the minimum write speed of the card in Megabytes per second (MB/s). Now, there are more ratings to cards. You might also see the [Ultra High Speed-I (UHS-I)][uhs] interface classes, U1 or U3, indicating a minimum write speed of *10 MB/s* and *30 MB/s*, respectively.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/oswaldogo/46037946041/in/datetaken-public/" title="Test of SD Cards - Guess Who’s The Winner"><img src="https://farm5.staticflickr.com/4871/46037946041_83673a56e5_k.jpg" width="640" height="427" alt="Test of SD Cards - Guess Who’s The Winner"></a>

I recently purchased a 32GB [SanDisk Extreme PRO][sandisk-extreme-pro] which is a class 10 UHS-I U3 card. It has a read speed rating of up to *95 MB/s* and up to *90 MB/s* for its write speed. I opted to buy the Extreme PRO instead of the [Extreme][sandisk-extreme] version because of the write speed rating difference.

**Tip:** I prefer to carry more smaller capacity cards to lessen the risk of losing all my photos in case of a broken or corrupted card.
{: .notice--info}

The Extreme version only supports a write speed of up to *40 MB/s* for 16-64 GB and up to *60 MB/s* for the 128-256 GB variants. Aside from the write speed rating difference, the Extreme PRO has a better bang for my buck because of the price to write speed ratio. I gave more importance to the write speed ratio as compared to the price to capacity ratio for this case.

  ```
  Extreme 32GB:
  600 PHP / 40 MBps = 15 PHP / MBps
  600 PHP / 32 GB = 18.75 PHP / GB

  Extreme PRO 32GB:
  800 PHP / 90 MBps = 8.88 PHP / MBps
  800 PHP / 32 GB = 25 PHP / GB
  ```

**Note:** Prices are rounded up and are not the SRPs as of 25-November 2018. Also, please be aware that there are many fake memory cards. Double check the credibility of the sellers before buying.
{: .notice--warning}

## Testing the SD Card

As there are many fake memory cards being sold today, first, I wanted to verify the performance of the card I bought if it lives up to the rating of the manufacturer. It would be a waste if I bought a fake memory card that performs like a lower class one. For this verification, I found a great software named [CrystalDiskMark][crystaldiskmark]. It is an open-source disk benchmark tool for measuring the read and write performance of your hard disk, SSD, and/or flash drives. 

Also, this software gave me an opportunity to measure my current SD card. I am using the [SanDisk Ultra][sandisk-ultra-gray] freebie back when I bought my camera. It is a class 10 UHS-I card and has a read speed rating of *48 MB/s*. There's no actual write speed rating based from the product specification but it will surely be slower than its read speed.

### Software Test - CrystalDiskMark (v6.0.2 x64)

I used the [UGreen USB 3.0 Card Reader][ugreen-usb-hub] for connecting the SD cards to my machine where CrystalDiskMark v6.0.2 x64 is installed. I set CrystalDiskMark's test count to five with one GB test data. I included some of my existing SD cards to the test for comparison. The results confirmed that the Extreme PRO SD card I bought is up to its rating. For my SanDisk Ultra card, its write speed is less than 30 MB/s which might explain why I was encountering some write delays.

| SD Card                                      | Capacity (GB) | Seq Q32T1 (Read MB/s)  | Seq Q32T1 (Write MB/s) |
| -------------------------------------------- | ------------: | ---------------------: | ---------------------: |
| [SanDisk Extreme PRO][sandisk-extreme-pro]   |            32 |                  91.40 |                  85.63 |
| [SanDisk Ultra][sandisk-ultra-gray]          |            16 |                  46.32 |                  28.86 |
| [Kingston MicroSD][kingston-class10-uhs1]    |            32 |                  45.98 |                  13.34 |
| SanDisk Ultra MicroSD                        |            64 |                  45.93 |                  12.35 |

### Camera Test - Fujifilm X-A10

After the satisfying benchmark results from [CrystalDiskMark][crystaldiskmark], now let's head on to the integration test with the [Fujifilm X-A10][fuji-xa10] camera. Digital cameras have a memory buffer that stores images temporarily before getting written to the SD card. The buffer can help photographers in burst shooting to capture more photos while writing in the background. The faster the writing to the card, the faster the buffer clears.

I wanted to verify the card performance using my camera and determine if my camera would choke on its image buffer (which would make me regret the SD card purchase). The test was to continuously shoot in RAW for 30 seconds and determine how much data could be written to the SD card. I recorded videos of the camera during testing to know the total time of writing in which I depended on the camera's light indicator. Head down below to see the results of the test.

**Note :** This test involved shooting pure RAW images only. I did not include JPEG because it would add more processing overhead to the camera which might skew the writing results.
{: .notice--info}

#### Camera Configuration

| Option                         | Value            |
| ------------------------------ | ---------------- |
| Continuous Shooting            | H (6.0 fps)      |
| Focus Mode                     | MF               |
| ISO                            | 200              |
| Shutter Speed                  | 1/200            |
| Image Quality                  | RAW              |
| Dynamic Range                  | Auto             |
| Film Simulation                | Standard         |
| White Balance                  | Auto             |
| Shoot Without Lens             | On               |
| MF Assist                      | Standard         |

#### Camera Test - Results

The performance of the Sandisk Extreme PRO did not disappoint me even if it did not reach the write speed from the software test. Its results really blew past the performance of the other SD cards I've used. Comparing the results from CrystalDiskMark, the result of the Sandisk Ultra was quite strange as it was the 2nd top performer but became the slowest one for this test.

| SD Card                                      | Data Written (MB) | No. of Images (RAW) | Write Time (s) | Avg Write Speed (MB/s)|
| -------------------------------------------- | ----------------: | ------------------: | -------------: | --------------------: |
| [SanDisk Extreme PRO][sandisk-extreme-pro]   |           2182.41 |                  94 |             33 |                 66.13 |
| [SanDisk Ultra (Gray)][sandisk-ultra-gray]   |            534.03 |                  23 |             67 |                  7.97 |
| [Kingston MicroSD][kingston-class10-uhs1]    |            697.50 |                  30 |             52 |                 13.41 |
| SanDisk Ultra MicroSD                        |            581.25 |                  24 |             61 |                  9.53 |

**Important Note :** In reality, people wouldn't shoot like the test scenario done and I am not sure if the test done is safe for my camera. Best to still observe performance depending on your use case.
{: .notice--warning}

## Conclusion

I am happy with my purchase given that SD card prices are now more affordable while achieving great performance. But really, I do not need that much of a performance because I do not take photos in burst mode as most photos I take are landspaces and products. I am hoping that I will not encounter any laggy moments in the future while using the SanDisk Extreme PRO card.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/oswaldogo/45516397954/in/datetaken-public/" title="SanDisk Extreme PRO - The Missing Piece"><img src="https://farm2.staticflickr.com/1956/45516397954_220055b3a3_z.jpg" width="640" height="427" alt="SanDisk Extreme PRO - The Missing Piece"></a>

Having a faster and better performing SD card is essential for increasing the throughput of your camera. They are great helpers but the need still depends on your use case, photography style, and budget. Below are some pointers that might help you decide if need an upgrade or not.

1. If you are not having problems or hiccups with your current setup, then you do not need an upgrade.
2. If you are purely shooting JPEGs or shooting one image at a time, then you are probably fine with a normal class 10 card.
3. If your SD card is broken, buy a reliable one with the appropriate speed for your camera.
4. If you shoot many many many photos and tired of waiting, go with higher speeds.
5. The most important point is to just keep shooting and to practice more whatever your SD card is.

Cheers!

<script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

[sd]: https://en.wikipedia.org/wiki/Secure_Digital
[uhs]: https://en.wikipedia.org/wiki/Secure_Digital#UHS

[sandisk-extreme]: https://www.sandisk.com/home/memory-cards/sd-cards/extreme-sd-uhs-i
[sandisk-extreme-pro]: https://www.sandisk.com/home/memory-cards/sd-cards/extremepro-sd-uhs-i
[sandisk-ultra-gray]: https://www.sandisk.com/home/memory-cards/sd-cards/ultra-sd-48mbs
[kingston-class10-uhs1]: https://www.kingston.com/en/flash/microsd_cards/sdc10g2

[crystaldiskmark]: https://crystalmark.info/en/software/crystaldiskmark
[fuji-xa10]: http://www.fujifilmph.com/x-series/x-mirrorless-digital-camera/x-a10
[ugreen-usb-hub]: http://www.ugreen.com.cn/product-912-en.html