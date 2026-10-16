# Snow website (GitHub Pages)

## Put it online
1. Create a new GitHub repository (public), e.g. `snow`.
2. Upload everything in this folder (`index.html`, `update.json`, `.nojekyll`, `apk/`).
3. Repository **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`. Save.
4. After a minute your site is at `https://YOUR-USERNAME.github.io/snow/`.

## Release a new version
1. Raise `versionCode` in `app/build.gradle.kts`, build the signed APK.
2. Rename it `snow.apk` and replace `apk/snow.apk` in the repo (GitHub web upload works for files under 25 MB; bigger files: use Git, up to 100 MB each).
3. Edit `update.json`: raise `versionCode`, set `versionName`, `notes`, and make `apkUrl`
   `https://YOUR-USERNAME.github.io/snow/apk/snow.apk`.
4. Commit. Phones running an older version are forced to update the next time the app opens.

## In the app
Set `UPDATE_URL` in `Updater.kt` to `https://YOUR-USERNAME.github.io/snow/update.json`.

Tip: if the APK is over 100 MB, attach it to a GitHub Release instead and use that download link as `apkUrl`.
