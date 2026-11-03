# NUEVE Studio

Static website for NUEVE Studio (Yatazil Farouk): one `index.html` with no build step, plus `img/`, `vid/` and `fonts/`.

## Deploy on Cloudflare Pages

1. Push this repository to GitHub.
2. In Cloudflare: **Workers & Pages → Create → Pages → Connect to Git**, then pick the repository.
3. Build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/`
4. Deploy, then add your domain under **Custom domains**.

Alternatively, with the Wrangler CLI: `npx wrangler pages deploy . --project-name nueve-studio`

## Notes

- `_headers` sets caching (fonts 1 year, images and videos 30 days, HTML always revalidated) and basic security headers.
- Every file is under Cloudflare Pages' 25 MiB per-file limit; videos are H.264 MP4, 1080p, no audio.
- When you replace an image or video, give it a new file name (or wait for the 30-day cache to expire) so visitors get the new version.
- Fonts are self-hosted (Archivo and JetBrains Mono, SIL Open Font License; see `fonts/`).
- The contact form does not send anything yet: connect it to a form service before going live.
