# dcape-app-unbound

[![GitHub Release][1]][2] [![GitHub code size in bytes][3]]() [![GitHub license][4]][5]

[1]: https://img.shields.io/github/release/dopos/dcape-app-template.svg
[2]: https://github.com/dopos/dcape-app-template/releases
[3]: https://img.shields.io/github/languages/code-size/dopos/dcape-app-template.svg
[4]: https://img.shields.io/github/license/dopos/dcape-app-template.svg
[5]: LICENSE

[Unbound](https://www.nlnetlabs.nl/projects/unbound/about/) application package for [dcape](https://github.com/dopos/dcape-app-unbound).

## Upstream

* Project: [Unbound](https://www.nlnetlabs.nl/projects/unbound/about/)
* Docker: [mvance/unbound](https://hub.docker.com/r/mvance/unbound)

## Requirements

* linux 64bit with git, make, sed installed
* [docker](http://docker.io)
* [dcape](https://github.com/dopos/dcape) v3
* VCS service like [Gitea](https://gitea.io)
* CI/CD service like [Woodpecker CI](https://woodpecker-ci.org/)

## Install

### Via CI/CD

* VCS: Fork or mirror this repo in your Git service
* CI/CD: Activate repo
* VCS: "Test delivery", config sample will be saved to config service (enfist in dcape)
* Config: Edit config vars and remove .sample from config name
* VCS: "Test delivery" again (or Drone: "Restart") - app will be installed and started on CI/CD host
* After that just change source and do `git push` - app will be reinstalled and restarted on CI/CD host

### Via terminal

Run commands on deploy host with [dcape](https://github.com/dopos/dcape) installed:
```bash
git clone --single-branch --depth 1 https://github.com/dopos/dcape-app-unbound.git
cd dcape-app-template
make config-if
... <edit .env.sample>
make up
```
Then next edit default unbound config in ./unbound, `make reup` for apply.

## License

Copyright 2023 Aleksei Kovrizhkin <lekovr+dopos@gmail.com>

Authors: Aleksei Kovrizhkin <lekovr+dopos@gmail.com>, Andrey Pazychev <anp135+dopos@gmail.com>

Licensed under the Apache License, Version 2.0 (the "[License](LICENSE)");