# parcel-bad-tagged-templates

Codegen for tagged template literals creates one `let _ = (t)=>t` function per file and they don't get renamed as files are merged.

```
$ parcel build src/index.html
🚨 Build failed.

@parcel/optimizer-terser: "_" is redeclared

    2885 | 
  > 2886 | let _ = (t)=>t
  >      |    ^ "\_" is redeclared
    2887 | , t;
    2888 | const $85deba37093b6689$export$c9cacf6069bed432 = $cc85e8b8e7405a89$export$2e2bcd8739ae039.div(t || (t = _`

  💡 It's likely that Terser doesn't support this syntax yet.
```
