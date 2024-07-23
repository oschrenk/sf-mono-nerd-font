# DEVELOPMENT

**Requirements**

- [Docker](https://www.docker.com/) via `brew install docker`
- [git-lfs](https://git-lfs.com) via `brew install git-lfs`

## Procedure

```
cd Downloads
mkdir sf-mono
cd sf-mono

curl -s -O https://devimages-cdn.apple.com/design/resources/download/SF-Mono.dmg
hdiutil attach SF-Mono.dmg
pkgutil --expand-full "/Volumes/SFMonoFonts/SF Mono Fonts.pkg" ~/Downloads/sf-mono/extracted

docker run --rm -v ~/Downloads/sf-mono/extracted/SFMonoFonts.pkg/Payload/Library/Fonts/:/in -v ~/Downloads/sf-mono/SF-Mono-NerdFont:/out nerdfonts/patcher:4.14.4 --mono --adjust-line-height --complete
```

Then copy all these file to this repository

## Versions

- SF Mono. It can be read in the "Font Book.app" under Details
- Nerd Font Patcher. Versioning scheme is not clear. Version is taken from the output of the last available image tag

## git-lfs

```shell
git lfs install
> Git LFS initialized.

git lfs track "*.otf"
```

## Github

Objects in Git LFS are not included by default in release archives.
To enable it, see [Managing Git LFS objects in archives](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-git-lfs-objects-in-archives-of-your-repository#managing-git-lfs-objects-in-archives)
