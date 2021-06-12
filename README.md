# Docker CLI Helpers

## Installation

```
cd ~/
git clone https://github.com/devimust/docker-cli-helpers
cd docker-cli-helpers
cp .env.example .env
# modify .env file with your computer preferences
docker-compose build
```

## Usage

Create a new laravel app and run composer

```
cd ~/dev
docker-compose -f ~/docker-cli-helpers/docker-compose.yml run --rm laravel new blog

cd ~/dev/blog
docker-compose -f ~/docker-cli-helpers/docker-compose.yml run --rm composer update
```

## Examples

Add these lines to your bash profile file:

```
laravel () {
  docker-compose -f ~/docker-cli-helpers/docker-compose.yml run --rm laravel "$@"
}

composer () {
  docker-compose -f ~/docker-cli-helpers/docker-compose.yml run --rm composer "$@"
}
```

Then you can use them as if they were natively installed. e.g.

`cd ~/dev && laravel new blog`

`cd blog && composer update`
