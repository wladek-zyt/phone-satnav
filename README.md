# Build a satnav out of an old Android phone
I did this with a Motorola Moto G6(plus) but it should work with most of Android devices.

# Requirements
Download ADB and Fastboot: https://dl.google.com/android/repository/platform-tools-latest-windows.zip
Download Magisk: https://github.com/topjohnwu/Magisk/releases/download/v21.2/Magisk-v21.2.zip
Download TWRP Image: https://eu.dl.twrp.me/evert/twrp-3.5.0_9-0-evert.img.html
Download USB drivers for your phone, Motorola in this case: https://support.motorola.com/us/en/solution/MS88481

# Root the phone
Make sure to take a backup of your entire device data.
First root the phone, if you haven't already:
  1. Allow USB debugging and unlock OEM in the phone settings
    1.1 Go to Settings > System > About phone > tap the build number 5 times untill developer options are unlocked
    1.2 Go to Settings > System > Advanced > Developer options and check OEM unlocking and USB debugging
    1.3 (optionally) click Default USB configuration in the Developer options and set it to File Transfer. This will allow you to transfer files to your phone without having to change it every time you connect the phone to your computer.

Motorola's OEM unlocking is not that simple however, you'll have to follow the following steps to unlock it:
  1.4 Go To Settings -> Dev Settings, And Select "Allow OEM Unlock"
  1.5 Put your device in fastboot mode (power off, then press the power and volume down buttons simultaneously).
  1.6 Go to the Minimal ADB and Fastboot folder and open Command Prompt from there.
  1.7 Connect your Phone to PC
  1.8 Type this in the CMD prompt window: fastboot oem get_unlock_data
  1.9 You will get a return string. Copy the complete string, without the (bootloader) text in between and paste it into a notepad.
  1.10 Now go to https://accounts.motorola.com/ssoauth/login?TARGET=https://motorola-global-portal.custhelp.com/cc/cas/sso/redirect/standalone%2Fbootloader%2Funlock-your-device-b
  1.11 Sign in using your Google account or Motorola ID. Scroll down the page and paste the copied string in the field. Then click on ‘Can my device be unlocked?’, after which a "REQUEST UNLOCK KEY" button will appear at the bottom of page.
  1.12 To get your unlock key, select the ‘I Agree’ option. Note: You will receive an email with your Unlock Key at the email address you used to log in there.
  1.13 Copy the 20-character key that Motorola sent you via email. Make sure your device is connected.
  1.14 Then type: fastboot oem unlock [UNLOCK KEY]. (Replace UNLOCK KEY with the key from the Motorola email).
  1.15 Hit enter, it will ask you to repeat the command to confirm, let it run for a few seconds and after it's done, reboot your phone back into fastboot mode. You'll now see that OEM is unlocked.
  
2. 
