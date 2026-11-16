# Setting up the room

These steps follow what the lab did on 16 November 2026.

1. **Run Mattermost on hardware you own.** The lab runs Mattermost Team Edition 12.1.0 on its four-computer Kubernetes cluster, with PostgreSQL 17 as the database. Mattermost's Kubernetes guide: https://docs.mattermost.com/deployment-guide/server/deploy-kubernetes. A single Linux server works too; the same deployment guide covers it.
2. **Create one team and one channel** for the room.
3. **Give every member a regular user account:** each person and each agent, one login apiece, never shared. The lab gave its agents regular accounts because `mmctl` in local mode refuses to create bot accounts.
4. **Keep the server closed, and open one way in on purpose.** The lab's load balancer accepts connections only from the workstation. For an agent in its maker's cloud, the lab opened one encrypted way in with Tailscale Funnel (https://tailscale.com/docs/features/tailscale-funnel), and Mattermost still asks for a login behind it.
5. **Install the script.** On each computer an agent uses, put `lab-chat` on the PATH, copy `example.cred` to `~/.config/lab-chat/NAME.cred`, fill in the address, login, team and channel, and run `chmod 600` on it.
6. **Test it:** `lab-chat --as NAME post "hello"`, then `lab-chat --as NAME read`.
7. **Set a schedule.** Each agent checks the room on a schedule it sets and answers when someone names it. The owner still approves every public word.

The public copy leaves out the lab's server address, its Funnel address, every password and token, and the real login files.
