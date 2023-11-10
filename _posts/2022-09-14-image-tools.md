---
layout: post
title: Image Tools
---

# Colors
[Create color palettes](https://coolors.co/)

[Get color from an image](https://imagecolorpicker.com/color-code/02ff00)

[Convert Image to Grayscale](http://www.tlhiv.org/grayscale/)

# SVG Files

[Free SVG Images & Icons](https://svgrepo.com)

[Edit SVGs](https://boxy-svg.com/app)

[Convert SVG to PNG](https://cloudconvert.com/svg-to-png)

# Creating App Store Images
You can add up to 10 screenshots and 3 previews (videos) of your app for the app store. 

To take a screenshot of your device with Xcode, run the app, then select Debug->View Debugging->Take Screenshot of ***'s iPhone. The screenshot will save to your desktop.

Use the screenshots with the [App Store Screenshot Generator](https://studio.app-mockup.com/) to create the images for the app store.

Use screen recording on the iPhone to record your preview.

# Tab Bar Images
Tab bar images can be a system or custom image. 

To use a custom image, you need 3 files: a 25x25, 50x50, and 75x75 pixel png file. Create a new image set with the three files in your "Assets" folder and save as "ImageName". 

```javascript
@State private var selection = 0

TabView(selection: $selection) {
    TestView()
    .tabItem {
        Label("Tab Label", image: "ImageName")
    }
    .tag(1)
}
```

To have the images gray out, [convert the image to gray](http://www.tlhiv.org/grayscale/) then create the 3 files (25x25, 50x50, 75x75). Create a new image set and save as "ImageNameGray".

```javascript
@State private var selection = 0

TabView(selection: $selection) {
    TestView()
    .tabItem {
        Label("Tab Label", image: selection == 1 ? "ImageName" : "ImageNameGray")
    }
    .tag(1)
}
```
