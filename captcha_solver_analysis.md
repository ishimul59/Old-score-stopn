# CAPTCHA Solver Extension - বিস্তারিত বিশ্লেষণ

## এক্সটেনশন সম্পর্কে সাধারণ তথ্য
- **নাম**: SCORE STOP 
- **ভার্সন**: 0.63
- **উদ্দেশ্য**: স্বয়ংক্রিয়ভাবে বিভিন্ন ধরনের CAPTCHA সমাধান করা

## মূল এক্সট্রেশন ফাইলগুলো এবং তাদের কাজ:

### 1. **Content Scripts (content_scripts1.js & content_scripts2.js)**
- **কাজ**: সব ওয়েবসাইটে inject হয় এবং CAPTCHA detect করে
- **বৈশিষ্ট্য**: 
  - সব HTTP/HTTPS সাইটে run হয়
  - CAPTCHA elements খুঁজে বের করে
  - Background script এর সাথে communicate করে

### 2. **reCAPTCHA Interceptor (recaptcha3_object_interceptor.js)**
- **কাজ**: Google reCAPTCHA v3 intercept করে
- **বিশেষত্ব**:
  - `grecaptcha.execute()` function কে override করে
  - Enterprise version সাপোর্ট করে
  - Automatic solution inject করে

### 3. **FunCaptcha Interceptor (funcaptcha_object_inteceptor.js)**
- **কাজ**: Arkose Labs FunCaptcha solve করে
- **বৈশিষ্ট্য**:
  - `FunCaptcha` এবং `ArkoseEnforcement` objects modify করে
  - Session token management করে
  - Automatic callback handling

### 4. **hCAPTCHA Interceptor (hcaptcha_object_inteceptor.js)**
- **কাজ**: hCAPTCHA services intercept করে
- **ফিচার**:
  - `hcaptcha.render()` এবং `hcaptcha.execute()` override করে
  - Multiple widget support করে
  - Invisible এবং visible captcha দুটোই handle করে

### 5. **Geetest Interceptor (geetest_object_interceptor.js)**
- **কাজ**: Geetest CAPTCHA system solve করে
- **বৈশিষ্ট্য**:
  - `initGeetest()` function intercept করে
  - Challenge-response mechanism handle করে
  - Form binding এবং validation করে

### 6. **Background Script (background.js)**
- **কাজ**: Extension এর main processing logic
- **প্রধান কাজ**:
  - CAPTCHA solving API service এর সাথে communication
  - Image extraction এবং processing
  - Cost calculation এবং balance management
  - Screenshot capture এবং analysis

## API Integration:
- **Service Provider**: ar1n.xyz domain ব্যবহার করে
- **Statistics**: সব solving attempts track করে
- **Balance Management**: Account key দিয়ে balance check করে

## সাপোর্টেড CAPTCHA Types:
1. **reCAPTCHA v2** - Image selection based
2. **reCAPTCHA v3** - Score based invisible
3. **hCAPTCHA** - Privacy focused alternative
4. **FunCaptcha** - Interactive puzzle based
5. **Geetest** - Slide and click based
6. **Traditional Image CAPTCHA** - Text recognition

## Extension Features:
- **Auto-submit**: Form automatically submit করে
- **Sound notifications**: Success/error sounds
- **Proxy support**: Custom proxy configuration
- **Whitelist/Blacklist**: Specific domains এর জন্য
- **Pre-caching**: reCAPTCHA solutions cache করে
- **Multi-language**: Multiple language support

## Configuration Options:
- Account key management
- Auto-submit form toggle
- Sound notifications on/off
- Delay settings
- Proxy configuration
- Domain filtering

## Security & Privacy:
- সব major websites এ access permission
- Network requests intercept করে
- Screenshot capture ability
- Data transmission to external servers

## মূল উদ্দেশ্য:
এই extension টি মূলত automation এবং testing purposes এর জন্য ব্যবহার হয়, যেখানে বিভিন্ন ধরনের CAPTCHA automatically solve করা প্রয়োজন।

---

**সতর্কতা**: এই ধরনের tools ব্যবহার করার সময় সংশ্লিষ্ট websites এর terms of service মেনে চলা উচিত।