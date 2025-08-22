[![](https://jitpack.io/v/Tamil-Fuzionest/BizSub-SDK.svg)](https://jitpack.io/#Tamil-Fuzionest/BizSub-SDK)

# 🚖 BizSub SDK – Taxina Subscription Flow (Android)

BizSub is an **Android SDK** designed to simplify the **subscription and payment flow** for **Taxina-powered taxi applications**.
It provides a ready-to-use subscription screen, handles the Razorpay payment flow, and makes it easy for developers to integrate subscription plans into their apps.

---

## 📦 Features

* 🔑 Secure integration with **Razorpay** (supports orderId, amount, etc.)
* 🎨 Ready-made **subscription activity UI** (customizable theme support)
* 📱 Designed for **Taxi apps subscription plans** (e.g., drivers paying for app usage)
* ⚡ Lightweight & easy to integrate

---

## 🚀 Installation

### Option 1: From Maven Central / GitHub Packages

```gradle
repositories {
    mavenCentral()
    // or
    maven { url = uri("https://maven.pkg.github.com/fuzionest/BizSub-SDK") }
}

dependencies {
    implementation("com.fuzionest:bizsub:1.0.0")
}
```

## 🛠️ Usage

Launch the **BizSub subscription activity** from your app:

```kotlin
import com.fuzionest.bizsub.SubscriptionActivity

// Example: Start subscription flow
val subscription = SubscriptionActivity(context)
subscription.startPayment(
    keyId = "rzp_test_key",          // Razorpay key
    orderId = "order_123",           // Order ID from your backend
    amount = "1000",                 // Amount in INR (paise format if required)
    planName = "Driver Gold Plan",   // Subscription plan name
    vehicleNo = "TN01AB1234",        // Driver’s vehicle number
    phone = "+911234567890"          // Driver’s phone number
)
```

On **successful payment**, BizSub will return the Razorpay payment ID which you can verify with your backend.

---

## 📂 Example Project

We’ve included a **sample Android project** in the [`example/`](example/) folder.
You can open it in Android Studio and run directly to see how **BizSub** integrates with a taxi driver app.

---

## 🎨 Customization

* You can **customize the theme and colors** of the subscription page.
* Hide or show UI elements (like user icon, labels) as per your brand.

---

## 📖 Developer Flow

1. Add BizSub dependency
2. Configure your backend to generate **Razorpay orderId**
3. Call `SubscriptionActivity.startPayment()` with the orderId and driver details
4. Verify payment on your backend
5. Enable subscription features in your Taxi app

---

## 🧑‍💻 Contributing

Contributions are welcome!

1. Fork this repo
2. Create a feature branch
3. Submit a Pull Request 🚀

---

## 📜 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 Fuzionest Pvt Ltd

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
