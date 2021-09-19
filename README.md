# [Guide] How to Downgrade apps on AppStore with iTunes 12.6.5 & Charles Proxy (no Jailbreak).

# Table of contents
[I. Notes](#Notes)

[II. Requirements](#requirements)

[III. Get Started](#getintoit)

[1. Preparing](#preparing)

[2. Install Charles Proxy Cerfificate](#cert)

[3. Create the Breakpoint](#breakpoint)

## I. Notes
<a name="Notes"/>

- The Guide seems complicated, but you only need to do Step 1,2, and 3 for the first time. There are 5 steps in total.

- Jailbreak is **NOT** needed. Since the iPA comes directly from iTunes, it's encrypted and can be installed without Sideload. The IPA is 100% legit.

- You can get the old version of any apps on AppStore as long as that version is still **available** on AppStore.


## II. Requirements
<a name="requirements"/>

- **iTunes 12.6.5** - the latest version of iTunes that supports download apps. Download here (directly from Apple).

- **A Windows machine**: Windows XP/7/10 are supported, not tested on Windows 11 yet.
 
> _(Why Windows only? - Apple killed iTunes 12.6.5 on macOS. Even if you manage to get iTunes 12.6.5 on your Mac, the download feature will does not work.)_

- **Charles Proxy**. I use version 4.2.7 but I don't think it's matter. _(No need to crack Charles Proxy)_

- **An Apple ID for iTunes**. Use a clone ID if you like. Keep in mind that if you switch to another ID, you'll need to re-do the process from **Step 3**.


## III. Get Started
<a name="getintoit"/>

### Step 1. Preparing
<a name="preparing"/>

- Nothing special about Charles Proxy so I'll focus on iTunes. 

- After you install iTunes succesfully, go to **Edit** => **Preferences** => **Avanced** => Untick **Check for new software updates automatically** to prevent iTunes from asking for update.

- If you get an error about **Library.itl** when opening iTunes: Go to `“C:\Users\Username\My Music\iTunes\”` and delete the existed **Library.itl**

- Login into iTunes with your prepared Apple ID: **Account** => **Sign-in**

- The `Build Number Version` of the version you want to downgrade. You can get the `Build number Version` of most apps on AppStore from [Tool Lantency](https://tools.lancely.tech/apple/app-search). See more info in pictures below:

![Tool Lancety](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/IMG_1823.PNG?token=AMT5SDEBOBFHPY4G6ALGM4LBI5UTS)



### Step 2. Install Charles Root Certificate
<a name="cert"/>

![0](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/0.png?token=AMT5SDFKVCRKB4PGVVLR6C3BI5MC2)

![13](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/13.png?token=AMT5SDGTO6FMC6RW4EIUDMDBI5ML4)

![456](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/456.png?token=AMT5SDHI6TXASLZWYCK4P7TBI5MNG)

![7](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/7.png?token=AMT5SDCWPGO3QNE5PZGVDKDBI5MOO)

_**Congrats! You just installed Charles Certificate!**_


### Step 3. Create the Breakpoint
<a name="breakpoint"/>

_(This is where the fun begins!)_

1. Open iTunes & Charles Proxy

![ikSFiKO-1024x545](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/ikSFiKO-1024x545.jpg?token=AMT5SDF4V3P7IVAFNXIN7CDBI5M7W)


2. Search for the app you want to downgrade. I will get the IPA of **Facebook v161.0** as an example

![6BD0iOX](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/6BD0iOX.png?token=AMT5SDEVMAEZ6B5EYCQBTFDBI5NFG) 


3. Select **Get** or **Download** to download **Facebook**. This is not the version we want so we'll delete it.

![P1oxyj](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/P1oxyj.png?token=AMT5SDHQKSAOUXZ635PZ3D3BI5QGC)


4. Now, go to **Charles Proxy**, we'll see a list of domains. **Find a domain that has a form of** `“p**-buy.itunes.apple.com”`, `**` is two-random numbers. As you can see in my picture below, mine is `“p31-buy.itunes.apple.com”`. Right-click on it and select **Enable SSL Proxying**

![Z8ONSO](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/Z8wONSO-1024x546.jpg?token=AMT5SDFEU4H3S5UVZIUAQLDBI5QTA)


5. Enable the Breakpoint

- Go back to iTunes and download Facebook again. This is still not a version we want, so we'll delete it.

- In Charles Proxy, you'll see a new `p31-buy.itunes.apple.com` address **with the blue icon at the top of the line**. Expand this address to `buyProduct`. And then following the pictures:

![zH1Lh](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/zH1LhHX-1024x548.png?token=AMT5SDAXHVTPANC2Q2C45HTBI5RX2)

![O3gX5](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/O3gX5aL.png?token=AMT5SDHWWLCK4242LXDSRMDBI5SHY)

![kypYS2J](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/kypYS2J.png?token=AMT5SDGEUFW2UVKEVVFY273BI5SJG)

![hBwS](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/hBwSXT7.png?token=AMT5SDBSBYK6WN7F6ODU4MLBI5SOK)


### Step 4. Get the old version of the appplication (IPA)
<a name="getipa"/>

- **Note: You ONLY need to do the first 3 steps once time. The next time you download an old version of any apps, you'll start from this step (Step 4).**

- Go back to iTunes and download Facebook, again! **Charles Proxy** will automatically show the **Breakpoint popup.** Select **Edit Request** => **XML Text** => Replace the current `Build Number Version` of Facebook with the `Build Number` of **Facebook v161.0**: `826067593` => **Execute** => **Execute**. Now iTunes will download **Facebook v161.0** istead of the latest version.
 
> But how do I know the `Build Number` of **Facebook v161.0**? - Read [Preparing Section](#preparing) carefully!

![WiiLTTo](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/WiiLTTo.png?token=AMT5SDFEJH3QKUNEHCIDAA3BI5UBO)

![fb161](https://raw.githubusercontent.com/qnblackcat/How-to-Downgrade-apps-on-AppStore-with-iTunes-and-Charles-Proxy/main/Screenshots/qv0mzsp.png?token=AMT5SDBNE2Q5UJK5OTLVX3TBI5V2U)

- How do I know the `Build Number` of **Facebook v161.0**? - Read [Preparing Section](#preparing) carefully!

### Step 5. Install the downloaded IPA.
<a name="installipa"/>

- We've finished the hardest part!👊 The IPA will be saved at ```C:\Users\<User>\Music\iTunes\iTunes Media\Mobile Applications```

> _**Pro Tips:**_ Instead of going to the location above,  **iTunes** => **Library** => Right-click on the app => **Open in Explorer**

- 





