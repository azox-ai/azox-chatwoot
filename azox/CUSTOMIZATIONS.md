# Azox customizations on Chatwoot

Upstream: https://github.com/chatwoot/chatwoot
Baseline: tag `v4.18.0`, commit `9f920b549c14491a4e587687a3eed5d21c6ccc7d` (branch `azox/v4.18.0`).

Each customization lives on its own `azox/feat/*` branch from the baseline so it can be
re-applied, retired or redesigned independently when upgrading upstream.

| ID | Branch | Purpose | Files | Test | Retire when |
|---|---|---|---|---|---|
| AZX-CW-001 | `azox/feat/avatar-image-jpg-alias` | Accept Zalo CDN avatars sent with the non-standard `Content-Type: image/jpg`; store them as `image/jpeg`. Without it every Zalo contact avatar is rejected. | `app/jobs/avatar/avatar_from_url_job.rb` | `spec/jobs/avatar/avatar_from_url_job_spec.rb` ("normalizes Zalo image/jpg avatar responses") | Upstream accepts `image/jpg` for avatar URL downloads (verify with the spec on clean upstream). |
