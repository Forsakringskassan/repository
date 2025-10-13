# Repository

This is a GitHub repository that we only use for publishing packages.

## Setup

To consume these packages you need Github credentials.

- Go to <https://github.com/settings/tokens>
- You only need `read:packages`
- Add the environment variables:
  - `GITHUB_TOKEN=the-token`
  - `GITHUB_ACTOR=your-github-user`

How to use the credentials depends on use case:

- Gradle, see https://github.com/Forsakringskassan/gradle-conventions
- Maven, see https://github.com/Forsakringskassan/fk-maven/

When using Docker, login with:

```sh
echo $GITHUB_TOKEN | docker login ghcr.io -u $GITHUB_ACTOR --password-stdin
```

And run an image like:

```sh
docker run -d \
  -p 8080:80 \
  ghcr.io/forsakringskassan/designsystem-user-app:snapshot
```

In this case, you can browse to it at http://localhost:8080/

List running apps with:

```sh
docker ps
```

Stop a running app with:

```sh
docker stop <CONTAINER I>
```
