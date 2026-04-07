# Celeritas

Celeritas is a web framework for Go.

** Under Development **


## Requirements

- Go 1.21.3
- dbmate
- docker


## How to Run/Test

### spin up necessary stacks

- run `docker compose up -d`

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

### Create new framework

1. copy original `cp -rv celeritas celeritas-ext`
2. ignore the new framework forlder in .gitignore
3. add submodule

## How to Update Celeritas Repo

### Commit changes

```sh
# 1. First, save your uncommitted changes to stash
git stash

# 2. Checkout the main branch
git checkout main

# 3. Pull the latest changes (optional, if you want to update)
git pull origin main

# 4. Reapply your stashed changes
git stash pop

# 5. Now commit your changes
git add .
git commit -m "Your commit message"
```

### Create and Push a new tag

```sh
# 1. Make sure you're on the right commit (main branch with your changes)
git checkout main

# 2. Create an annotated tag (recommended)
git tag -a v0.0.6 -m "Release v0.0.6: describe your changes here"

# 3. Push the tag to remote
git push origin v0.0.6

# Or push all tags at once
git push origin --tags

# 4. verify
git tag -l
git show v0.0.6
```

### Update parent module

```sh
# 1. Make sure celeritas submodule is at v0.0.6
cd /path/to/go-laravel/celeritas
git checkout v0.0.6

# 2. Go to parent repo
cd /path/to/go-laravel

# 3. Add the submodule change
git add celeritas

# 4. Commit the update
git commit -m "Update celeritas submodule to v0.0.6"

# 5. Verify the change
git submodule status
```
