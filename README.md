[![APK Builder](https://github.com/shiveshnavin/apk-builder/actions/workflows/main.yml/badge.svg)](https://github.com/shiveshnavin/apk-builder/actions/workflows/main.yml)

# APK Builder CI
The Github Action allows you to build APK from any android studio project repo url

### Usage
Simply goto actions and click on run workflow and provide your username and public repo. The output apk will be generated as part of build artifacts

![image](https://user-images.githubusercontent.com/16799797/188626094-e014480c-228c-408d-bbb8-efe8821e6b64.png)

### Note
Make sure to specify signing config in app/build.gradle 
```
android {

    signingConfigs {
        release {
            keyAlias 'myKeyAlias'
            keyPassword 'password'
            storePassword 'password'
            storeFile file("${rootDir}/key.jks")
        }
    }
    
    
      buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
            signingConfig signingConfigs.release
        }
        debug {
            signingConfig signingConfigs.release
        }
    }
    
}
```
