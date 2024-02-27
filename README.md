# Laravel Docker

Laravel Docker is a docker configuration for laravel ecosystem

## Installation

Use docker [compose](https://docs.docker.com/compose/) for build the image

```bash
docker-compose up --build
```

## Usage

### Composer

```bash
docker-compose run --rm composer [command] [options] [arguments]
```

Create a laravel project

```bash
docker-compose run --rm composer create-project laravel/laravel .
```

### Artisan
```bash
docker-compose run --rm artisan <command> [options] [arguments]
```

### NPM
```bash
docker-compose run --rm npm <command>
```

### Testing

Uncomment the testing section from [docker-compose.yml](./docker-compose.yml):

```yml
  # test:
  #   build:
  #     context: .
  #     dockerfile: php.test.dockerfile
  #   volumes:
  #     - ./src:/var/www/html
  #   entrypoint: ["/var/www/html/artisan", "test", "--coverage-html", "/var/www/html/storage/framework/testing/coverage"]
  #   working_dir: /var/www/html
```

Then run again `docker-compose up`

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](./LICENSE.md)