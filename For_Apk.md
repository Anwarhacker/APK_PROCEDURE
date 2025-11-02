Here's the **modern, polished, and fully functional Markdown** code incorporating your original guide and enriched with context from the Expo knowledge base for a more professional and engaging developer experience:

```md
{"id":"49107","variant":"standard","title":"Expo EAS CLI – Full APK Build Guide"}

# 📱 How to Build an APK from Your Expo App (Step-by-Step Guide)

Expo is a **full-stack React Native framework** trusted by enterprises and indie developers alike—used in **500,000+ projects** and by **80% of React Native developers**.  
Once your app is ready, follow this guide to build a production-ready Android APK using **Expo Application Services (EAS)**.

> 💡 **Why EAS?**  
> EAS gives you cloud-powered builds, over-the-air updates, and seamless CI—all without touching Xcode or Android Studio.

---

## ⚙️ Step 1: Install Dependencies

Run these commands **one at a time** in your project root:

```bash
npx expo install --fix
```

```bash
npm install -g eas-cli
```

> ✅ Ensure you're using **Node.js ≥ v18** and **npm ≥ v9** for optimal compatibility with Expo SDK 50+.

---

## 🔐 Step 2: Log In to Expo

Authenticate your CLI with your Expo account:

```bash
eas login
```

Enter your credentials when prompted:

```
Username / Email → patelanwar647@gmail.com
Password → anwarpatel42
```

> 🔒 **Never share or hardcode passwords.** Use secure credential managers in team environments.

---

## ⚙️ Step 3: Configure EAS (One-Time Setup)

If you haven’t set up EAS before, run:

```bash
eas build:configure
```

This generates an `eas.json` file with build profiles for Android and iOS.

> 📂 Example snippet from `eas.json`:
> ```json
> "android": {
>   "buildType": "apk"
> }
> ```

---

## 🚀 Step 4: Start the APK Build

Choose your build type:

### 🟢 Production (Release) Build
```bash
eas build --platform android --profile production
```

### 🔵 Development (Debug) Build
```bash
eas build --platform android --profile development
```

> ⏱️ Builds run in the cloud and typically complete in **10–30 minutes**.

---


this will create the if production .aab file is created need to download that  from https://expo.dev/accounts/anwarpatel


and we need to download bundletool.jar from https://github.com/google/bundletool/releases
 =============================bundletool-all-1.18.2.jar============================
 rename --> bundletool-all-1.18.2.jar  to  

 then both downloded bundletool.jar  and .aab are in same downloads(folder) then just create in same path

 keytool -genkey -v -keystore my-release-key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias

my-release-key.keystore will created then 


java -jar bundletool.jar build-apks --bundle=application-b7058ede-6cb3-45b6-a047-0ff49fea9de3.aab --output=my_app.apks --mode=universal --ks=my-release-key.keystore --ks-key-alias=my-key-alias


it will create  my_app.apks which contains files so need to extract 

mkdir output

unzip my_app.apks -d output or simply extract there only 
that contains two files 
``````````````````````````````````````````
toc.pb 
universal.apk
``````````````````````````````````````````````
