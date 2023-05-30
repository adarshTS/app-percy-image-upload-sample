# Uploading Screenshots from a Folder

This repo helps to understand the folder structure for image upload. 


## Step 1

```
Download this script that helps you upload images directly to Percy:
https://github.com/percy/example-percy-appium-js/blob/ninad/manual-upload-poc/manual/manual_upload.js
```

## Step 2
export your PERCY_TOKEN into your local or CI environment.

## Step 3
Setup your images in the below folder structure

Folder Structure

```
.resources/
    device1/
        image1.png
        image2.png
        device.json
    device2/
        image1.png
        image2.png
        device.json
```
You can have arbitrary device names.

Your device.json should look like this, for a sample device:

Sample device.json
```
{
  "deviceName": "OnePlus 8", # Arbitrary
  "os": "Android", # Can be any string
  "osVersion": "10", # can be any string
  "deviceScreenSize": "1080x2400", # Should match your screenshot resolution
  "statusBarHeight": 104, # Helps us automatically ignore any status bar, can be 0
  "navigationBarHeight": 229, # Helps us automatically ignore any navigation bar, can be 0
  "orientation": "portrait"
}
```
## Step 3
Run the test script via 
```
npx percy app:exec -- node manual_upload.js
```