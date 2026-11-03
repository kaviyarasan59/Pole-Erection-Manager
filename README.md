# RDSS Pole Mapping Android App (source project)

## Features in this starter project
- Pole types: 9M 300kg, 9M 400kg, 9M Square pole, 11M RSJ, 8M LT
- GPS location and map-based pole marking (tap map to select, then Add pole; long-press to add directly)
- Pole list, pole marker details, manual material entry per pole
- CSV import/export including pole and material rows
- KML import/export for pole coordinates and labels
- Online OpenStreetMap map tiles; osmdroid cache can display previously viewed tiles offline

## Important offline-map note
This uses a tile cache, not a full offline map downloader. Open the survey area and zoom to required levels while online before going offline. Only cached map tiles are available offline. For extensive offline use, add a legally obtained MBTiles/MapTile package and configure its provider.

## Build APK on Android/PC
This is an Android Studio Gradle project. An Android SDK/Gradle build environment is required to produce an installable APK.
1. Install Android Studio on a PC, open this project folder, and let Gradle sync. This source bundle does not include Gradle wrapper binaries/scripts; open it in Android Studio and sync Gradle, or use the included GitHub Actions workflow to build it in the cloud.
2. Use JDK 17 (Android Studio's bundled JDK is suitable).
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. The debug APK is normally at `app/build/outputs/apk/debug/app-debug.apk`.

## Notes / limitations
- The project source is provided; an APK has not been compiled or device-tested in this environment. The included GitHub Actions workflow installs Gradle and builds the APK without needing wrapper files.
- Location permission is requested at launch. Enable GPS/location on the phone.
- CSV import expects headers followed by `pole_number,pole_type,latitude,longitude,material_name,quantity,unit`.
- KML import reads Placemark name and Point coordinates. Imported KML placemarks default to the first pole type because the pole type is not standardized in KML.
- This is a starter app, not a production utility. Test field accuracy, data backup, and CSV/KML edge cases before operational use.
