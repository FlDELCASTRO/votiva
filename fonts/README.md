# Fonts

Phase 1 loads Sora, Inter and Kantumruy Pro from Google Fonts via a `<link>` in
`index.html`. That is the quickest correct thing and it is cached by Google's
CDN, but it costs an extra DNS lookup and connection on first paint.

Phase 6 (performance pass, target < 2s first load on 4G) self-hosts them here:
download the woff2 subsets, drop them in this folder, declare `@font-face` in
`src/styles/tokens.css` with `font-display: swap`, and delete the `<link>`.
Khmer subsets are large, so subset Kantumruy Pro to the Khmer block plus Latin.
