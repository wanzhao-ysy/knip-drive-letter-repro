# knip-drive-letter-repro

Minimal reproduction for [webpro-nl/knip#2396](https://github.com/webpro-nl/knip/issues/2396).

Requires Windows: npm links workspaces as directory junctions there, and the bug depends on drive-letter casing.

```sh
npm install
npx knip --directory "C:\path\to\knip-drive-letter-repro"   # exit 0, no issues
npx knip --directory "c:\path\to\knip-drive-letter-repro"   # exit 1
```

The lowercase run reports:

```text
Unused exports (1)
used  packages/lib/src/index.ts:1:14
```
