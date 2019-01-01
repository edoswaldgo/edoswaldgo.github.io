---
title: "What is Your Favorite Focal Length? Determine Your Frequently Used Focal Lengths via ExifTool"
excerpt: "A fun but inaccurate way to know your favorite focal length using ExifTool, Google Sheets and your huge amount of travel photos."
toc: true
toc_label: "Table of Contents"
categories:
- photography
tags:
- tools
- technology
- software
splash_teaser: /assets/img/blog/cameras/canon-kit-lens-600x450.jpg
---

## Introduction

Firstly, I would like to greet you a happy happy new year! May you have a prosperous and cheerful 2019. Past few weeks have been quite busy and it has been a while since my last post. In general, 2018 went well for me especially the opportunities to travel with my wife and to learn more about photography.

To start the fresh new year, I would like to create a light and fun post with regard to photography. Most interchangeable-lens cameras being sold on the market are accompanied with a lens that will let you shoot right out of the box. Those [lenses][kit-lens] are called as kit or starter lenses and often cover most of the focal lengths you will need, from wide to medium telephoto.

<a data-flickr-embed="true" href="https://www.flickr.com/photos/oswaldogo/45640793795/in/datetaken-public/" title="What’s Your Favorite Focal Length?"><img src="https://farm8.staticflickr.com/7826/45640793795_a60f27441c_z.jpg" width="640" height="426" alt="What’s Your Favorite Focal Length?"></a>

When I bought my first dedicated camera, the [Fujifilm X-A10](/photography/buying-my-first-camera-fujifilm-xa10/), it came with a 16-50mm kit lens. While for my wife's [Canon 550D][canon-550d], the camera came with the 18-55mm lens. We have used them on our trips and got satisfying results.

**Note:** Having a kit lens should not hinder you from taking beautiful photos. Keep shooting and practice your composition skills for a better foundation.
{: .notice--warning}

People might say that upgrading your kit lens to a good affordable prime lens can give you sharper and more beautiful photos. If you feel that you have already outgrown your kit lens and want something more, upgrading to a faster and affordable prime lens can be a great option. But, this upgrade have some drawbacks that might lead you to just leaving your new lens at home.

## Problem

A prime lens has a fixed focal length as compared to the usual kit lens with variable focal lengths. Flexibility of zoom lenses is very handy because you can compose more even when just standing at one place. For prime lenses, you need to move your feet in order to achieve your desired composition for farther/nearer subjects.

**Tip:** Moving your feet for composition can be a benefit rather than a consequence because there are times when you will see a different perspective that is better than the composition you foresee.
{: .notice--info}

Another problem, a bigger one, is when you do not know the focal length you want to use. You might have heard many people say that you need to buy the affordable 50mm prime lens, a.k.a. the Nifty-Fifty, as your second lens. But, some people will say that the Nifty-Fifty is too tight especially for crop sensor cameras. Head below to learn about determining your favorite focal length for your first prime lens.

## Solution

Remember my [post](/photography/how-to-modify-photos-metadata-using-exiftool/) before on how I used [ExifTool][exiftool] to modify the metadata of my photos especially the focal length? Now, we will still use ExifTool but for data gathering purposes. Assuming that you already have some photo dumps from your past shoots, we will use those photos to know your frequently used focal lengths.

### Data Gathering via ExifTool

1. Download and install ExifTool (*may follow the instructions [here][install-instructions]*)

    **ProTip:** For Mac users with Homebrew, you may get ExifTool via `brew install exiftool`
    {: .notice--info}

2. After the installation, open your favorite console emulator.

3. Go to some directory for placing the retrieved data.

    ```bash
    cd ~/Documents/
    ```

4. Execute the following command to list the `FocalLength` property of all the image files inside the directory.

    ```bash
    exiftool -FocalLength -csv -t -r ~/Pictures/album-to-process > focal-lengths.csv
    ```

5. After ExifTool finishes processing the directory, it will generate a `.csv` file while displaying how many images were processed.

    ```bash
    1 directories scanned
    1092 image files read
    ```

### Data Analysis via Google Sheets

After gathering data, let us find some meaningful information

1. Open the .csv output file of ExifTool in [Google Sheets][google-sheets]

    | SourceFile                              | FocalLength                 |
    | --------------------------------------- | --------------------------- |
    | ~/Pictures/album-to-process/IMG001.JPG  | 16.0 mm                     |
    | ~/Pictures/album-to-process/IMG002.JPG  | 35.0 mm                     |
    | ~/Pictures/album-to-process/IMG003.JPG  | 50.0 mm                     |

2. Click on the `FocalLength` header

3. Click `Insert` -> `Chart`

![image-center](/assets/img/blog/cameras/focal-length-summary-700x433.png "Focal Length Summary"){: .align-center}

**Tip:** You may sort the `FocalLength` column for better visualization of ascending focal lengths.
{: .notice--info}

## Conclusion

Based from the chart above, the most frequent focal length I use is 16mm, which is relatively wide even for a crop sensor camera. I can say that I really love to take pictures using a wide angle lens because I love nature and landscapes. The solution I provided is not 100% foolproof as there are many factors that can easily affect your data.

1. Location / Genre - Some places are more scenic but depending on your location, you might need to zoom more. For people who love shooting portraits, they might be also zooming more to have a compressed shot.

2. Garbage Images / Test Shots - It is best to process only albums that are properly curated because not all shots are usable and will probably just skew the data.

3. Conscious Decision - You might have noticed that 35mm and 50mm succeeded 16mm from the chart. This is because I want to shoot using these fixed focal lengths to have a feel of prime lenses.

I hope this method can help you understand more about your shooting style and preferences. If you do not have some backing data for analysis, I believe item #3 is the best way to try out specific focal lengths. This can greatly help you decide in purchasing your new lens. Cheers!

*P.S. I mentioned, at the start of the article, that this post is a fun one. This is quite shallow but for me, trying to integrate different fields, even just the basic concepts, is very enjoyable.*

<script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

[kit-lens]: https://en.wikipedia.org/wiki/Kit_lens
[fuji-xa10]: http://www.fujifilmph.com/x-series/x-mirrorless-digital-camera/x-a10
[canon-550d]: https://en.wikipedia.org/wiki/Canon_EOS_550D

[exiftool]: https://www.sno.phy.queensu.ca/~phil/exiftool/
[install-instructions]: https://www.sno.phy.queensu.ca/~phil/exiftool/install.html
[google-sheets]: https://sheets.google.com