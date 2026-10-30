# DNS plan: atxmasonry.com -> GitHub Pages (NOT applied yet)

Do these steps in GoDaddy DNS for atxmasonry.com, and only when we're ready to cut over.

## 1. Remove the Squarespace A records (@)
- A @ 198.49.23.144
- A @ 198.49.23.145
- A @ 198.185.159.144
- A @ 198.185.159.145

## 2. Add the GitHub Pages A records (@)
- A @ 185.199.108.153
- A @ 185.199.109.153
- A @ 185.199.110.153
- A @ 185.199.111.153

Recommended AAAA records (@), per GitHub docs:
- AAAA @ 2606:50c0:8000::153
- AAAA @ 2606:50c0:8001::153
- AAAA @ 2606:50c0:8002::153
- AAAA @ 2606:50c0:8003::153

## 3. Change www
- CNAME www: ext-sq.squarespace.com -> sgilger-source.github.io

## 4. Leave these alone
- Do NOT touch any MX or TXT records (email and verification).

## 5. After DNS (same day)
1. Add a `CNAME` file containing `atxmasonry.com` to the repo, or set the custom domain under repo Settings > Pages.
2. Recommended: verify the domain under GitHub account Settings > Pages (this adds a TXT record).
3. Once the certificate is issued, turn on "Enforce HTTPS".
4. Cancel Squarespace only after the new site loads at https://atxmasonry.com.

Note: setting the custom domain moves the github.io preview to redirect to atxmasonry.com, so don't do that before DNS moves.
