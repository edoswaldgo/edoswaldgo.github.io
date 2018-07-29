---
title: "How to Modify Metadata of Your Photos Using ExifTool"
excerpt: "Guide on how to modify metadata of your beautiful photos using ExifTool."
categories:
- photography
tags:
- tools
---

## Introduction

Early this year, I got my first camera with a 16-50mm kit lens to start learning more about photography. I did not borrow the camera of my wife as she's using it during trips. As months pass, while taking more and more photos, I wondered how faster and shorter lenses behave.

I bought relatively affordable lenses but with some consequences. The lenses are full manual and the camera wouldn't be able to communicate with them. Information like aperture and focal length will not be detected automatically. On my camera, the focal length can be set manually but I eventually encountered a trivial problem.

**Try it out:** Take pictures using a prime lens and focus manually. The experience is very engaging and quite fun!
{: .notice}

## Problem

I initially set my camera's focal length setting to 12mm given that I am using a full manual lens. But from time to time, I have been changing the lens of my camera to 35mm depending on the subject. Upon changing lenses, I forgot to update my camera settings to the actual focal length of the lens. All the photos that I have taken resulted to have 12mm focal length on their Exif metadata.

I only noticed this discrepancy after uploading some of the photos to [Flickr][flickr]. Below is one of the images that have incorrect Exif metadata. If you will view the image in Flickr, you will notice that the `Lens Model` is set to `12.0 mm` but I really took the shot using a 35mm lens.

<a data-flickr-embed="true" data-header="true" href="https://www.flickr.com/photos/oswaldogo/29404044238/in/datetaken-public/" title="Rest, Shoot, Tweak"><img src="https://farm2.staticflickr.com/1810/29404044238_17277f29a2_z.jpg" width="640" height="427" alt="Rest, Shoot, Tweak"></a>

## Solution

In order not to further spread false information, I tried to find a tool that can modify metadata of images. My main objective is to clear the value of the `FocalLength` and `LensModel` properties of all the images. I found a great tool named [ExifTool][exiftool]. This free software is created by Phil Harvey and is platform independent. Below are the steps I made in order to address the issue.

1. Download and install ExifTool (*may follow the instructions [here][install-instructions]*)

    **ProTip:** For Mac users with Homebrew, may get ExifTool via `brew install exiftool`
    {: .notice--info}

2. After the installation, open your favorite console emulator.

3. Go the directory containing the images to be converted.

    ```bash
    cd ~/Pictures/photos-to-process
    ```

4. Execute the following command to clear the `FocalLength` and `LensModel` properties of all the `JPG` files in the directory.

    ```bash
    exiftool -EXIF:FocalLength= -EXIF:LensModel= *.JPG
    ```

5. ExifTool will replace the files with the processed ones. But, the tool will also produce backups having `_original` as suffix.

6. Voila! You may now upload and/or share your photos, like the one below!

<a data-flickr-embed="true" data-header="true"  href="https://www.flickr.com/photos/oswaldogo/28405562707/in/datetaken-public/" title="Super Friendly Huntaway!"><img src="https://farm2.staticflickr.com/1784/28405562707_52a78b1514_z.jpg" width="640" height="427" alt="Super Friendly Huntaway!"></a>

**Note:** List of available Exif tag names are available [here][exif-tags] in case you need to alter other properties.
{: .notice}

Cheers!

<script async src="https://embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

[exiftool]: https://www.sno.phy.queensu.ca/~phil/exiftool/
[install-instructions]: https://www.sno.phy.queensu.ca/~phil/exiftool/install.html
[exif-tags]: https://www.sno.phy.queensu.ca/~phil/exiftool/TagNames/EXIF.html
[flickr]: https://www.flickr.com/