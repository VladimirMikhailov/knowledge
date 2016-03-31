# Virtualization

  `BOX URL: https://github.com/kraksoft/vagrant-box-ubuntu/releases/download/15.04/ubuntu-15.04-amd64.box`
  Ubuntu Snappy with docker

## Setup simple cluster

  vagrant box add {title} {box url}
  vagrant init {title}
  vagrant up

## Setup ssh if ssh login doesn't work

  ```
    vagrant ssh-config | pbcopy
  ```

  and paste it into `.ssh` config file
