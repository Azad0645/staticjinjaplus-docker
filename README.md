# StaticJinjaPlus Docker Port

Этот репозиторий содержит Docker конфигурацию для запуска и сборки образов [StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus).

## Готовые образы на DockerHub

- `fenix16450/static-jinja-plus:0.1.0` (ubuntu, версия 0.1.0)
- `fenix16450/static-jinja-plus:0.1.1` (ubuntu, версия 0.1.1)
- `fenix16450/static-jinja-plus:develop` (ubuntu, последняя main ветка)
- `fenix16450/static-jinja-plus:latest` (ubuntu, последняя стабильная = 0.1.1)

- `fenix16450/static-jinja-plus:0.1.0-slim` (python-slim, версия 0.1.0)
- `fenix16450/static-jinja-plus:0.1.1-slim` (python-slim, версия 0.1.1)
- `fenix16450/static-jinja-plus:develop-slim` (python-slim, последняя main ветка)
- `fenix16450/static-jinja-plus:slim` (python-slim, последняя стабильная = 0.1.1-slim)

Пример запуска:

```bash
docker run --rm fenix16450/static-jinja-plus:latest
```

## Сборка образов

Вместо `USERNAME` можно использовать любое имя образа, например свой логин DockerHub.

Ubuntu

```bash
docker build -f Dockerfile.ubuntu \
  --build-arg APP_REF=0.1.0 \
  --build-arg APP_TARBALL_CHECKSUM="sha256:3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444" \
  -t USERNAME/static-jinja-plus:0.1.0 .

docker build -f Dockerfile.ubuntu \
  --build-arg APP_REF=0.1.1 \
  --build-arg APP_TARBALL_CHECKSUM="sha256:30d9424df1eddb73912b0e2ad5375fa2c876c8e30906bec91952dfb75dcf220b" \
  -t USERNAME/static-jinja-plus:0.1.1 .

docker build -f Dockerfile.ubuntu \
  --build-arg APP_REF=main \
  --build-arg APP_TARBALL_CHECKSUM="sha256:9adccb8fe17a40252df1a3acdea7edef4633b4ecaa8ba2dd5e0270f87ae43eab" \
  -t USERNAME/static-jinja-plus:develop .
```

Slim

```bash
docker build -f Dockerfile.slim \
  --build-arg APP_REF=0.1.0 \
  --build-arg APP_TARBALL_CHECKSUM="sha256:3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444" \
  -t USERNAME/static-jinja-plus:0.1.0-slim .

docker build -f Dockerfile.slim \
  --build-arg APP_REF=0.1.1 \
  --build-arg APP_TARBALL_CHECKSUM="sha256:30d9424df1eddb73912b0e2ad5375fa2c876c8e30906bec91952dfb75dcf220b" \
  -t USERNAME/static-jinja-plus:0.1.1-slim .

docker build -f Dockerfile.slim \
  --build-arg APP_REF=main \
  --build-arg APP_TARBALL_CHECKSUM="sha256:9adccb8fe17a40252df1a3acdea7edef4633b4ecaa8ba2dd5e0270f87ae43eab" \
  -t USERNAME/static-jinja-plus:develop-slim .
```