# [Guide] How to Downgrade Apps on AppStore with iTunes 12.6.5 & Charles Proxy (no Jailbreak).

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
- **iTunes 12.6.5 only works on Windows**. Apple killed iTunes 12.6.5 on macOS. Even if you manage to get iTunes 12.6.5 on your Mac, the download feature will not work.
- The Guide seems complicated, but it's very easy to follow. Plus, you only need to do Step 1, 2, and 3 for the first time (There are 5 steps in total).
- Jailbreak is **NOT** needed. Since the iPA comes directly from iTunes, it's encrypted and can be installed without Sideload. The IPA is 100% legit!
- You can get the old version of any apps as long as that version is still **available** on AppStore.
***

# II. Requirements
- **iTunes 12.6.5** - the latest version of iTunes that supports download apps. Download: [Apple (archive)](http://web.archive.org/web/20171009185131if_/https://secure-appldnld.apple.com/itunes12/091-33626-20170922-F51D3530-A003-11E7-8324-03D19A97A551/iTunes64Setup.exe)/ [backup](https://27man-my.sharepoint.com/:u:/g/personal/qn____27man_onmicrosoft_com/EeTCq3PxQGxEt0HH4CWb9loB_poQsJFiqgxoqlKGUPXR2Q?e=BOwGm2).
- **A Windows machine**: Windows XP/7/10/11 are supported.
- **Charles Proxy**: I use version 4.2.7 but I don't think it matters (No need to _crack_ Charles Proxy). [Download here](https://www.charlesproxy.com/assets/release/4.2.7/charles-proxy-4.2.7-win64.msi)/ [back up](https://www.dropbox.com/s/nrp4obp0ctcwn9e/Charles%20Proxy%204.2.7.rar?dl=0)
- **An Apple ID for iTunes**: Use a spare ID if you like. Keep in mind that if you switch to another ID, you'll need to re-do the process from [Step 3](#step-3-create-the-breakpoint).
***

# III. Getting Started
## Step 1. Preparing
- Nothing special about Charles Proxy so I'll focus on iTunes. 
- After you install iTunes succesfully, go to **`Edit > Preferences > Avanced`** > Untick **`Check for new software updates automatically`** to prevent iTunes from asking for update.
- If you get an error about **Library.itl** when opening iTunes: Go to **`C:\Users\Username\My Music\iTunes\`** and delete the existed **Library.itl**
- Login to iTunes with your prepared Apple ID: **`Account > Sign-in`**.
- The **`Build version number`** (or `Build Number`) of the version you want to downgrade. You can get the `Build version number` of most apps on AppStore from [Tool Lantency](https://tools.lancely.tech/apple/app-search).
![Tool Lancety](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/IMG_1823.PNG)
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
- If the app is removed from AppStore, but still available in your **Purchased tab**: it can be found in **`Account > Purchased`**.
![6BD0iOX](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/6BD0iOX.png) 

### Step 3.3. 
- Select **`Get`** or **`Download`** to download **Facebook**. This is not the version we want so we'll delete it.
![P1oxyj](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/P1oxyj.png)

### Step 3.4. 
- Now, go to **Charles Proxy**, we'll see a list of domains. Find a domain that has a form of **`p**-buy.itunes.apple.com`**, **`**`** is two-random numbers. As you can see in the picture below, mine is **`p31-buy.itunes.apple.com`**. Right-click on it and select **`Enable SSL Proxying`**
![Z8ONSO](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/Z8wONSO-1024x546.jpg)

### Step 3.5. Enable the Breakpoint
- Go back to iTunes and download Facebook again. This is still not a version we want, so we'll delete it.
- In **Charles Proxy**, you'll see a new **`p31-buy.itunes.apple.com`** address **with the blue icon at the top of the line**. Expand this address to **`buyProduct`**, and then follow the pictures:
![zH1Lh](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/zH1LhHX-1024x548.png)
![O3gX5](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/O3gX5aL.png)
![kypYS2J](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/kypYS2J.png)
![hBwS](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/hBwSXT7.png)
***


## Step 4. Get the old version of the appplication (IPA)
### _Note: You ONLY need to do the first 3 steps once. Next time you downgrade an app, you'll start from this step (Step 4)._
- Go back to iTunes and download Facebook, again! **Charles Proxy** will automatically show the **Breakpoint popup**. 
- **Edit Request** > **XML Text** > Replace the current `Build Number Version` of Facebook with the `Build Number` of **Facebook v161.0** (`826067593`) > **Execute** > **Execute**. Now iTunes will download **Facebook v161.0** instead of the latest version.
- In some cases, the **Breakpoint popup** can appear twice, simply edit the current `Build Number Version` like above one more time and you're good to go.

> But how do I know the `Build Number` of **Facebook v161.0** is `826067593`? - Read [Preparing Section](#preparing) carefully!

![WiiLTTo](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/WiiLTTo.png)
![fb161](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/qv0mzsp.png)
***


## Step 5. Install the IPA
- The IPA will be saved at **`C:\Users\<User>\Music\iTunes\iTunes Media\Mobile Applications`**. _**Tips:**_ Open the IPA in Explorer by going to **`iTunes > Library > Right-click on the app > Open in Explorer`**
![GcbjR](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/GcbjRwn.png)

### 5.1. Windows

_**It is a pain in the neck to install the IPA via iTunes. That's why we will not iTunes. AppManager & 3uTools & iMazing are good alternatives.**_

- **[AppManager](https://github.com/kawaiizenbo/AppManager) (recommended)**: Plug your device into your PC, click on **`Install new`** and select the IPA.
![image](https://user-images.githubusercontent.com/52943116/160886525-868d249d-d1e8-431b-af16-215696f4eaec.png)

- **3uTools (may not safe, not recommended)**: Drag & drop the IPA into the Apps tab.
![3u](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/1534755814062064808.gif)

- **iMazing**: **`Manage Apps > Device Tab > Drag & Drop the IPA into the window.`** _(Note: iMazing **does** work on Windows, but I'm too lazy to setup iMazing on Windows just for 2 screenshots)._
![iMazing](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/IMG_1832.PNG)

### macOS
Simply Airdrop the IPA from your Mac to your device. You can use [Apple configurator 2](https://apps.apple.com/us/app/apple-configurator-2/id1037126344) to install the IPA as well.

![Mac](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/Screen%20Shot%202021-09-20%20at%2009.22.02.png)



# IV. FAQ
## 1. I can't see the Build number of the version I need on Tool Lantency?
- The easiest way to get the Build version number is to ask a jailbroken user who has AppStore++ installed. Just tell them the app & the version you need to get.
- If you have nobody to ask, you could try this way. It will take a while depending on your luck. https://github.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/issues/8#issuecomment-1272240225
- Still can't find the Build version number? Well, open a new issue, I will help you.

## 2. Can I share the IPA with my friends?
- **Absolutely yes!** However, you have to give them the IPA **with the Apple ID you used to get the IPA**. Why? Because the first time they open your app, they will be asked to enter the purchased ID. That's how iOS works.
- Don't want to share your main account? Use a clone Apple ID then.

## 3. Can Apple revoke my IPA?
- **No, they can't!** If you use iOS long enough, I'm sure you remember that time when we can download IPA directly from iTunes. Our IPAs came from iTunes just like an app from AppStore. Apple can do nothing about it.

## 4. Can the app be able to receive push notifications?
- Again, the IPA comes from iTunes, which is the same as AppStore... So **YES**, it works like an app from AppStore.

## 5. I got errors installing the IPA via AltStore/Sideloadly/...
- The IPA is **encrypted** with your purchase ID. You **CAN NOT** sideload it. I mentioned how to install the ipa in [Step 4](#step-4-get-the-old-version-of-the-appplication-ipa).
_(FYI: you only sideload **decrypted** IPA. You DO NOT sideload **encrypted** IPA!)._

## 6. Can I install the IPA from iTunes via Filza?
- Yeah, you can install the IPA using Filza.

## 7. What happens if I use another Apple ID?
- You have to re-start the process from [Step 3](#step-3-create-the-breakpoint).

## 8. Apps crash on openning?
- Most likely the version is too old and not compatible with your current iOS/iPadOS anymore.

## 9. How do I remove Charles Proxy Certificates?
- Open **Run** window (Windows + R) and type in `certmgr.msc`
- In the **certmgr** window, go to **Trusted Root Certification Authorities** - **Certificates** - Right click on **Charles Proxy CA** certificate and delete it. 
![image](https://user-images.githubusercontent.com/52943116/144748946-435e88eb-56da-4574-b112-795f63440e1c.png)

## 10. Is it possible to install the IPA without a computer?
- **Yes, it is 100% possible!**. However, it requires more additional Steps. I may add it in the future. 
