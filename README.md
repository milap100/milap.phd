# milap.phd

Personal academic website for Milap Rajgor, built with Jekyll and hosted on GitHub Pages.

## Update the content

- `_data/profile.yml` — email, affiliation, academic profiles, and CV link
- `_data/publications.yml` — publication entries
- `_data/projects.yml` — research projects
- `_data/teaching.yml` — courses and teaching activities
- `_data/research.yml` — research themes
- `_posts/` — dated research articles written in Markdown
- `about.md` — longer biography

The data files contain commented examples in the format the site expects. For an empty list, delete its `[]` line before adding the first entry. Keep the indentation and use spaces, not tabs.

## Add a CV

Put the PDF in `assets/files/`, then set this in `_data/profile.yml`:

```yml
cv_path: "/assets/files/milap-rajgor-cv.pdf"
```

## Publish with GitHub Pages

1. Create a GitHub repository and push this folder to its `main` branch.
2. Open **Settings → Pages** in that repository.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Select the `main` branch and `/(root)`, then save. GitHub Pages rebuilds the Jekyll site after every push.
5. In **Custom domain**, enter `milap.phd` and save.
6. Once GitHub finishes its DNS check and provisions the certificate, enable **Enforce HTTPS**.

The included `CNAME` contains `milap.phd`.

## Porkbun DNS

Open **Domain Management**, locate `milap.phd`, click **DNS**, and remove default parking/forwarding records that conflict with the root or `www`. Add:

| Type | Host | Answer / value |
|---|---|---|
| A | leave blank | `185.199.108.153` |
| A | leave blank | `185.199.109.153` |
| A | leave blank | `185.199.110.153` |
| A | leave blank | `185.199.111.153` |
| CNAME | `www` | `YOUR_GITHUB_USERNAME.github.io` |

Replace `YOUR_GITHUB_USERNAME` with the account that owns the repository. Leave TTL at Porkbun's default. Do not add a wildcard (`*`) record. Because the custom domain is the apex `milap.phd`, GitHub Pages will redirect `www.milap.phd` to `milap.phd` after both DNS variants are configured.

## Recommended domain verification

In your GitHub account, open **Settings → Pages → Add a domain**, enter `milap.phd`, and copy the TXT record GitHub provides into Porkbun. Keep that TXT record in place; it protects against domain takeover.

## Optional local preview

With Ruby and Bundler installed:

```sh
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

The 1200 × 630 social-sharing image is `assets/images/og.png`.
