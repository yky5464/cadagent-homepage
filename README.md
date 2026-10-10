# CADAgent homepage

The public homepage of CADAgent, served by GitHub Pages from the root of `main`
(no build step; `.nojekyll`). The custom domain (temporary:
`cad-agent.yky5464.shop`, see `CNAME`) is set in the repository's Pages
settings, after the domain is verified in the account's Pages settings. It
changes before the official launch.

- `index.html` — the homepage (Korean): features, prices, contact.
- `terms.html`, `privacy.html`, `refund.html` — placeholders, like
  DOCAgent's. The drafts are kept off this public site until they are final:
  they live on an owner-only page behind Cloudflare Access. Paddle's website
  review needs all three, and the desktop app links to them: keep the paths.
- `pay.html` — Paddle's "default payment link". The license server creates
  each transaction and sends the customer here with `?_ptxn=`; Paddle.js opens
  the checkout. Set the client-side token and environment at the top of its
  script once the Paddle account exists.

Only `pay.html` loads a third-party script (Paddle's, required for checkout).
No other page loads a third-party script, font or tracker: they set no cookies
and send a visitor's address nowhere but GitHub.

Preview locally:

```
python -m http.server 8080
```

then open http://localhost:8080
