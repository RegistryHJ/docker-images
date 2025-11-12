# Ubuntu Docker Images

[**DockerHub Repository Link**](https://hub.docker.com/r/registryhj/ubuntu)

<br />

## Features

- Custom APT repository mirror configuration (KAIST Mirror)
- Locale configuration (LANG=C.UTF-8)
- Timezone setup (Asia/Seoul)
- Optimized package installation and caching

<br />

## Supported Tags

- [`24.04`](https://hub.docker.com/repository/docker/registryhj/ubuntu/tags?name=24.04): (`24.04.3`, `noble`)
- [`22.04`](https://hub.docker.com/repository/docker/registryhj/ubuntu/tags?name=22.04): (`22.04.5`, `jammy`)

<br />

## How to use

**Pull this image:**

```
docker pull registryhj/ubuntu:<tag_name>
```

**Create container in background process:**

```
docker run -d -it --name <container_name> registryhj/ubuntu:<tag_name>
```

**Execute Shell Prompt:**

```
docker exec -it <container_name> bash
```

<br />

## Supported Architectures

- `linux/amd64`
- `linux/arm64`
- `linux/ppc64le`
- `linux/riscv64`
- `linux/s390x`

<br />

## Contact

For more information, visit:

- Maintainer's GitHub: https://github.com/RegistryHJ

<br />

---

Copyright © 2025 RegistryHJ
