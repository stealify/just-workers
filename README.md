# just-workers
Build Tooling for v8::isolates inspired by just-js packaged as stealifyVm binarys the fastest worker implementation with minimal overhead
https://www.techempower.com/benchmarks/#section=data-r20&hw=ph&test=composite ranking on 2. in the overall score at this benchmark case prooves that.
Combined with haproxy or iptables + systemd socket activation. allows to run many instances on a single server.

## Roadmap
- finish the api parts
  - allow a user to package simple js code into a linux32 or 64 binary
  - haproxy config parser and writer
  - haproxy management (kernel)
  - iptabeles management (kernel)
  - handle systemd socket activation
  - handle instance start stop protocol metrics logging via systemd
  - implement own spawn server based on a http3 enabled backend that takes the request as backup and then spawns and proxys that all new request will get fullfilled by the spawned main 

## Structure
- /gui
  - /ide = Graphical Client (powered by eclipse project theia)
  - /compiler = Graphical Client for the v8::isolates compiler tooling
- /api
  - /rest = http3 rest endpoint
- /modules = universal ECMAScript code main source and logic
- /subrepos = 3th party dependencies where we contribute back get exposed via wrapper file in /modules
- /dependencies = external dependencies managed via pnpm for /modules
