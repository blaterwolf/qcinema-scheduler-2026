# QCinema 2026 Planner

**Open the planner:** [blaterwolf.github.io/qcinema-scheduler-2026](https://blaterwolf.github.io/qcinema-scheduler-2026/). It works in any browser on your phone or computer, with nothing to install or sign in to.

A schedule planner for the QCinema International Film Festival 2026 (Nov 13–22, Quezon City). Pick screenings from the full festival schedule, add your own films and talks, add posters, and save your plan as one image for X or an iPhone wallpaper.

Everything you add is saved in your own browser only (localStorage for the schedule, IndexedDB for posters). Nothing is sent anywhere, and nothing syncs between devices. Each visitor gets their own empty planner.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app |
| `schedule.json` | Snapshot of the official festival schedule (as of Nov 8, 2026) |
| `logos/qc14.png`, `logos/genreteurs.png` | Header and share-image logos |

## Put it on GitHub Pages

1. On github.com, click **New repository**. Name it (for example `qcinema-scheduler-2026`) and set it to **Public**.
2. In the new repository, click **Add file → Upload files**. Drag in `index.html`, `schedule.json`, `README.md` and the `logos` folder, then click **Commit changes**.
3. Go to **Settings → Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main** and folder **/ (root)**, then click **Save**.
4. Wait a minute or two. The **Actions** tab shows a "pages build and deployment" run; when it's green, the site is live at `https://<your-username>.github.io/qcinema-scheduler-2026/`.

To change anything later, upload the new file over the old one and commit. The site redeploys on its own.

### Or push with git

Create the repository on GitHub empty (no README or license), then in this folder:

```
git init
git add .
git commit -m "QCinema 2026 scheduler"
git branch -M main
git remote add origin https://github.com/<your-username>/qcinema-scheduler-2026.git
git push -u origin main
```

Then turn on Pages as in step 3. After that, every `git push` redeploys the site.

## Run it locally (XAMPP)

Put the folder in `C:\xampp\htdocs\qcinema-scheduler-2026`, start Apache in the XAMPP Control Panel, and open `http://localhost/qcinema-scheduler-2026/`. Each address keeps its own saved plan, so use Export/Import to move a plan between localhost and the GitHub Pages site.

Open the site from its web address. Opening `index.html` straight from your computer won't load the festival schedule.

## Moving your plan between devices

Use **Back up your plan** at the bottom of the page:

- **Export backup** saves a `.json` file with your schedule and posters.
- **Import backup** on another device or browser loads that file. If that browser already has entries, it asks before replacing them.

Clearing the site's data deletes your plan, and Safari can clear it if you don't open the site for about a week, so export a fresh backup after big changes. Don't upload your backup file to the repository: anyone could download it.

## Updating the festival schedule

If the festival changes times, replace `schedule.json` with a newer snapshot in the same format. Festival entries only store the screening id, so everyone's planner picks up the new times and cinemas on their next visit.
