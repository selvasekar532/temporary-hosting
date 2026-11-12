# Ithought / Milestones2Wealth Quiz - GitHub Pages

This repository hosts the static participant website on GitHub Pages.

## Important backend requirement

GitHub Pages only hosts static files. It does **not** run the quiz database, secure scoring API, duplicate-email validation or shared live leaderboard.

The `index.html` therefore needs the Supabase Edge Function URL configured before the quiz can operate:
1. Open `index.html`.
2. Find:
   `const API_URL = "REPLACE_WITH_SUPABASE_FUNCTION_URL";`
3. Replace the placeholder with your deployed Supabase function URL:
   `https://YOUR_PROJECT_REF.supabase.co/functions/v1/quiz-api`
4. Commit the updated file.

Deploy the backend separately to Supabase using the private backend source from the complete application package. **Do not put the backend folder or service-role key in this public GitHub repository.** The backend source contains the answer key and should be kept in a private repository or a trusted local deployment folder. Never put a Supabase `service_role` key in `index.html`, GitHub Pages, or any browser code.

## Publish on GitHub Pages

1. Create a GitHub repository, for example `ithought-financial-wellness-quiz`.
2. Upload `index.html`, the `.github` folder and this README to the repository root.
3. Commit to the `main` branch.
4. Open the repository **Settings → Pages**.
5. Under **Build and deployment**, choose **GitHub Actions** as the source.
6. Open the **Actions** tab and wait for `Deploy Ithought quiz to GitHub Pages` to finish successfully.
7. Your public URL will be:
   `https://YOUR-GITHUB-USERNAME.github.io/REPOSITORY-NAME/`

## QR code

Once the GitHub Pages URL is live, create a QR code that points to that exact URL. Test it on at least two phones before printing.

## Included
- `index.html`: Milestones2Wealth-branded participant interface, quiz, result, public leaderboard UI and organiser UI.
- `.github/workflows/pages.yml`: automatic GitHub Pages deployment on every push to `main`.

## Final testing required

Before the event, verify that the Supabase backend is deployed and configured, then test registration, 7-minute timer, answer syncing, scoring, duplicate email rejection, shared leaderboard updates, organiser access and QR scanning from separate devices. GitHub Pages publishing alone does not complete these backend functions.
