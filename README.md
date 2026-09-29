# Safety notice
This repository is a static training fixture for GitHub security scanning.
- No malware, payloads, network listeners, authentication bypass, or working credentials.
- Do not deploy or execute the sample application code.
- All secrets are synthetic and intentionally invalid.
- Use only in a dedicated public training repository with no production data.

# Lab 1: Secret scanning
Goal: demonstrate secret scanning without using a real credential.

`training.env` contains unmistakably synthetic, revoked-looking placeholders. Provider-pattern detection is not guaranteed because the values are intentionally invalid. For a deterministic demo, configure a custom secret pattern named `Training token` with this regex:

```regex
TRAINING_TOKEN_[A-Z0-9]{24}
```

Then push a branch containing `training.env`. If push protection is enabled for the custom pattern, GitHub can block the push. Otherwise, use the resulting secret-scanning alert.

Never use a real token, even temporarily.
