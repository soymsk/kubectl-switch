# kubectl-switch
Quickly kubectl context switcher. 
Just a bash snippet.


# Requirements
Install [peco](https://github.com/peco/peco)

# Just add this code into your bash_profile
```shell
function kubectl-switch() {
	kubectl config use-context $(kubectl config get-contexts  | peco --initial-index=1 --prompt='kubectl config use-context > ' |  sed -e 's/^\*//' | awk '{print $1}')
}
```
