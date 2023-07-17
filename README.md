# Personal website

This repo contains the code for the website hosted at slavo.me. 

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