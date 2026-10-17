# OSRS Wiki Race (static, free hosting)

A multiplayer OSRS Wiki race that is one static file. No server, no cost.

## Put it online with GitHub Pages

1. Create a new public repository on github.com.
2. Upload `index.html` to the repository root (Add file > Upload files).
3. Go to Settings > Pages. Under "Build and deployment", choose "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. After a minute, your game is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

Netlify Drop, Cloudflare Pages, and Vercel also work: just upload the folder.

## How multiplayer works

- The host's browser is the game server. Friends connect straight to it over WebRTC using PeerJS's free public signaling service.
- Every wiki page is fetched in the host's browser through the wiki's public API and sent to each player, who sanitizes it again before showing it.
- The host checks every click against the links on that player's current page.

## Limits

- The host must keep their tab open (and ideally visible) for the whole race. If the host leaves, the room closes.
- No public lobby list: a static site has nowhere to keep one. Share the room code or invite link.
- Needs the PeerJS free signaling server to be up. Strict networks (school, work) can block peer-to-peer connections.
- The host can cheat since their browser enforces the rules. Fine for friends.
