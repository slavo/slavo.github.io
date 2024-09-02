# Personal website

This repo contains the code for the website hosted at www.techliberal.com. 

## Local setup

### WSL2 on windows

* Install homebrew if not installed (within WSL). It has latest versions of hugo, which isn't the case with Ubuntu's default package manager.
* Install hugo if not installed `brew install hugo`
* Clone this repo
* Get the latest version of the theme. Because the hugo theme is in a git submodule, it has to be fetched separately. In the root dir, `git submodule update --init` would get the latest version from the theme repo. If there are more changes to the theme, they can be pulled with `git submodule update --remote --rebase`
* Launch the hugo server `hugo server`

The one thing to watch out for is WSL networking. By default, localhost in WSL can't be accessed directly through a browser running natively on Windows. So `hugo server` would work, but not do anything by default. You can solve this by using `--bind` and specify the IP address of WSL explicitly every time. Or have an automated way to do that each time WSL starts and gets a new IP. See this blog post for example details: https://www.tylerquinlivan.com/posts/hugo_on_wsl/

More info on the networking of WSL: https://learn.microsoft.com/en-us/windows/wsl/networking#accessing-a-wsl-2-distribution-from-your-local-area-network-lan. You may need to do this every time the WSL IP changes.

TIP: another way to find the IP of the VM within WSL is `hostname -I`

### MacOS

On MacOS you can run everything natively. Follow the same steps as in WSL, but you don't need to worry about networking. Just starting the server as normal with `hugo server` would work, and you can use http://localhost:1313 (assuming default port) for development.

### Everywhere

If the repo is cloned for the first time, the theme will also need to be initiated as it's running as a github submodule. It's not cloned automatically by default because of that. The following needs to be run in the main folder:

`git submodule init`

`git submodule update`

## Creating and editing content

A new blog post can be added by creating it with the Hugo CLI.

`hugo new posts/new-title.md`

This would add the file in the posts folder, but also create the metadata at the beginning which Hugo needs (timestamp, whether it's draft etc). Once this is done, open the file and edit the markdown as normal until finished.

If adding a new page, the same command as above can be used (skipping the folder path, so it's in the root content folder), but it also needs to be added to the navigation if needed. This is done separately through the Hugo them config.yaml file. There's a menu section in it which basically contains the top-level navigation - just add the desired page to it.

When adding images to any content, they need to be included through the `![]` syntax. But the URLs will differ from the ones appearing in auto-complete. They all go into the static folder as files, and are referenced from the root when deployed, so (/image-name.png)

Adding links to other posts or pages can be done through Hugo's `rel` syntax. An absolute link would look like `[Now page]({{< ref "/now" >}})`. See here for more info: https://gohugo.io/content-management/cross-references/

## Deployment

### Github Pages



## Upgrading packages and keeping up to date