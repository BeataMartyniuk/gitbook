# Android Emulator

If you do not own an Android device to run our Sandbox app on, you can do it using an emulator.

#### Things you need

* [ ] [bunq Sandbox App APK](https://appstore.bunq.com/api/android/builds/bunq-android-sandbox-master.apk)
* [ ] [Android Studio](https://developer.android.com/studio/index.html)

### Starting the Android Virtual Device \(AVD\) Manager

1. Open **Android Studio**.
2. Find and select _Tools → Android → AVD Manager_ on the top menu.

### Setting up a new virtual device

1. Start the wizard by clicking **+ Create Virtual Device**.
2. Select a device \(we recommend _Pixel 5.0_ or _Nexus 6_\) and press **Next**.
3. Select an x86 system image \(we recommend _Nougat, API Level 25, Android 7.1.1 with Google APIs_\) and press **Next**. The image needs to have Google Play Services 10.0.1 or higher.
4. In the bottom left corner, select **Show Advanced Settings**.
5. Scroll to **Memory and Storage**.
6. Change **Internal Storage** to 2048 MB.
7. Change **SD card** to 200 MB.
8. Press **Finish**.

### Starting the virtual device

1. On the right side under **Actions**, select the green **Play** button.
2. Wait for the device to boot, this may take a few minutes.

### Installing the bunq Sandbox App APK

1. Open the command line.
2. Navigate to your Android SDK platform tools directory \(e.g. `cd ~/Library/Android/sdk/platform-tools` on macOS\).
3. Make sure that the virtual device is started and has fully booted.
4. Run `./adb install ~/Downloads/bunq-android-sandboxEmulator-public-api.apk`. and wait for the success message.

### Creating an account and/or logging in

1. Create a sandbox account in the [developer portal](https://developer.bunq.com/).
2. Log in to the sandbox app using the sandbox user credentials.

{% hint style="info" %}
You will be asked to verify your phone number when you open the app for the first time. Sandbox does not send actual SMS messages. Enter any valid phone number and use the default verification code `992266`. 
{% endhint %}

If you couldn't generate a sandbox account in the developer portal, use Tinker:

1. Install [Tinker](https://beta.doc.bunq.com/quickstart/tinker).
2. Run `tinker/user-overview` to create a sandbox account. The output of the command will include the login credentials for the sandbox account.

{% hint style="warning" %}
It is **NOT** possible to create sandbox accounts using the sandbox app. bunq does not review Sandbox account applications.
{% endhint %}

### Creating a new API key

You can create additional sandbox API keys for the sandbox app. Go _Profile → Security & Settings → Developers → API keys → Add API key_. 

The API key is valid and can be assigned to an IP within 4 hours after its creation. Otherwise, it becomes invalid. API keys that are created via the sandbox app are wiped from the sandbox base with each sandbox reset.

