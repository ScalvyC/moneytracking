# Ezra's Money Tracker - GitHub Pages + Supabase

This version uses GitHub Pages for hosting and Supabase for login, database storage, and syncing between laptop and phone.

## Files

- `index.html` - the full app
- `database.sql` - Supabase tables and Row Level Security policies

## Very important security note

Do not put your `sb_secret_...` key inside this app. It is only for secure backend/server code.

You already shared the secret key in chat, so rotate/regenerate it in Supabase before using the project seriously.

The publishable key can be used in frontend code when Row Level Security is enabled.

## Step 1: Enable Supabase email login

In Supabase:

1. Go to `Authentication`.
2. Go to `Providers`.
3. Enable `Email`.
4. For testing, turn `Confirm email` off.

## Step 2: Create the database tables

In Supabase:

1. Go to `SQL Editor`.
2. Paste everything from `database.sql`.
3. Click `Run`.

## Step 3: Add your Supabase Project URL

Open `index.html` and find:

```js
const SUPABASE_URL = "PASTE_YOUR_SUPABASE_PROJECT_URL_HERE";
```

Replace it with your Project URL from:

`Project Settings -> API -> Project URL`

It should look like:

```js
const SUPABASE_URL = "https://your-project-ref.supabase.co";
```

The publishable key is already placed in `index.html`.

## Step 4: Run locally

Double-click `index.html` and test:

1. Create Account
2. Add a tracker
3. Add an expense
4. Logout
5. Sign in again

## Step 5: Deploy on GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` to the root of the repo.
3. Go to `Settings -> Pages`.
4. Under `Build and deployment`, choose:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Save.

GitHub will give you a link. Open that link on your laptop and phone, then sign in with the same email and password.

## Old local data

If you had old browser-only data, open the app on that same old device, sign in, then go to:

`Trackers -> Move Old Device Data to Cloud -> Import Old Local Data`

After importing, open the app on your phone and sign in with the same account.
