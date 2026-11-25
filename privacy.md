# Privacy Policy

*Last updated: 25 November 2026*

Zenith ("the app") is a pilot's logbook. This policy explains what data the app handles and why. In short: **your data stays on your device or in your own cloud storage. We do not run servers, have no user accounts, collect no analytics or crash reports, show no ads, and never sell or share your data.**

## Data stored on your device

The following is stored locally on your device in the app's private storage:

- **Logbook:** flights (times, airports, remarks, landings, IFR/night time), aircraft (including registration, notes and photos), simulators and crew roles.
- **People:** names and optional profile photos of crew and other people you add.
- **Pilot profile:** your name, nickname, postal address, previous totals, licences (including licence numbers, ratings and language proficiency) and medical certificates (class, expiry, limitations, notes).
- **Signatures and images:** drawn or uploaded signatures and header images, plus photos you take or pick from your gallery.
- **Flight tracks:** GPS points (latitude, longitude, altitude, speed, heading, time) of recorded flights.
- **Settings and caches:** preferences, a random device ID used for optional sync, downloaded public aircraft and airport reference data, cached aircraft photos, generated PDF exports and local backup files.

Credentials (cloud access tokens and any API keys you enter, such as for OpenSky, FlyItalyAdsb or CARTO) are kept in the device's secure storage (Android Keystore / iOS Keychain) and are never included in backups.

The app does not apply its own encryption to the logbook database, photos or backup files; they rely on your device's protection (screen lock and device encryption). Android Auto Backup is disabled for the app. On iOS, the app's data may be included in your own device backups (iCloud or computer) according to your device settings.

## Permissions

- **Location (precise, including in the background):** used only when you start a flight recording, to record your flight track (a foreground notification is shown on Android). It is also used to sort nearby airports and to fill in the position of a new airport, at your request. Location data stays on your device and is never sent to us.
- **Camera and photo library:** used only when you choose to add photos of aircraft or people, signatures or header images. Zenith does not access your gallery otherwise.
- **Notifications:** used for local reminders (for example expiring documents). No push notification service is used.
- **Internet:** used for cloud backup/sync, optional lookups and map tiles (see below).
- **Install packages (Android only):** used only if you choose to install an app update downloaded from GitHub.

## Cloud backup and sync

Backups and optional cross-device sync are **off unless you connect a cloud account**. You can connect Google Drive or Dropbox. Zenith has no server of its own: data travels directly between your device and the provider you chose, over HTTPS.

Backup and sync files are **not encrypted by Zenith**. They are protected only by your cloud account's own security, so keep that account secure.

### What is uploaded

- **Backups:** a ZIP file containing your whole logbook: database, photos, signatures and app settings (but no credentials). Backups can be scheduled (off, daily or weekly) and run when the app is opened or resumed. A backup is skipped when nothing has changed. By default only the newest 3 backups are kept; older ones are deleted automatically.
- **Sync (optional, off by default):** if you enable "Sync across devices", compressed logbook change files and related photos/tracks are uploaded to a separate folder and downloaded by your other devices. While enabled, sync runs on app launch, on resume and shortly after you change your logbook. Records you delete are propagated for 90 days, and state files of devices that have stopped syncing for 90 days are removed.

## Dropbox

If you connect Dropbox, Zenith signs in through Dropbox's official authorization page in your browser, using OAuth 2.0 with PKCE. Zenith never sees or stores your Dropbox password.

**Permissions requested:** `account_info.read`, `files.metadata.read`, `files.content.read` and `files.content.write`. Zenith uses them as follows:

- **Account info:** reads your Dropbox display name and email address only to show which account is connected in the backup settings. They are held in memory, not stored, and not sent anywhere else.
- **File listing:** lists file names, sizes and modification dates of Zenith's own folders to show your backups and to find sync files.
- **Upload and download:** uploads backup ZIPs and sync files, and downloads them when you restore a backup or when sync pulls changes from another device.
- **Deleting:** deletes only files inside Zenith's own folders: old backups beyond the retention limit, outdated sync files, and everything in the sync folder if you choose "Delete sync data". Zenith does not delete anything else.

**Where files are stored:** Zenith uses only two folders: `Zenith Backups` (backups) and `Zenith Sync` (sync data). Zenith does not search, read or modify any other file in your Dropbox, and does not create shared links.

**Tokens:** the access and refresh tokens are stored only in your device's secure storage and are refreshed automatically.

**Disconnecting:** you can disconnect Dropbox at any time in the app's backup settings. This revokes the access token with Dropbox where possible and deletes the tokens from your device. **Files already in your Dropbox are kept** until you delete them yourself; "Delete sync data" in the app removes the sync folder's contents. You can also remove Zenith's access in your [Dropbox account settings](https://www.dropbox.com/account/connected_apps).

Dropbox data is used solely to store and restore your Zenith data at your request. It is not shared with anyone, not sold, not used for advertising or to train AI/ML models. Dropbox processes your files under its own [privacy policy](https://www.dropbox.com/privacy).

## Google Drive

If you choose to connect Google Drive, the app requests the `https://www.googleapis.com/auth/drive.file` scope. This lets Zenith create, read, update and delete **only the backup and sync files and folders it created itself** (`Zenith Backups` and `Zenith Sync`). It cannot see any other file in your Drive.

- Google user data is used solely to store and restore your Zenith data at your request.
- Data is transferred directly between your device and Google. It never passes through servers we operate.
- Google user data is not shared with, transferred to, or sold to any third party, and is not used for advertising or to train AI/ML models.
- You can disconnect at any time from the app's backup settings (which revokes the access token) or from your [Google Account permissions](https://myaccount.google.com/permissions). Files already in your Drive are kept until you delete them.

Zenith's use and transfer of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

## Third-party services

To provide some features, the app contacts public services. These services receive your IP address with any internet request and are governed by their own privacy policies. Zenith sends no account identifiers, device ID or advertising ID to them.

| Service | When | What is sent |
|---|---|---|
| jetapi.dev, adsbdb, hexdb.io, Planespotters | When you look up an aircraft or route | Aircraft registration, or callsign |
| OpenSky Network, FlyItalyAdsb | When you import a flight track | Aircraft ICAO24 address, callsign, airport and time window of the flight; your own API credentials if you entered them |
| OpenStreetMap, CARTO | When a map is shown | Map tile coordinates; your own CARTO API key if you entered one |
| OurAirports, tar1090-db (GitHub), ICAO aircraft types | Periodic reference data updates | Plain download requests, no personal data |
| GitHub (this website and release API) | Shortly after launch, to read announcements and check for app updates | Plain requests, no identifiers |

Lookups and track imports only happen when you use those features. Note that these services can therefore see that a request for a specific aircraft or flight came from your IP address at a given time.

## Exports and sharing

You can export your logbook as a PDF and save or share backup files. These actions happen only when you start them, and you choose where the file goes (for example through the system share sheet).

## Data retention and deletion

All data remains under your control. Zenith keeps no data on servers, so there is no account for us to delete. You can delete individual records in the app at any time. Uninstalling the app deletes its local data (including local backups stored in the app's private folder). Backups and sync files in Google Drive or Dropbox remain until you delete them from those services or from within the app (automatic pruning of old backups, "Delete sync data"). Data in iOS device backups is managed through your device backup settings.

## Security

Connections to cloud providers and online services use HTTPS. Secrets are kept in the platform's secure storage. As noted above, local data and uploaded backup files are not additionally encrypted by the app.

## Children

The app is not directed at children under 13.

## Changes

Changes to this policy will be published on this page with a new date.

## Contact

Questions: [winstrikerzenithlogbook@gmail.com](mailto:winstrikerzenithlogbook@gmail.com)
