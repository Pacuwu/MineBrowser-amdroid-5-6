# MiniBrowserGecko

Navegador ligero basado en GeckoView para revivir dispositivos antiguos
(MinSdk 22 / Android 5.1.1 Lollipop).

## Cómo abrirlo

1. Abre Android Studio.
2. "Open" (o "Open an Existing Project") y selecciona esta carpeta
   (`MiniBrowserGecko`), NO la subcarpeta `app`.
3. Android Studio detectará que falta el Gradle Wrapper y te ofrecerá
   regenerarlo automáticamente. Acepta. Si no te lo pregunta solo, ve a
   `File > Sync Project with Gradle Files`.
4. Espera a que descargue las dependencias (GeckoView pesa bastante,
   puede tardar varios minutos la primera vez).
5. Conecta tu dispositivo (o usa un emulador) y dale a Run.

## Requisitos en tu PC

- Android Studio reciente (cualquier versión actual sirve).
- JDK 17 (Android Studio normalmente ya trae uno embebido, así que no
  suele hacer falta instalar nada aparte).

## Si la sincronización falla por la versión de GeckoView

La versión de GeckoView indicada en `app/build.gradle` (canal "stable")
es real y comprobada, pero Mozilla saca una nueva cada ~4 semanas, así
que puede que ya exista una más reciente. Si da error de "no se pudo
resolver la dependencia", entra en:

https://maven.mozilla.org/?prefix=maven2/org/mozilla/geckoview/geckoview-stable/

y copia el nombre de la versión más reciente en la variable
`geckoviewVersion` de `app/build.gradle`.

## Estructura

```
MiniBrowserGecko/
├─ build.gradle              (proyecto raíz)
├─ settings.gradle
├─ gradle.properties
└─ app/
   ├─ build.gradle           (dependencia de GeckoView)
   ├─ proguard-rules.pro
   └─ src/main/
      ├─ AndroidManifest.xml
      ├─ res/layout/activity_main.xml
      └─ java/com/minerva/minibrowser/MainActivity.kt
```
