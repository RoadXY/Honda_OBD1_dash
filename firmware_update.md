# How to Update Your Honda Dash Firmware

Updating the firmware on your Honda Dash is simple and can be done wirelessly via your web browser. Follow this guide to download the latest software and flash it to your dash.

---

## 1. How Software Releases Work on GitHub

Whenever a new version of the software is ready, it is published as a **Release**. Think of a release as a stable package containing the latest updates, bug fixes, and features.

To find the latest software:
1. Go to the main repository page: [https://github.com/RoadXY/Honda_OBD1_dash](https://github.com/RoadXY/Honda_OBD1_dash)
2. On the right side of the screen, look for the **Releases** section.
3. Click on the latest version (marked with a green **Latest** tag).
4. Under the **Assets** section of that release, click on **`firmware.bin`** to download the file to your computer or phone.

> ⚠️ **Important:** Do not rename the file! The Honda Dash will only accept a file exactly named `firmware.bin`.

---

## 2. Updating Your Honda Dash

Before you start, make sure your Honda Dash has an **SD card inserted** and that your computer or phone is connected to the same Wi-Fi network as the dash.

### Step 1: Open the Update Page
Open your web browser and navigate to the Honda Dash IP address (or go directly to the `/firmware` page if you are redirecting from the main menu). 

### Step 2: Upload the Firmware to the SD Card
1. Look at the **Status** at the bottom of the card. It should say **Ready**. *(If it says "Please insert SD Card", make sure your SD card is properly pushed in).*
2. Click the file selection button (Choose File) and select the **`firmware.bin`** file you downloaded from GitHub.
3. Click the **UPLOAD TO SD** button.
4. Wait a few moments while the file transfers. The progress bar will show the upload speed. Once completed, the status will turn green and say: **Upload Successful - Ready to Flash**.

### Step 3: Flash the Dash
1. Click the **FLASH FIRMWARE** button.
2. A warning pop-up will appear asking if you want to continue. Click **OK**.
3. The screen will display **Flashing... please wait...**. 
4. Once the update is complete, the Honda Dash will automatically reboot and start running the brand-new software!

---

## Troubleshooting

* **The "Upload to SD" button is greyed out:** Make sure you have actually selected the file first, and ensure the SD card is detected by the dash.
* **Can I select a different file?** No, the system will reject any file that is not explicitly named `firmware.bin`.
* **The update failed mid-way:** Simply refresh the web page, ensure your Wi-Fi connection is stable, and try uploading the file again. Your existing dash software will remain safe until the flashing process successfully finishes.
