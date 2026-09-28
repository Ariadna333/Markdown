# Scripts de Gradle i Estructura del Projecte

El sistema de construcció per excel·lència en Android és **Gradle**. Permet automatitzar la compilació, provar l'aplicació i gestionar les dependències externes.

## Fitxers de Configuració Principals

Un projecte d'Android típic conté dos fitxers de configuració Gradle principals:

* **`build.gradle.kts` (Project-level):** Defineix els suplements (*plugins*) i opcions globals per a tots els mòduls.
* **`build.gradle.kts` (Module-level):** Defineix la configuració específica de l'aplicació (`app`).

### Exemple de Mòdul Gradle (`build.gradle.kts`)

```kotlin
plugins {
    alias(libs.plugins.android.application)
    alias(libs.plugins.kotlin.android)
}

android {
    namespace = "com.example.androidapp"
    compileSdk = 34

    defaultConfig {
        applicationId = "com.example.androidapp"
        minSdk = 24
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
}

dependencies {
    implementation(libs.androidx.core.ktx)
    implementation(libs.androidx.appcompat)
    implementation(libs.material)
}
```

## Comandances útils de Gradle

Pots executar les següents instruccions des de la terminal per a compilar i validar el projecte:

* Netejar el projecte: ` ./gradlew clean `
* Compilar la versió de desenvolupament: ` ./gradlew assembleDebug `
* Executar les proves unitàries: ` ./gradlew test `