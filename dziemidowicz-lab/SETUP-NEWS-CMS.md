# Setting up your News editor (Decap CMS)

Everything is built and ready in this folder. Two short manual steps remain — both happen on free, existing accounts (GitHub and Netlify), and neither requires writing any code.

## Step 1 — Upload everything to your GitHub repo

Upload the **entire contents** of this folder to your `kdziemidowicz.github.io` repository, keeping the folder structure exactly as is:
- `admin/` (contains index.html and config.yml)
- `_posts/` (contains your sample news post)
- `_layouts/` (contains the post.html template)
- `uploads/` (empty for now — images you add via the CMS will land here)
- `_config.yml` (tells GitHub Pages to run Jekyll)
- `news.html`
- Your existing five pages (already updated with a "News" nav link)

GitHub's web uploader supports drag-and-drop of folders, so you can drop this whole directory in at once via **Add file → Upload files**.

**Important:** open `admin/config.yml` and replace this line:
```
repo: kdziemidowicz/kdziemidowicz.github.io
```
with your actual GitHub username and repository name if different.

## Step 2 — Connect Netlify as the login bridge

Decap CMS needs somewhere to handle the "Login with GitHub" button — Netlify provides this for free, and you don't need to host anything there.

1. Go to [app.netlify.com](https://app.netlify.com) and sign up free (you can sign up using your GitHub account directly — same login).
2. Click **Add new site → Import an existing project → Deploy with GitHub**.
3. Select your `kdziemidowicz.github.io` repository. Netlify will try to deploy it — that's fine, you can ignore the resulting Netlify URL entirely; you're only using this to register the OAuth connection.
4. Once the site exists in Netlify, go to **Site configuration → Identity** (or search "OAuth" in settings) and follow the prompt to **enable Git Gateway / GitHub OAuth provider**. This generates the connection Decap's login screen uses.

## Step 3 — Use it

Go to:
```
https://kdziemidowicz.github.io/admin
```
Click **Login with GitHub**, authorize the app once, and you'll see the News collection with your sample post. Click **New News**, fill in the title, date, summary, and body, hit **Publish**. Decap commits a new markdown file straight to your repo — GitHub Pages rebuilds automatically, and your new post appears on `/news.html` within a minute or two.

## What you'll never need to touch again
Writing a post = filling in four fields and clicking Publish, from any browser, no code, no GitHub interface. The technical wiring above only needs to happen once.
