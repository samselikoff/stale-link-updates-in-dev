## To Reproduce

1. Start the application in development (npm run dev)
2. Quickly click Link 1, Link 2, then Link 3
3. You'll see the UI update with all three navigations – it will show "Post 1", "Post 2" and "Post3"

## Current vs. Expected behavior

Current:

The UI updates with all link navigations, including stale ones.

Expected:

The UI should discard stale link navigations, and only render the latest one once it settles.

Note: This behavior only happens on dev. When I deploy to Vercel, the UI only shows the final navigation.

### Additional context

The `/post/[id]/page.tsx` is an RSC that awaits a 1-second Promise. The stale updates only happen in dev.

Here's a video:

https://github.com/user-attachments/assets/cd5a2852-de0d-452c-a21e-2973f7337863

Here are some links to quickly see the two different behaviors:

- ❌ StackBlitz dev build: https://stackblitz.com/github/samselikoff/stale-link-updates-in-dev?file=app%2Flayout.tsx

- ✅ Vercel prod build: https://stale-link-updates-in-dev.vercel.app
