---
title: "Replicating Lightroom Mobile Defaults in Raw Therapee - Can this be achieved?"
excerpt: "Are you also a Lightroom Mobile user wanting to edit on a desktop computer? Check how I try to replicate the default output of Adobe Lightroom using Raw Therapee."
toc: true
toc_label: "Table of Contents"
categories:
- photography
tags:
- technology
- software
- adobe
- lightroom
- raw therapee
- editing
- user experience
- color grading
- photo editing
- digital photography
splash_teaser: /assets/img/blog/photography/raw-therapee/sooc-lightroom-rawtherapee-compare-600x450.jpg
---

## Introduction

Few years have passed, I want to know the improvements in [Raw Therapee][rawtherapee] and see if I should now edit using my desktop computer.

Well, there's great news! The problem about the default washed out images I mentioned in my [old post][lr-workflow-post] has already been updated in versions 5.4 and above.

**Note:** Verion 5.4 has been released last 20-March 2018. I am so late! (-_-)
{: .notice}

Based on its documentation [here][rawtherapee-defaults], the software now uses the "Auto-Matched Curve" profile instead of "Neutral" for raw files. The initial state of the imported image will look like your SOOC (_"Straight Out of Camera"_) JPEG.

<figure>
  <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-default.jpg"
       alt="Image exported using Raw therapee default">
  <figcaption>Default JPEG output of Raw Therapee</figcaption>
</figure>

The output of the default profile of Raw Therapee looks nice. But, how does it compare to the output of my camera and the default of [Adobe Lightroom][lightroom]?

## Comparison - Defaults

The default output of Raw Therapee does not fully mimic the SOOC shot. It looks brighter with green tint. Skin tone is on the yellowish side and the browns look more orangy. I also noticed that the image is smoother which have less details but with less noise.

On the other hand, Lightroom's output is more similar to the SOOC image. It is just a bit brighter and saturated. Skin tone looks more natural with a bit of magenta tint. It also looks grainier which is likely due to a brighter image.

<figure class="third">
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-sooc.JPG">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-sooc.JPG"
         alt="Image straight out of camera">
  </a>
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-lightroom-default.jpg">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-lightroom-default.jpg"
         alt="Image exported using Adobe Lightroom Mobile">
  </a>
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-default.jpg">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-default.jpg"
         alt="Image exported using Raw therapee default">
  </a>
  <figcaption>(L to R) Camera SOOC, Lightroom Mobile, and Raw Therapee.</figcaption>
</figure>

Have you noticed the similarities and differences I mentioned above? Feel free to comment if you've noticed other discrepancies.

**Note:** I am using a modified neutral profile for my camera that's why the SOOC shot is quite flat.
{: .notice}

## Raw Therapee - Settings

Upon checking other default settings, I noticed that "Noise Reduction" is enabled in Raw Therapee by default. Maybe this is the answer for the lack of detail issue.

Also, I recently found out that Raw Therapee supports custom color profiles and these profiles are included in the [Adobe DNG Converter][dng-converter] software.

I wonder if these settings are sufficient enough to replicate the default output Adobe Lightroom. Let's try applying the tweaks using the steps below.

### Steps

1. Download and install [Adobe DNG Converter][dng-converter]

2. Check the existence of the folder below

    ```
    %ALLUSERSPROFILE%/Adobe/CameraRaw/CameraProfiles/Adobe Standard
    ```

3. Find the `.dcp` file of your camera (if supported)

    ```
    %ALLUSERSPROFILE%/Adobe/CameraRaw/CameraProfiles/Adobe Standard/Canon EOS M50 Adobe Standard.dcp
    ```

4. Run the Raw Therapee application

5. Using the File Browser tab, Browse the raw image to edit

6. Open the image > Editor tab will be displayed

7. Set the custom camera profile

    - Go to the Colors tab
    - Find the Camera Management section
    - Click Custom > click the browse button
    - Choose the `.dcp` file from step #3.
    - Click Open

        ![image-center](/assets/img/blog/photography/raw-therapee/raw-therapee-camera-profile-settings.png "Custom Color Profile"){: .align-center}

    **Note:** For the complete details about DCP, you may check their documentation [here][rawtherapee-dcp].
    {: .notice}

8. Disable Noise Reduction

    - Click the Detail section
    - Find the Noise Reduction section
    - Click the "power" button to toggle

        ![image-center](/assets/img/blog/photography/raw-therapee/raw-therapee-noise-reduction-settings.png "Toggle Noise Reduction"){: .align-center}

9. Export the image

## Output - Final

<figure>
  <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-adobe-standard-no-nr.jpg"
       alt="Image exported using Raw therapee with Adobe Standard Profile">
</figure>

In my opinion, the new Raw Therapee output is way way better than its default. Grains and details are already visible. Greenish tint is gone and skin tone looks more natural. 

For the browns, they look less orangy now. But when compared again to Lightroom, the shade is still far off. Brightness difference is very minor and can easily be adjusted.

<figure class="third">
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-default.jpg">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-default.jpg"
         alt="Image exported using Raw therapee default">
  </a>
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-adobe-standard-no-nr.jpg">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-raw-therapee-adobe-standard-no-nr.jpg"
         alt="Image exported using Raw therapee with Adobe Standard Profile">
  </a>
  <a href="/assets/img/blog/photography/raw-therapee/coffee-watch-lightroom-default.jpg">
    <img src="/assets/img/blog/photography/raw-therapee/coffee-watch-lightroom-default.jpg"
         alt="Image exported using Adobe Lightroom Mobile">
  </a>
  <figcaption>(L to R) Raw Therapee (Default), Raw Therapee (Adobe DCP), and Lightroom Mobile</figcaption>
</figure>

## Conclusion

Replicating the exact output as Lightroom can not easily be done with few change of settings. Further adjustment of colors is needed to really align them.

With those minor changes, the image really improved a lot especially the skin tone. If you are someone who is not particular with the color differences, or someone who has his/her own presets, using Raw Therapee is definitely a great option.

Will I switch from using Lightroom Mobile (free version) to Raw Therapee? My answer is still a no as my use case hasn't changed since then. I don't process a lot of images and I really love the UX of the mobile app.

Hope you like my small experiment and do suggest some tips if you know other settings to be modified.

Stay safe!

[lr-workflow-post]: /photography/my-photo-editing-workflow-utilizing-adobe-lightroom-mobile/
[rawtherapee]: https://rawtherapee.com/
[rawtherapee-defaults]: https://rawpedia.rawtherapee.com/Sidecar_Files_-_Processing_Profiles#Defaults
[rawtherapee-dcp]: https://rawpedia.rawtherapee.com/How_to_get_LCP_and_DCP_profiles
[dng-converter]: https://helpx.adobe.com/photoshop/digital-negative.html
[lightroom]: https://lightroom.adobe.com/