# Cron Jobs

## What is Cron?

Cron is a Linux service that automatically runs commands or scripts at scheduled times.

It is commonly used to:

- Back up files
- Restart services
- Run maintenance tasks
- Execute scripts automatically

---

## Cron Schedule Format

```
* * * * * command
│ │ │ │ │
│ │ │ │ └── Day of Week (0-6, 0 = Sunday)
│ │ │ └──── Month (1-12)
│ │ └────── Day of Month (1-31)
│ └──────── Hour (0-23)
└────────── Minute (0-59)
```

| Field | Values |
|--------|--------|
| Minute | 0-59 |
| Hour | 0-23 |
| Day of Month | 1-31 |
| Month | 1-12 |
| Day of Week | 0-6 (0 = Sunday) |
| Command | Command or script to execute |

---

## Special Characters

| Symbol | Meaning |
|---------|---------|
| `*` | Every value |
| `,` | Multiple values |
| `-` | Range |
| `/` | Step interval |

Example:

```bash
*/5 * * * * backup.sh
```

Runs every 5 minutes.

---

## Common Examples

Every day at 2:00 AM

```bash
0 2 * * * backup.sh
```

Every hour

```bash
0 * * * * script.sh
```

Every Monday at 8:30 AM

```bash
30 8 * * 1 report.sh
```

Every 10 minutes

```bash
*/10 * * * * cleanup.sh
```

---

## Managing Cron Jobs

Edit your cron jobs:

```bash
crontab -e
```

List scheduled jobs:

```bash
crontab -l
```

Remove all jobs:

```bash
crontab -r
```

---

## Real-World Uses

- Daily database backups
- Log cleanup
- Email reports
- Restart services
- Run monitoring scripts
- Execute scheduled automation

---

## Key Takeaways

- Cron automates repetitive tasks.
- Jobs are defined in the crontab file.
- Cron uses a 5-field scheduling format.
- `crontab -e` edits jobs.
- `crontab -l` lists jobs.