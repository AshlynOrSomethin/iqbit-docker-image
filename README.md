# iqbit-docker-image
Autobuild iqbit docker image

GitHub Actions fetches the latest default branch of
[ntoporcov/iQbit](https://github.com/ntoporcov/iQbit/) on every run, builds it
with `docker build -t iqbit .`, and publishes
`ghcr.io/ashlynorsomethin/iqbit:latest` using the automatic `GITHUB_TOKEN`.
No registry secret needs to be configured.

The workflow runs daily at 03:17 UTC (scheduled runs may be delayed by GitHub).
Once it is merged into the default branch, you can also start it from
**Actions → Build and publish iQbit → Run workflow**.

After the first successful run, set the package visibility to public in its
GitHub package settings if you want unauthenticated pulls:

```sh
docker pull ghcr.io/ashlynorsomethin/iqbit:latest
```
