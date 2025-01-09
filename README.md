# verifyedSdk
This Repo is for Open SDK (verifyed SDK).

# Customer Onboarding Integration Guide
This guide provides detailed instructions for integrating the onboarding process into your Android application.

---

## Table of Contents

1. [Add Maven Repositories](#add-maven-repositories)
2. [MainActivity Setup](#mainactivity-setup)
3. [Dependencies](#dependencies)
4. [Library Versions](#library-versions)

---

## Add Maven Repositories

Add the following code to your `settings.gradle.kts` file to include the required Maven repositories:

```kotlin
dependencyResolutionManagement {
    ...
    repositories {
        google()
        mavenCentral()
        maven {
            url = URI("https://s3.ap-south-1.amazonaws.com/hvsdk/android/releases")
        }
        maven { url = uri("https://jitpack.io") }
        maven {
            url = uri("https://maven.pkg.github.com/Pratikmontra/verifyedsdk")
        }
    }
}

MainActivity Setup
To launch the onboarding process in your application, add the following code to your MainActivity.kt:

kotlin
Copy code
val openAccountManager = OpenAccountManager.initialize(
    emailId = "muyiwa@gmail.com", 
    custId = "5678", 
    tenantId = "1234"
)
openAccountManager.openOnBoarding(this)
Replace the placeholder values with actual customer-specific details:

emailId: Customer's email address
custId: Customer ID
tenantId: Tenant ID


Dependencies
Add the required dependencies to your app/build.gradle.kts file:

kotlin
Copy code
implementation(libs.verifyedsdk)
implementation(libs.ssp) // Scalable text sizes
implementation(libs.sdp) // Scalable dimensions
implementation(libs.navigation.fragment.ktx)
implementation(libs.navigation.ui.ktx)
implementation(libs.navigation.compose)
implementation(libs.convertgsonkotlin)
implementation(libs.maps.ktx)
implementation(libs.maps.utils.ktx)
implementation(libs.places)
implementation(libs.play.services.location)
implementation(libs.foundation)
implementation(libs.convetor.gson)
implementation(libs.androidx.multidex)
implementation(libs.security.crypto.ktx)
implementation(libs.glide)
implementation(libs.androidx.material3)
implementation(libs.androidx.activity.compose)
implementation(platform(libs.androidx.compose.bom))
implementation(libs.androidx.ui)
implementation(libs.androidx.ui.graphics)
implementation(libs.androidx.activity.compose)
implementation(libs.jsdp)
implementation(libs.retrofit)
implementation(libs.logging.interceptor)
implementation(libs.play.services.maps)
implementation(libs.hyperverge)
implementation(libs.coil)
implementation(libs.maps.compose)
implementation(libs.maps.compose.utils)
implementation(libs.maps.compose.widgets)
Library Versions
Include the following versions in your libs.versions.toml file:

toml
Copy code
[versions]
verifyedsdk = "1.0.1"
ssp = "1.1.1"
sdp = "1.1.1"
nav_version = "2.7.1"
convertgsonkotlin = "1.5.1"
foundation = "1.0.5"
mapsKtx = "5.0.0"
mapsUtilsKtx = "5.0.0"
places = "3.3.0"
playServicesLocation = "21.0.1"
convetergson = "2.9.0"
multidex = "2.0.1"
securityCryptoKtx = "1.1.0-alpha03"
glide = "1.0.0-alpha.6"
material3 = "1.0.0-alpha02"
composeBom = "2024.06.00"
activityCompose = "1.9.0"
jsdp = "1.0.4"
retrofit = "2.9.0"
logginginterceptor = "4.10.0"
playServicesMaps = "18.2.0"
hyperverge = "0.35.0"
coilCompose = "2.1.0"
mapsComposeVersion = "4.4.1"

[libraries]
verifyedsdk = { module = "com.github.Pratikmontra:verifyedsdk", version.ref = "verifyedsdk" }
ssp = { group = "com.intuit.ssp", name = "ssp-android", version.ref = "ssp" }
sdp = { group = "com.intuit.sdp", name = "sdp-android", version.ref = "sdp" }
navigation-fragment-ktx = { group = "androidx.navigation", name = "navigation-fragment-ktx", version.ref = "nav_version" }
navigation-ui-ktx = { group = "androidx.navigation", name = "navigation-ui-ktx", version.ref = "nav_version" }
navigation-compose = { group = "androidx.navigation", name = "navigation-compose", version.ref = "nav_version" }
convertgsonkotlin = { group = "org.jetbrains.kotlinx", name = "kotlinx-serialization-json", version.ref = "convertgsonkotlin" }
maps-ktx = { group = "com.google.maps.android", name = "maps-ktx", version.ref = "mapsKtx" }
maps-utils-ktx = { group = "com.google.maps.android", name = "maps-utils-ktx", version.ref = "mapsUtilsKtx" }
places = { group = "com.google.android.libraries.places", name = "places", version.ref = "places" }
play-services-location = { group = "com.google.android.gms", name = "play-services-location", version.ref = "playServicesLocation" }
foundation = { group = "androidx.compose.foundation", name = "foundation", version.ref = "foundation" }
convetor-gson = { group = "com.squareup.retrofit2", name = "converter-gson", version.ref = "convetergson" }
androidx-multidex = { module = "androidx.multidex:multidex", version.ref = "multidex" }
security-crypto-ktx = { group = "androidx.security", name = "security-crypto", version.ref = "securityCryptoKtx" }
glide = { module = "com.github.bumptech.glide:compose", version.ref = "glide" }
androidx-material3 = { group = "androidx.compose.material3", name = "material3", version.ref = "material3" }
androidx-compose-bom = { group = "androidx.compose", name = "compose-bom", version.ref = "composeBom" }
androidx-ui = { group = "androidx.compose.ui", name = "ui" }
androidx-ui-graphics = { group = "androidx.compose.ui", name = "ui-graphics" }
androidx-activity-compose = { group = "androidx.activity", name = "activity-compose", version.ref = "activityCompose" }
jsdp = { group = "network.chaintech", name = "sdp-ssp-compose-multiplatform", version.ref = "jsdp" }
retrofit = { group = "com.squareup.retrofit2", name = "retrofit", version.ref = "retrofit" }
logging-interceptor = { group = "com.squareup.okhttp3", name = "logging-interceptor", version.ref = "logginginterceptor" }
play-services-maps = { group = "com.google.android.gms", name = "play-services-maps", version.ref = "playServicesMaps" }
hyperverge = { group = "co.hyperverge", name = "hyperkyc", version.ref = "hyperverge" }
coil = { group = "io.coil-kt", name = "coil-compose", version.ref = "coilCompose" }
maps-compose = { group = "com.google.maps.android", name = "maps-compose", version.ref = "mapsComposeVersion" }
maps-compose-utils = { group = "com.google.maps.android", name = "maps-compose-utils", version.ref = "mapsUtilsKtx" }
maps-compose-widgets = { group = "com.google.maps.android", name = "maps-compose-widgets", version.ref = "mapsUtilsKtx" }