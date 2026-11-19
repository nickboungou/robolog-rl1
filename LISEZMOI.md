# RoboLog RL-1 : application Android et iPhone (Capacitor)

Prérequis : Node.js 18+. Android : Android Studio. iPhone : un Mac avec Xcode.

    npm install
    npx cap add android     # et/ou : npx cap add ios
    npx cap sync

## Android (APK)
    npx cap open android
Dans Android Studio : Build > Build Bundle(s) / APK(s) > Build APK(s).
Le fichier est dans android/app/build/outputs/apk/debug/app-debug.apk
Copiez-le sur le téléphone et installez-le (autoriser les sources inconnues).
Les téléphones Android coupent parfois le Wi-Fi « sans internet » :
acceptez de rester connecté à ROBOLOG-RL1 quand le téléphone le demande.

## iPhone
    npx cap open ios
Dans ios/App/App/Info.plist, ajoutez avant la dernière balise </dict> :

    <key>NSLocalNetworkUsageDescription</key>
    <string>Connexion au bras robotisé RoboLog</string>
    <key>NSAppTransportSecurity</key>
    <dict><key>NSAllowsArbitraryLoadsInWebContent</key><true/></dict>

Dans Xcode : choisissez votre équipe (Signing & Capabilities), branchez l'iPhone, bouton Run.
Pour l'App Store : compte Apple Developer (99 USD/an), Product > Archive, puis App Store Connect.

## Mise à jour de l'interface
Modifiez www/index.html, puis : npx cap sync
