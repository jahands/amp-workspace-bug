# amp-workspace-bug

I found a bug where @'ing a file crashes amp when using a vscode workspace where one of the folders is a subdirectory of the repo (seems to require multiple folders to repro). This happens in Cursor, but not VS Code.

## Environment

System: MacOS Sequoia 15.5

Cursor version:

```
Version: 1.2.4 (Universal)
VSCode Version: 1.99.3
Commit: a8e95743c5268be73767c46944a71f4465d05c90
Date: 2025-07-10T16:55:16.443Z (1 day ago)
Electron: 34.5.1
Chromium: 132.0.6834.210
Node.js: 20.19.0
V8: 13.2.152.41-electron.0
OS: Darwin arm64 24.5.0
```

Amp extension version:

```
Identifier
sourcegraph.amp
Version
0.0.1752293794
Last Updated
2025-07-12, 06:17:48
```

## Repro Steps

1. Clone this repo

```sh
git clone https://github.com/jahands/amp-workspace-bug.git
```

2. Open this project using the workspace amp-workspace-bug.code-workspace

```sh
cursor amp-workspace-bug/amp-workspace-bug.code-workspace
```

3. Open Amp chat and start a new thread

4. Start typing @ followed by random characters. e.g. `@lsdkfjsdlfkjsdf`

5. At this point, Amp freezes (for me anyway), and the only way to fix it is to quit all instances of Cursor and re-open the project. It repro's 100% of the time for me.
