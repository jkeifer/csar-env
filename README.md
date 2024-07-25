# CSAR repos and environments

Use this like so:

```commandline
cd ~
git clone git@github.com:jkeifer/csar-env.git csar
cd csar
git submodule update --remote --init --checkout --no-single-branch
git submodule foreach git checkout
```

Adding a new repo is like this (using `./snodas/django-snodas` as an example):

```commandline
git submodule add git@github.com:PSU-CSAR/django-snodas.git ./snodas/django-snodas
git submodule update --remote --init --checkout --no-single-branch ./snodas/django-snodas
(cd ./snodas/django-snodas git checkout)
```

Then edit the `./.gitmodules` file to ensure `update = none` and `ignore = all`.

If it is a repo previously cloned manually then the update and checkout don't
need to be run. Instead, the git directory can be adopted into the parent by
running `git submodule absorbgitdirs snodas/django-snodas`.
