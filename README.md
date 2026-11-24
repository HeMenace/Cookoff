# Jessop Cookoff app on GitHub Pages

The whole app is `index.html`. Hosting on GitHub Pages is free. A free Firebase Realtime Database keeps all three houses in sync live. One cookoff stays far under Firebase's free Spark plan limits, and it doesn't need a credit card.

## 1. Create the Firebase database (about 5 minutes)

1. Go to https://console.firebase.google.com and click **Create a project**. You can name it anything, for example `jessop-cookoff`. You can turn Google Analytics off.
2. In the left menu, open **Build > Realtime Database** and click **Create Database**. Pick the US location, then choose **Start in test mode**.
3. Open the **Rules** tab, paste this, and click **Publish**:

   ```json
   {
     "rules": {
       "cookoff2026": { ".read": true, ".write": true }
     }
   }
   ```

   Anyone with the site link can change scores, which is fine for one party. After the event, set `.write` to `false` to freeze the results.
4. Go to **Project settings** (the gear icon) > **General** > **Your apps**, click the web icon `</>`, register an app (skip Hosting), and copy the `firebaseConfig` object it shows you.

## 2. Paste the config into index.html

Find this line near the top of the script:

```js
const FIREBASE_CONFIG=null;
```

Replace `null` with the object you copied. It needs to include `databaseURL`:

```js
const FIREBASE_CONFIG={
  apiKey: "…",
  authDomain: "jessop-cookoff.firebaseapp.com",
  databaseURL: "https://jessop-cookoff-default-rtdb.firebaseio.com",
  projectId: "jessop-cookoff",
  appId: "…"
};
```

The Firebase web config isn't a secret, so it's fine for it to be in a public repo. The database rules above are what control access.

## 3. Publish on GitHub Pages

1. Create a new public repository, for example `cookoff`, and upload `index.html` to it.
2. Go to **Settings > Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, and save.
3. After about a minute, the site is live at `https://<your-username>.github.io/cookoff/`.

Open the site on two phones. The tag at the top should say **Live · synced**. If you add a drink on one phone, it shows up on the other within a second.

## On the day

- Each house needs at least one phone with the site open. The person running it in each house uses the **My team** tab, and the judges use **Judging**.
- One person presses **Start 2 hours** in **Setup**. Every device shares the same clock.
- **Clear all results** in Setup wipes everything for everyone, so use it only to clear test data before 1 PM.
