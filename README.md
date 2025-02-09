# [Guide] How to Downgrade Apps on AppStore with iTunes 12.6.5 & Charles Proxy (no Jailbreak).

_If you think this guide is useful, considering support me via [Paypal](https://www.paypal.com/paypalme/qnblackcat) <img src="https://img.shields.io/badge/-lightgrey?style=social&logo=paypal" alt="Badge">!_

# Table of Content
* [I. Notes](#i-notes)
* [II. Requirements](#ii-requirements)
* [III. Getting Started](#iii-getting-started)
   * [Step 1. Preparing](#step-1-preparing)
   * [Step 2. Install Charles Root Certificate](#step-2-install-charles-root-certificate)
   * [Step 3. Create the Breakpoint](#step-3-create-the-breakpoint)
   * [Step 4. Get the old version of the appplication (IPA)](#step-4-get-the-old-version-of-the-appplication-ipa)
   * [Step 5. Install the IPA](#step-5-install-the-ipa)
* [IV. FAQ](#iv-faq)


# I. Notes
- **iTunes 12.6.5 only works on Windows**. Apple discontinued iTunes 12.6.5 on macOS. Even if you manage to get iTunes 12.6.5 on your Mac, the download feature will not work.
- The guide seems complicated, but it's very easy to follow. Plus, you only need to do Steps 1, 2, and 3 once (there are 5 steps in total).
- Jailbreak is **NOT** needed. Since the IPA comes directly from iTunes, it's encrypted and can be installed directly, no sideloading. The IPA is 100% legit!
- You can get any version of any app, as long as that version is still **available** on the App Store.
- Supports both iOS and iPadOS apps.
  
# II. Requirements
- **iTunes 12.6.5** - the latest version of iTunes that supports download apps. Download: Apple iTunes 12.6.5.3 - [32bit](https://secure-appldnld.apple.com/itunes12/091-87820-20180912-69177170-B085-11E8-B6AB-C1D03409AD2A5/iTunesSetup.exe) | [64bit](https://secure-appldnld.apple.com/itunes12/091-87819-20180912-69177170-B085-11E8-B6AB-C1D03409AD2A6/iTunes64Setup.exe) | [(backup)](https://27man-my.sharepoint.com/:u:/g/personal/qn____27man_onmicrosoft_com/EeTCq3PxQGxEt0HH4CWb9loB_poQsJFiqgxoqlKGUPXR2Q?e=BOwGm2).
- **A Windows machine**: Windows XP/7/10/11 are supported. You can also use a VM Windows. Tested on an Apple Silicon mac with Paralles Desktop & Windows 11. Boot Camp should work as well.
- **Charles Proxy**: I use version 4.2.7 but I don't think it matters (No need to _crack_ Charles Proxy). [Download here](https://www.charlesproxy.com/assets/release/4.2.7/charles-proxy-4.2.7-win64.msi)/ [back up](https://www.dropbox.com/s/nrp4obp0ctcwn9e/Charles%20Proxy%204.2.7.rar?dl=0)
- **An Apple ID for iTunes**: Use a spare ID if you like. Keep in mind that if you switch to another ID, you'll need to re-do the process from [Step 3](#step-3-create-the-breakpoint).
***

# III. Getting Started
## Step 1. Preparing
- Nothing special about Charles Proxy, so I'll focus on iTunes.
- After you install iTunes successfully, go to **`Edit > Preferences > Advanced`** and untick **`Check for new software updates automatically`** to prevent iTunes from asking for updates.
- If you get an error about **Library.itl** when opening iTunes: Go to **`C:\Users\Username\My Music\iTunes\`** and delete the existing **Library.itl**.
- Log in to iTunes with your prepared Apple ID: **`Account > Sign-in`**.
- The **`Build version number`** (or `Build Number`) of the version you want to downgrade:
  - Method 1: You can get the `Build version number` of most apps on the App Store from [ipafilezone](https://ipafilezone.com/) or [Appstore.bilin (backup)](https://appstore.bilin.eu.org/).
    ![Screen Shot 2023-10-22 at 21 23 50](https://github.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/assets/52943116/7e45d260-dbe9-4d6c-b744-ef4a12c12132)

  - Method 2: Ask a jailbroken user who has AppStore++ installed to get the `Build version number` for you.
  - Method 3: Look at the `buyProduct` content and search for `softwareVersionExternalIdentifier`. The very bottom line is equal to the latest version. Keep trying until you succeed.
  - Method 4: Almost the same as Method 3. See [here](https://github.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/issues/8#issuecomment-1272240225).
***


## Step 2. Install Charles Root Certificate
![0](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/0.png)
![13](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/13.png)
![456](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/456.png)
![7](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/7.png)

_**Congrats! You just installed Charles Proxy Certificate! See the FAQ section for how to remove the Charles Proxy Certificate if you don't need it anymore**_
***


## Step 3. Create the Breakpoint

_(This is where the fun begins!)_

### Step 3.1. Open iTunes & Charles Proxy
![ikSFiKO-1024x545](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/ikSFiKO-1024x545.jpg)

### Step 3.2.
- Search for the app you want to downgrade. I will get the IPA of **Facebook v161.0** as an example.
- If the app is removed from the App Store but still available in your **Purchased tab**, it can be found in **`Account > Purchased`**.
![6BD0iOX](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/6BD0iOX.png)

### Step 3.3.
- Select **`Get`** or **`Download`** to download **Facebook**. This is not the version we want, so we'll delete it.
![P1oxyj](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/P1oxyj.png)

### Step 3.4.
- Now, go to **Charles Proxy**, and you'll see a list of domains. Find a domain that has a form of **`p**-buy.itunes.apple.com`**, where **`**`** represents two random numbers. As you can see in the picture below, mine is **`p31-buy.itunes.apple.com`**. Right-click on it and select **`Enable SSL Proxying`**.
![Z8ONSO](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/Z8wONSO-1024x546.jpg)

### Step 3.5. Enable the Breakpoint
- Go back to iTunes and download Facebook again. This is still not the version we want, so we'll delete it.
- In **Charles Proxy**, you'll see a new **`p31-buy.itunes.apple.com`** address **with a blue icon at the top of the line**. Expand this address to **`buyProduct`**, and then follow the pictures:
![zH1Lh](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/zH1LhHX-1024x548.png)
![O3gX5](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/O3gX5aL.png)
![kypYS2J](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/kypYS2J.png)
![hBwS](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/hBwSXT7.png)

***


## Step 4. Get the old version of the appplication (IPA)
### _Note: You only need to do all the previous steps once. Next time you downgrade an app, you'll start from this step (Step 4)._
- Go back to iTunes and download Facebook again! **Charles Proxy** will automatically show the **Breakpoint popup**. 
- **Edit Request** > **XML Text** > Replace the current `Build version number` of Facebook with the `Build Number` of **Facebook v161.0** (`826067593`) > **Execute** > **Execute**. Now iTunes will download **Facebook v161.0** instead of the latest version.
- In some cases, the **Breakpoint popup** can appear twice. Simply edit the current `Build version number` like above one more time, and you're good to go.

> But how do I know the `Build version number` of **Facebook v161.0** is `826067593`? - Read the [Preparing Section](#preparing) carefully 😉

![WiiLTTo](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/WiiLTTo.png)
![fb161](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/qv0mzsp.png)
***

## Step 5. Install the IPA
<details>
  <summary><strong>5.1. Windows</strong></summary>
  
  - [**AppManager**](https://github.com/kawaiizenbo/AppManager) (recommended): Plug your device into your PC, click on **`Install new`** and select the IPA.
    ![AppManager](https://user-images.githubusercontent.com/52943116/160886525-868d249d-d1e8-431b-af16-215696f4eaec.png)

  - **iMazing**: **`Manage Apps > Device Tab > Drag & Drop the IPA into the window.`**  
    _(Note: iMazing **does** work on Windows, but I'm too lazy to set up iMazing on Windows just for two screenshots)._  
    ![iMazing](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/IMG_1832.PNG)

  - **3uTools (may not be safe, not recommended)**: Drag & drop the IPA into the Apps tab.  
    ![3uTools](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/1534755814062064808.gif)
</details>

<details>
  <summary><strong>5.2. macOS</strong></summary>
  
  - If the Apple ID used to download apps on iTunes and the Apple ID used on your iPhone are the same, simply Airdrop the IPA to your phone to install it.
  
  - Otherwise, you can use [Apple Configurator 2](https://apps.apple.com/us/app/apple-configurator-2/id1037126344) to install the IPA.  
    ![Mac](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/Screen%20Shot%202021-09-20%20at%2009.22.02.png)
</details>

<details>
  <summary><strong>5.3. I don't have a computer (seriously?)</strong></summary>
  
  1. Upload the iPA to a cloud storage that supports direct URL generation (Ex: Dropbox, archive.org, MySharePoint...).  
  
  2. Go to [Manifest.plist Generator](https://qnblackcat.github.io/Manifest-Generator/) to generate a Manifest.plist. Upload & get its direct url.  
  
  3. Go to [itms Generator](https://qnblackcat.github.io/Manifest-Generator/) to create an iPA installation link _(You must open the link in Safari)._  
</details>

# IV. FAQ
## 1. I can't see the Build number of the version I need on either ipaarchive or Appstore.bilin?
- The easiest way to get the Build version number is to ask a jailbroken user who has AppStore++ installed. Just tell them the app and the version you need.
- If you have nobody to ask, you could try this way. It will take a while depending on your luck. [More details here](https://github.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/issues/8#issuecomment-1272240225).
- Still can't find the Build version number? Well, open a new issue, and I will help you. You must include the AppStore's URL of the app.

## 2. The app forces me to update to use it!
- There's not much you can do in this situation (unless you're jailbroken). You probably have to update it.

## 3. How to prevent Appstore auto update for the downgraded app?
- This requires Apple Configurator, so macOS only. See: https://github.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/issues/26

## 4. Can I share the IPA with my friends?
- **Absolutely yes!** However, you have to give them **the Apple ID you used to get the IPA**. Why? Because the first time they open your app, they will be asked to enter the purchased ID.
- Don't want to share your main account? Use a clone Apple ID then.

## 5. Can Apple revoke my IPA?
- **No, they can't!** If you have used iOS long enough, you might remember the time when we could download IPA directly from iTunes. Our IPAs came from iTunes just like an app from the App Store. Apple can do nothing about it.

## 6. Can the app receive push notifications?
- Again, the IPA comes from iTunes, which is the same as the App Store... So **YES**, it works like an app from the App Store.

## 7. I got errors installing the IPA via AltStore/Sideloadly/...
- The IPA is **encrypted** with your purchase ID. You **CAN NOT** sideload it. I mentioned how to install the IPA in [Step 5](#step-5-install-the-ipa).
_(FYI: you only sideload **decrypted** IPA. You DO NOT sideload **encrypted** IPA!)._

## 8. Can I install the IPA from iTunes via Filza?
- Yes, you can install the IPA using Filza.

## 9. What happens if I use another Apple ID?
- You have to restart the process from [Step 3](#step-3-create-the-breakpoint).

## 10. Apps crash on opening?
- Most likely the version is too old and not compatible with your current iOS/iPadOS anymore.

## 11. How do I remove Charles Proxy Certificates?
- Open the **Run** window (Windows + R) and type in `certmgr.msc`.
- In the **certmgr** window, go to **Trusted Root Certification Authorities** - **Certificates** - Right-click on the **Charles Proxy CA** certificate and delete it. 
![image](https://user-images.githubusercontent.com/52943116/144748946-435e88eb-56da-4574-b112-795f63440e1c.png)

## 12. Is it possible to install the IPA without a computer?
- [Yes, it is (Step 5.1)](#53-i-dont-have-a-computer-seriously)
  
