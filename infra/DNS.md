# Growlrr DNS & GitHub Pages notes

## Custom domain
www.growlrr.com -> CNAME -> growlrr.github.io

## Apex (growlrr.com) recommended A records (GitHub Pages)
Add these A records (host = @):
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

## www record
Add CNAME:
- host: www
- value: growlrr.github.io

## Verify DNS propagation
Use:
  dig +short www.growlrr.com
  dig +short growlrr.com
  curl -I https://www.growlrr.com || true

If you see 404 from GitHub pages, check:
- Repo -> Settings -> Pages -> Source = main / /
- CNAME file present in repo root (contains www.growlrr.com)
- Wait ~5–15 mins for DNS / cert provisioning

## Notes
- If you need the apex served, ensure the A records are added on Namecheap.
- To change hosting to Vercel, update the DNS and point the domain per Vercel instructions.
