[![](https://jitpack.io/v/Tamil-Fuzionest/BizSub-SDK.svg)](https://jitpack.io/#Tamil-Fuzionest/BizSub-SDK)

# 🚖 BizSub SDK – Taxina Subscription Flow (Android)

BizSub is an **Android SDK** designed to simplify the **subscription flow** for **Taxina-powered taxi applications**.  
It provides a ready-to-use subscription screen and makes it easy for developers to integrate subscription plans into their apps.

---

## 🚀 Installation

Add **JitPack** in your `settings.gradle` or `build.gradle`:

```gradle
repositories {
    google()
    mavenCentral()
    maven { url "https://jitpack.io" }
}
````

Add the dependency:

```gradle
dependencies {
    implementation("com.github.Tamil-Fuzionest:BizSub-SDK:[![](https://jitpack.io/v/Tamil-Fuzionest/BizSub-SDK.svg)](https://jitpack.io/#Tamil-Fuzionest/BizSub-SDK)")
}
```

---

## 🛠️ Usage

Configure the SDK and launch the **BizSub subscription view** from your app:

```kotlin
// Step 1: Configure the SDK
BizSub.config(
    SubscriptionSdkConfig(
        vehicleId = "TN44MM5435" // Replace with driver’s actual vehicle number
    )
)

// Step 2: Show the subscription screen
BizSub.showSubscriptionView(this@MainActivity) { result ->
    when (result.status) {
        SubscriptionStatus.SUCCESS,
        SubscriptionStatus.FAILURE ->
            Toast.makeText(myTextView.context, result.message, Toast.LENGTH_SHORT).show()

        SubscriptionStatus.CLOSED ->
            Toast.makeText(this, "Closed by user", Toast.LENGTH_SHORT).show()

        SubscriptionStatus.ERROR,
        SubscriptionStatus.INVALID_VEHICLE_ID ->
            Toast.makeText(
                myTextView.context,
                "Error: ${result.message}",
                Toast.LENGTH_SHORT
            ).show()
    }
}
```

That’s it 🎉 — BizSub will open the subscription UI and return the result via callback.

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
