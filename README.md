# Celeritas

Celeritas is a web framework for Go.

** Under Development **


## Requirements

- Go 1.21.3
- dbmate
- docker


## How to Run/Test

### celeritas

- clone this repo and its submodules
- from root, run `go run celeritas/cmd/cli/*.go` to see available command
- run `go run celeritas/cmd/cli/*.go new new_project` to create the new_project
- or using make command, `make cel n=new_project`

### boilerplate

- open the project and go to the `celeritas-boilerplate`
- run `cp .env.example .env` and adjust the values
- run `make start`



## Working with git

### Added root project to git

1. di root: git init
2. buat .gitignore:
    - celeritas/
    - celeritas-boilerplate/
3. commit root workspace
4. terima git push ke remote baru (workspace manager)
5. Atau kalau kamu perlu manage celeritas sebagai subproject benar:
    - git submodule add https://github.com/ansufw/celeritas.git celeritas
    - git submodule add https://github.com/ansufw/celeritas-boilerplate.git celeritas-boilerplate


### Clone project

1. run `git clone --recurse-submodules https://github.com/ansufw/go-laravel.git [dir_name]`
2. or run
    - clone repo `git clone https://github.com/ansufw/go-laravel.git [dir_name]`
    - cd to repo and run `git submodule update --init --recursive --remote`