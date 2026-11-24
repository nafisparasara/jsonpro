# JSONPro static website

## Folder structure

```text
jsonpro-site/
├── index.html
├── about.html
├── contact.html
├── privacy-policy.html
├── terms.html
├── disclaimer.html
├── security.html
├── favicon.svg
├── robots.txt
├── sitemap.xml
├── ads.txt
├── _headers
└── README.md
```

## Deploy to Cloudflare Pages

1. Upload this folder to a GitHub repository (or replace the files in your existing repository).
2. In Cloudflare Pages, connect the repository or trigger a new deployment.
3. Use the project root as the build directory. No build command is required; this is a static HTML site.
4. Set the custom domain to `jsonpro.com` and choose one canonical host. Configure a redirect from `www.jsonpro.com` to `https://jsonpro.com/` (or reverse this consistently).
5. Open every page on the deployed domain and test the tools on desktop and mobile.
6. Submit `https://jsonpro.com/sitemap.xml` in Google Search Console.

## Before launch

- Confirm that you own and control `jsonpro.com`. Update every canonical URL and sitemap URL if your final domain differs.
- Verify all tools and conversion outputs with representative test data.
- Review legal pages against your actual hosting, logging, analytics and advertising configuration. These templates are not legal advice.
- The `ads.txt` file is a placeholder. Replace it with the exact seller record shown in your own AdSense account when Google provides one. Do not leave the example publisher ID active.
- Do not add AdSense code until your publisher account supplies the exact script and publisher ID. Update the CSP to allow the required Google ad domains when ads are installed.
- The current app uses Tailwind's browser CDN and Google Fonts. For a stricter production supply chain, pin/build Tailwind locally and self-host fonts before removing the external CSP allowances.
- The app's inline event handlers require `'unsafe-inline'` in `script-src`; this is a compatibility compromise. A future hardening pass should replace inline handlers with `addEventListener`, move scripts to versioned files, and use a nonce/hash-based CSP.

## Security notes

- JSON inputs are capped at 5 MiB in the main formatter editor. The diff, converter, JSONPath and JWT panels should also be used with reasonable payload sizes.
- JWT decoding does not verify signatures.
- Browser-side processing does not guarantee device security or protect against malicious browser extensions, compromised devices or third-party asset providers.
