# WordPress 7.1.3 on PHP 8.5.12 FPM Alpine

Minimal `linux/amd64` build using PHP 8.5.12, which fixes CVE-2026-109618 and CVE-2026-109619 (PHP2Shell). See the [PHP security release](https://www.php.net/archive/2026.php#2026-10-21-1).

## Build

```bash
docker build --pull --platform linux/amd64 \
  -t wordpress-local:7.1.3-php8.5.12-fpm-alpine .
```

## Verify

```bash
docker run --rm --network none --entrypoint php \
  wordpress-local:7.1.3-php8.5.12-fpm-alpine -v

docker run --rm --network none --entrypoint php-fpm \
  wordpress-local:7.1.3-php8.5.12-fpm-alpine -tt
```

Derived from [`docker-library/wordpress`](https://github.com/docker-library/wordpress/tree/2d7faab7fb71508e6854cdbed948c195957f279e) and licensed under GPL-2.0. See [LICENSE](LICENSE).
