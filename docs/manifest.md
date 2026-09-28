# Directoris de Codi Font i l'AndroidManifest

Aquesta secció descriu la distribució de les classes en **Kotlin** o **Java** i la funció del fitxer de registre principal de l'aplicació.

## AndroidManifest.xml

El fitxer `AndroidManifest.xml` és un dels components més importants. Funciona com una fitxa d'identificació de l'aplicació per al sistema operatiu Android.

### Responsabilitats Clau:
1. Declarar els **components** de l'aplicació (Activitats, Serveis, *Broadcast Receivers*, *Content Providers*).
2. Definir els **permisos** requerits (accés a Internet, càmera, ubicació, etc.).
3. Especificar el nivell de maquinari requerit.

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.androidapp">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:theme="@style/Theme.AndroidApp">

        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## Directoris del Codi Font (`src/main/java`)

El codi font s'organitza seguint una estructura de paquets. És recomanable utilitzar l'arquitectura **MVVM** (*Model-View-ViewModel*).

| Directori / Paquet | Descripció |
| :--- | :--- |
| `data/` | Repositoris, fonts de dades locals (Room) i remotes (Retrofit). |
| `ui/` | Pantalles, activitats, fragments i components de Compose/Layouts. |
| `viewmodel/` | Lògica de negoci i gestió de l'estat de la interfície. |

---
**[Volver al Índice Principal](index.md)**
