# proj1

Simple static HTML site, deployed via GitHub Pages, served on **gowripawate.in** (domain purchased on HostingRaja).

## Deploy (GitHub Pages)

1. Push this repo to `main`:
   ```
   git push -u origin main
   ```
2. On GitHub: repo **Settings → Pages** → under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
3. Under **Custom domain**, enter `gowripawate.in` and save (this repo already has a `CNAME` file with that value, so GitHub should pick it up automatically — but set it in the UI too so GitHub provisions HTTPS).
4. Wait for the DNS check to pass (see below), then tick **Enforce HTTPS** once it's available.

## DNS records (set these in HostingRaja's DNS management panel for gowripawate.in)

Apex domain (`gowripawate.in`) → 4 A records pointing at GitHub Pages:

| Type | Host/Name | Value             |
|------|-----------|--------------------|
| A    | @         | 185.199.108.153    |
| A    | @         | 185.199.109.153    |
| A    | @         | 185.199.110.153    |
| A    | @         | 185.199.111.153    |

`www` subdomain (optional, recommended so `www.gowripawate.in` also works):

| Type  | Host/Name | Value                |
|-------|-----------|-----------------------|
| CNAME | www       | vcpawate.github.io.   |

Notes:
- Remove/replace any existing A or CNAME record already on `@` in HostingRaja's panel before adding these (having conflicting records is the most common reason Pages custom domains fail).
- DNS propagation can take anywhere from a few minutes to a few hours.
- Once DNS resolves correctly, GitHub Pages will auto-issue an HTTPS certificate for the domain.
