# Ali Egal — Personal Website

## Access

Website: **[ali-e.net](https://ali-e.net)**

Source: [github.com/aliegal16-prog/personal-website](https://github.com/aliegal16-prog/personal-website)

## Development Notes

### Stack

- **Static site generator:** Jekyll 4.x
- **Hosting:** GitHub Pages
- **Domain:** Custom TLD registered via Cloudflare Registrar
- **HTTPS:** Automatically provisioned by GitHub Pages via Let's Encrypt

### Structure

```
.
├── _config.yml          # Jekyll configuration
├── _layouts/
│   └── default.html     # Base HTML layout
├── assets/css/
│   └── style.css        # Custom styles (no theme dependency)
├── index.html           # Main page content
├── CNAME                # Custom domain for GitHub Pages
├── Gemfile              # Ruby dependencies
└── README.md
```

### Custom Domain Setup (Part 2)

1. Registered domain through Cloudflare Registrar.
2. Added GitHub Pages IP addresses as A records in Cloudflare DNS:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
3. Added a `CNAME` record pointing `www` to `aliegal16-prog.github.io`.
4. Added the `CNAME` file to the repository root.
5. Set the custom domain in GitHub Pages settings.

**DNS propagation observation:** DNS updates were visible on `8.8.8.8` (Google Public DNS) before resolving locally, demonstrating how changes propagate through the DNS hierarchy before reaching local resolvers.

### HTTPS / Certificate (Part 3)

GitHub Pages automatically provisions a certificate from **Let's Encrypt** once the custom domain resolves correctly. After DNS propagated, the "Enforce HTTPS" option became available in the GitHub Pages settings. The certificate was issued within a few minutes.

### AI Usage

Site content was drafted with assistance from Claude (Anthropic). All technical setup, configuration, DNS records, and deployment steps were performed manually. The design and CSS were generated in collaboration with Claude and reviewed/adjusted for correctness and personal preference.
