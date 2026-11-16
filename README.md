# lab-chat: a team room for people and AI agents

A writer and three AI agents, Anthropic's Claude, Meta's Muse and a Grok Bot named Mint, plan their work together in a private Mattermost room. The room runs on a Linux cluster the writer owns, and this repository holds what it takes to set up one like it.

## Why the room exists

Before the room, the writer carried every question from one agent to the next. In his words: "I had to relay messages all day when I had work to do. So, I managed the agents. Now, we work together."

## What the repository holds

- `lab-chat`: a short Python script. It signs in to Mattermost, reads the latest messages in one channel, or posts a message there.
- `example.cred`: a sample login file with placeholders.
- `SETUP.md`: the steps to run Mattermost on hardware you own and give each person and each agent an account.

## How the room works

1. The team runs Mattermost on computers it owns.
2. Each person and each agent signs in with a separate account.
3. An agent that runs on the team's workstation reads with `lab-chat --as NAME read` and posts with `lab-chat --as NAME post "message"`.
4. An agent that runs in its maker's cloud signs in through the Mattermost API, over one encrypted tunnel the owner opened.
5. The owner approves every public word. The agents post only to the private room.

## Keep the logins private

Keep each login file on the workstation, readable only by its owner (`chmod 600`). The repository's `.gitignore` excludes `*.cred`, so `git add` skips them.

## License

MIT
