# A Tutorial For Hugo Web Development
Instructions on how to setup the environment for website updates

The guideline is also available [here](https://gohugo.io/installation/linux/).

## Prerequisites

### Installation of Go


1. Download [Go](https://go.dev/doc/install)
2. Go to the directory of the downloaded files and type the following commands in the terminal
```
sudo rm /usr/local/go
sudo tar -C /usr/local -xzf go1.22.5.linux-amd64.tar.gz
```
Note that `go1.22.5.linux-amd64.tar.gz` is the file downloaded.
3. Add /usr/local/go/bin to the PATH environment variable.
4. Verify that you've installed Go by opening a command prompt and typing the following command:
```
go version
```

### Installation of Snap

> https://snapcraft.io/docs/installing-snap-on-ubuntu

```
sudo apt update
sudo apt install snapd
```
Use `Tab` and `Enter` to agree with the protocal to finish the installation.

### Installation of Hugo

To install the extended edition of Hugo:
```
sudo snap install hugo
```

Check if the installation is successful by typing:
```
hugo version
```

## Create Your Own Web

### Find a Theme

1. Go to [here](https://themes.gohugo.io/) for your preferred themes, e.g., the [lightbi](https://themes.gohugo.io/themes/lightbi-hugo/), [walden](https://themes.gohugo.io/themes/hugo-theme-walden/) and [cleanwhite](https://github.com/zhaohuabing/hugo-theme-cleanwhite)
2. Click the download button
3. Follow the installation instructions in `README.md`

For example, to try on the walden theme:
```
mkdir mysite
cd mysite
git init
git branch -m main
mkdir themes
git submodule add git@github.com:Homecat805/hugo-theme-walden.git themes/hugo-theme-walden
cp -rf themes/hugo-theme-walden/exampleSite/* ./
hugo server
```
## Post Your Web on Github

1. Create a host repositoray with a README using the name of YOUR_ACCOUNT_NAME.github.com where YOUR_ACCOUNT_NAME is the name of your github account, e.g., UTAT-ADR. The resulting website link would be like `https://utat-adr.github.io/`.

2. Go to your source repository. Delete the existing `public/` folder and clone your host repository as the `public/` subfolder.
```
rm -rf public/
git clone https://github.com/UTAT-ADR/utat-adr.github.com public
```

3. Rebuild website:
```
hugo
```

4. Remove the README.md file (as otherwise your website will not be shown), add all files in public/ to git, and commit & push:
```
cd public
git rm README.md
git add .
git commit -m 'first commit'
git push
cd ..
```







