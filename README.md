### `gcloud` and `kubectl` in a container

I had difficulty with installation and running of `gcloud` on my work computer being insanely slow (commands taking minutes, updating taking upwards of an hour). Google publishes a docker image with these commands already installed, and running it is faster for me. After cloning this repository somewhere, add the following to your `bash` or `zsh` profile.

```bash
gcloud() {
    CMD="cd /path/to/cloned/repo && docker-compose run gcloud gcloud $@"
    bash -c $CMD
}

kubectl() {
    CMD="cd /path/to/cloned/repo && docker-compose run gcloud kubectl $@"
    bash -c $CMD
}
```
