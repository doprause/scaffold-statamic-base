# scaffold-statamic-base

Provides basic scaffolding for a Statamic project based on flat files.

- PHP: `8.4.x`
- Composer: `2.8.x`
- Node: `22.14.x`

## Prerequisits

To copy this repository into a new project, the following packages must be installed on the development system.

```sh
sudo apt install nodejs
```

> [!TIP]
> When developing on Windows with WSL2, read how to [setup WSL2 and Docker](https://github.com/doprause/docker-sysbox-wsl2)

## Usage

### Create project folder with scaffolding

The following command clones this repository to a sub-folder `mysite`.

```sh
degit doprause/scaffold-statamic-base mysite
```

Open the project in VS Code by navigating to the sub-folder and running `code .`:

```sh
cd mysite
code .
```

To start the devcontainer from VS Code open command palette with `Ctrl+Shit+P` and search for `Dev Containers: Rebuild Container Without Cache`.

The working directory in the devcontainer is `/workspace`. So within the devcontainer, if yo open a terminal, you find yourself in the `/workspace` directory.

### Create Statamic project

> [!TIP]
> The following commands must be executed from in the `/workspace` directory from within the devcontainer.

#### Create a Statamic project with:

```sh
statamic new mysite
```

This creates a new Statamic project within a sub-folder called `mysite`. Since we want to have the Statamic files directly in the workspace directory, we move them and delete the sub-folder `mysite` afterwards.

```sh
cp -r mysite/. . && rm -rf mysite
```

#### Installing Laravel Sail

To install Laravel Sail run the following commands:

```sh
composer require laravel/sail --dev
php artisan sail:install --with=none
```

Starting Laravel Sail in detached (`-d`) mode:

```sh
sail up -d
```

Stopping Laravel Sail:

```sh
sail stop
```
