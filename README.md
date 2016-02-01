## Scratch 2.0 Compiled For Mobile
This code has been released under the GPL version 2 license. Forks can be released under the GPL v2 or any later version of the GPL.

Based off of [Scratch 2.0 by MIT](http://scratch.mit.edu): http://scratch.mit.edu

[Scratch Forums Topic](https://scratch.mit.edu/discuss/topic/60012)

### Building
To build Scratch 2.0 for mobile you will need [Ant](http://ant.apache.org/), the [Flex SDK](http://flex.apache.org/) version 4.10+, and [playerglobal.swc files](http://helpx.adobe.com/flash-player/kb/archived-flash-player-versions.html#playerglobal) for Flash Player versions 10.2 and 11.4 added to the Flex SDK.

After downloading ``playerglobal11_4.swc`` and ``playerglobal10_2.swc``, move them to ``<path to flex>/frameworks/libs/player/<version>/playerglobal.swc``. E.g., ``playerglobal11_4.swc`` should be located at ``<path to flex>/frameworks/libs/player/11.4/playerglobal.swc``.

Create a ``local.properties`` file to set the required options. Your ``local.properties`` file may look something like this: 
```
FLEX_HOME=/Users/elfin8er/Downloads/flexsdk
SCRATCH_HOME=/Users/elfin8er/Documents/Programming/ScratchMobile/scratch-flash
android.certificate.password=PASSWORD
ios.certificate.password=1234

bin.ext=.bat
certificates.path=${SCRATCH_HOME}/certificates
ios.provision.path=${certificates.path}/Scratch_iOS.mobileprovision
ios.certificate.path=${certificates.path}/Scratch_iOS.p12
android.certificate.path=${certificates.path}/Scratch_android.p12
```

I have included iOS and Android certificates, but if you'd like to use your own, you can define their locations above. You can create an Android certificate with the following command:

```
keytool -genkey -v -keystore myname.key.p12 -alias alias_name -keyalg RSA -storetype pkcs12 -keysize 2048 -validity 10000
```

Now you can run Ant ('ant' from the commandline) to build a 11.6 SWF, 10.2 SWF, APK, and iPA.

If the source is building but the resulting .swf is producing runtime errors, your first course of action should be to download version 4.11 of the Flex SDK and try targeting that. The Apache foundation maintains an [installer](http://flex.apache.org/installer.html) that lets you select a variety of versions.

Please note that the Scratch trademarks (including the Scratch name, logo, Scratch Cat, and Gobo) are property of MIT. For use of these Marks, please see the [Scratch Trademark Policy](http://wiki.scratch.mit.edu/wiki/Scratch_1.4_Source_Code#Scratch_Trademark_Policy).

### Debugging
Here are a few integrated development environments available with Flash debugging support:
* [Intellij IDEA](http://www.jetbrains.com/idea/features/flex_ide.html)
* [Adobe Flash Builder](http://www.adobe.com/products/flash-builder.html)
* [FlashDevelop](http://www.flashdevelop.org/)
* [FDT for Eclipse](http://fdt.powerflasher.com/)

