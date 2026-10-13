# Paper Fix Tracker (GitHub Pages + Firebase)

Shared checklist: everyone's ticks and notes appear live for the whole team.

## 1. Put it on GitHub (about 3 minutes)
1. github.com → New repository → name it `paper-tracker` → Public → Create.
2. Add file → Upload files → drag in `index.html`, `README.md`, `firestore.rules` → Commit.
3. Settings → Pages → Source: "Deploy from a branch", Branch: `main`, folder `/ (root)` → Save.
4. After about a minute your site is at `https://YOUR-USERNAME.github.io/paper-tracker/`.

## 2. Create the shared database (about 5 minutes, free)
1. console.firebase.google.com → Add project (turn Google Analytics off).
2. Build → Firestore Database → Create database → choose a region (asia-southeast1 is closest) → Start in production mode.
3. Rules tab → paste the contents of `firestore.rules` → Publish.

## 3. Connect the site to the database
1. Project settings (gear) → Your apps → Web (`</>`) → register app → copy the `firebaseConfig` values.
2. On GitHub open `index.html` → pencil icon → find `var FB={...}` near the top → paste `apiKey`, `authDomain`, `projectId`, `appId` → Commit.
3. Open the site, pick your initials, tick a task. Open it on a second phone to check that it appears there.

## Notes
- The Firebase web `apiKey` is not a secret; the rules are what protect the data. These rules let anyone with the link tick tasks, so don't post the link publicly.
- The free Spark plan covers 50K reads and 20K writes a day, far more than 5 people need.
- With the key left empty, the page still works but saves only on that device.
- To change the tasks, edit the `T=[...]` list in `index.html`. Existing ticks stay tied to the task `id`.
