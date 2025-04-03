# scaffold-statamic-base

Provides basic scaffolding for a Statamic project based on flat files.

PHP: `8.4.x`
Composer: `2.8.x`
Node: `22.14.x`

## Prerequisits

To copy this repository into a new project, the following packages must be installed on the development system.

```sh
sudo apt install nodejs
```

## Usage

### Create project folder with scaffolding

The following commands create a new project with the scaffolding.

```sh
degit doprause/scaffold-statamic-base new-project
```

Open the devcontainer:

```sh
cd new-project
code .
```

To open the devcontainer from VS Code open command palette with `Ctrl+Shit+P` and search for `Dev Containers: Rebuild Container Without Cache`.

### Create Statamic project

Create a Statamic project with:

```sh
statamic new .
```
