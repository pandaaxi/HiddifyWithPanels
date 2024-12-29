# What is HiddifyWithPanels

For those who know, they know. For those who don’t, take your time to learn.

## Project Progress
- As of October 16, 2024, all features have been developed and no critical bugs remain. This marks the completion of version 1.0.

## Join the TG Group Chat

Feel free to join the V2Hiddify TG group chat for discussions and support: [V2Hiddify TG Group](https://t.me/V2Hiidify).

## Features
- [x] **OSS Support**: Automatic domain switching.
- [x] **Login with Panel Account**: Allows users to log in using panel accounts.
- [x] **Registration**: Provides user registration functionality.
- [x] **Password Recovery**: Offers password recovery options.
- [x] **Auto Subscription**: Automatically adds a subscription after purchasing a plan.
- [x] **Plan Information Display**: Shows the user’s current plan information.
- [x] **Payment Integration**: Supports payment platform integration.
- [x] **Plan Purchase**: Allows users to purchase different plans.
- [x] **Auto Subscription after Purchase**: Automatically adds a subscription post-purchase.
- [x] **Logout**: Users can log out.
- [x] **Localization Support**: Supports both English and Chinese localization.
- [x] **Invitation Codes**: Allows generation and copying of invitation codes.
- [x] **Wallet**: Supports wallet functionality, transfers, and withdrawals.
- [x] **Reset Subscription Link**: Supports resetting subscription links and automatic subscription to V2Hiddify.

## Installation Steps

### 1. Clone the Repository

First, clone the project repository locally:

```bash
git clone https://github.com/V2hiddify/HiddifyWithPanels
cd HiddifyWithPanels
```

### 2. Prepare Dependencies

Run the following commands based on your operating system to set up dependencies:

- **Windows**:

  ```bash
  make windows-prepare
  ```

- **Linux**:

  ```bash
  make linux-prepare
  ```

- **macOS**:

  ```bash
  make macos-prepare
  ```

- **iOS**:

  ```bash
  make ios-prepare
  ```

- **Android**:

  ```bash
  make android-prepare
  ```

### 3. Run the Project

Once dependencies are prepared, use Flutter to run the project:

```bash
flutter run
```

在项目目录下进行以下替换操作：

1. **替换面板域名**：

   打开```lib/features/panel/xboard/services/http_service/domain_service.dart``` 替换ossDomain为目标自己的oss地址.[oss模版](https://github.com/GalenBlabla/website-list/blob/master/websites.json)。  


2. **替换机场名字**：

   应用内，找到语言包```assets/translations/strings_zh-CN.i18n.json```（中文举例），修改第三行```"appTitle": "V2Hiddify"```。V2Hiddify就是程序应用内的名字以及欢迎界面的名字。  
   应用外，也就是应用本身的名字，需要在对应平台文件中修改，安卓示例：  
    #### 修改 `AndroidManifest.xml`

    在 `android/app/src/main/AndroidManifest.xml` 文件中，找到 `<application>` 标签中的 `android:label` 属性并修改它：

    ```xml
    <application
        android:name=".Application"
        android:banner="@mipmap/ic_banner"
        android:icon="@mipmap/ic_launcher"
        android:label="V2Hiddify"
    ```
   你仍然可以使用全局替换的方式更改你看到的目标文字，虽然这样可能会带来未知的错误。

   ~~搜索项目中所有 `V2Hiddify` 的地方，并替换为你的机场名称。例如，如果你的机场名字是 `SuperVPN`，可以用以下命令替换：~~


   ~~grep -rl 'V2Hiddify' lib/ | xargs sed -i 's/V2Hiddify/SuperVPN/g'~~

### 5. 打包应用
默认无任何代理.
根据需要打包相应平台的应用：  
如果需要配置安卓代理,在打包之前需要进入 `android` 目录下，找到 `gradle.properties` 文件，修改里面的代理 IP 和端口为自己的,如果无需代理，可忽略：

  ```properties
  org.gradle.jvmargs=-Xmx4048m -Dfile.encoding=UTF-8
  android.useAndroidX=true
  android.enableJetifier=true

  # HTTP 代理设置
  systemProp.http.proxyHost=192.168.28.36
  systemProp.http.proxyPort=7890

  # HTTPS 代理设置
  systemProp.https.proxyHost=192.168.28.36
  systemProp.https.proxyPort=7890

  # 不使用代理的主机（可选）
  systemProp.http.nonProxyHosts=localhost|127.0.0.1
  ```

### 5. Build the Application

- Build for Android:

  ```bash
  flutter build apk
  ```

- Build for iOS:

  ```bash
  flutter build ios
  ```

- Build for macOS:

  ```bash
  flutter build macos
  ```

- Build for Windows:

  ```bash
  flutter build windows
  ```

---

Following these steps, you can customize and package your V2Hiddify client to suit your panel needs.


### Support This Project

Supporting individual developers is not easy; if this project has been helpful to you, feel free to support it with a donation.

**Wallet Address (USDT-TRC20):**
```
TFPvpxb5k2mYYcvABe5BrCz7Tt6BhnZxxj
```

