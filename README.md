# maestro-project-agent

Hermes [profile distribution](https://hermes-agent.nousresearch.com/docs/user-guide/profile-distributions) that [MAESTRO](https://github.com/p-sw/maestro-skill) installs for every project agent.

It ships only the base config (Hindsight as the memory provider). It never carries memories, sessions, `.env` or messaging credentials. MAESTRO writes each project's `SOUL.md` and memory files after installing, so they are not distribution-owned and `hermes profile update` leaves them alone.

```bash
hermes profile install github.com/p-sw/maestro-project-agent --name proj-<slug> --yes
hermes profile update proj-<slug>      # pull a newer version; config.yaml is kept unless --force-config
hermes profile info proj-<slug>
```

Required env: `HINDSIGHT_API_KEY` (and optionally `HINDSIGHT_API_URL`); see `distribution.yaml`.
