# Personal website

This repo contains the code for the website hosted at slavo.github.io. 

## Local setup

### WSL2 on windows

Hugo can be installed in WSL though Ubuntu's default package manager. The one thing to watch out for is WSL networking. By default, localhost in WSL can't be accessed directly through a browser running natively on Windows. So `hugo server` would work, but not do anything by default. You can solve this by using `-bind` and specify the IP address of WSL explicitly every time. Or have an automated way to do that each time WSL starts and gets a new IP. See this blog post for example details: https://www.tylerquinlivan.com/posts/hugo_on_wsl/

More info on the networking of WSL: https://learn.microsoft.com/en-us/windows/wsl/networking#accessing-a-wsl-2-distribution-from-your-local-area-network-lan

TIP: another way to find the IP of the VM within WSL is `hostname -I`

### MacOS

On MacOS you can run everything natively. Install hugo through homebrew. Then just clone the repo and run `hugo server` to preview on localhost