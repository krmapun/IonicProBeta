*** Fuente https://www.youtube.com/watch?v=GdV-Prk8JDU ***
***ELABORADO POR MANUEL ROJAS***CONTIENE INFORMACION DE LA KEY Y EL PROCESO DE ACTUALIZACION****

1. GENERANDO KEY DE SEGURIDAD PARA LA APP ANDDANDO.

keytool -genkey -v -keystore nexgen-key.keystore -alias nexgen -keyalg RSA -keysize 2048 -validity 10000

Contraseņa: 	nexgenmb1.
nombres:	nexgen
unidad:		desarrollo
organizacion:	nexgen
ciudad:		bogota
estado:		norte
cod pais:	CO

2. GENERANDO LA APK SIN FIRMAR 

ionic cordova build android --release

*SE SACA LA RUTA DE LA APK*

3.  SE FIRMA LA APP CON LA KEY CREADA

jarsigner -verbose -sigalg SHA256withRSA -digestalg SHA1 -keystore nexgen-key.keystore C:/Users/NexgenAdmin/Documents/IonicPro/IonFire/platforms/android/build/outputs/apk/android-release-unsigned.apk nexgen

4. SE COMPACTA LA APK

zipalign -v 4 C:/Users/NexgenAdmin/Documents/IonicPro/IonFire/platforms/android/build/outputs/apk/android-release-unsigned.apk Anddando.apk


*** USUARIOS ***

-FACEBOOK DEVELOPERS-https://developers.facebook.com/
	nexgensoluciones.co@gmail.com
	12346nexgen
-FIREBASE-https://console.firebase.google.com/
	nexgensoluciones.co@gmail.com
	Nexgenadm1.

*** COMANDOS PARA ACTUALIZAR LA APP ***

npm uninstall -g ionic && sudo npm install ionic
npm update -g ionic
npm update -g cordova
cordova platform update [platform]

*** COMANDO PARA OBTENER EL HASH DE FACEBOOK CON LA KEYSTORE CREADA ***

keytool -exportcert -alias nexgen -keystore C:\Users\NexgenAdmin\Documents\IonicPro\IonFire\nexgen-key.keystore | C:\Users\NexgenAdmin\Documents\IonicPro\OpenSSL\bin\openssl sha1 -binary | C:\Users\NexgenAdmin\Documents\IonicPro\OpenSSL\bin\openssl base64

keytool -exportcert -alias YOUR_RELEASE_KEY_ALIAS -keystore YOUR_RELEASE_KEY_PATH | openssl sha1 -binary | openssl base64

ionic plugin add cordova-plugin-facebook4 --variable APP_ID="263466121030069" --variable APP_NAME="anddando"

