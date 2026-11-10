---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Please review this command-line tool for how people will use it. `shipit` is used at a small web agency by the developers and also by two project managers, who deploy content updates about once a week and always to the same place. You cannot run it; its help output and behaviour are below.

```
$ shipit --help
usage: shipit [-h] [-e ENV] [-t TGT] [-x] [-f] [-q] {push,purge,st}

options:
  -h, --help
  -e ENV, --env ENV
  -t TGT, --target TGT
  -x, --migrate
  -f, --force
  -q, --quiet

$ shipit push
ERR 12

$ shipit push -e prod -t web-03
$                                   (uploads the release; prints nothing; exit code 0)

$ shipit purge -e prod
$                                   (deletes every deployed release on prod at once; prints nothing)

$ shipit st
web-03 r214 ok
```

Notes from the maintainers: ERR 12 means that --env is missing. -e and -t are required for every push; there is no configuration file. The project managers always use `-e prod -t web-03`.
