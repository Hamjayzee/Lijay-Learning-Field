LIJAY Learning Field — beginner starter
A responsive web/PWA prototype that can be extended into an Android app. It currently includes:
responsive navigation and learning-category placeholders

student registration with optional resized photo

local demo student directory and CSV export

WhatsApp link after a valid international number is entered

basic PWA manifest and service worker


Important limitations

This is a prototype, not a production school system. Student records are stored in the current browser's localStorage; they do not sync between devices and can be cleared by the browser. Do not use real children's records yet. There is no login, server database, payment processing, teacher/admin role system, attendance, grades, or full picture editor connected.


Run it on your computer


Install a current version of Node.js from https://nodejs.org (LTS).

Open a terminal/command prompt in this folder.

Run npx serve . and accept installation if prompted.

Open the local URL shown in the terminal.
For PWA installation, serve it over HTTPS or localhost; opening index.html directly is not enough for service-worker features.


You can also upload the folder to a static web host that supports HTTPS.


Android next step (after the web version is tested)


Install Node.js and Android Studio.

In this folder, run npm init -y.

Run npm install @capacitor/core @capacitor/cli @capacitor/android.

Run npx cap init "LIJAY Learning Field" "com.lijay.learningfield" --web-dir .

Run npx cap add android.

Open the Android project with npx cap open android.

Use Android Studio to test on a phone/emulator and build an APK.


Capacitor setup commands can change with versions; check the current official Capacitor documentation before packaging. For a public release, configure HTTPS, authentication, secure database access, privacy notices, and backups first.


Recommended production architecture


Frontend: this responsive web app, later migrated to a maintained framework if desired.

Backend/database: Supabase or Firebase with authentication and row-level permissions.

Images: private storage buckets with file-size/type validation.

Payments: a reputable payment provider; never store card details yourself.

Roles: student, teacher, guardian, administrator.

Child safety: collect only necessary information, get appropriate guardian consent, and restrict access to children's records.


WhatsApp number

Enter the complete number in international digits format, e.g. 2348031234567 (Nigeria country code 234, omit the leading zero). The previously provided 0703972060 appears incomplete, so the app does not hard-code it.

