## Catalyst.DL – cifar10 with stages example

### Local run

```bash
catalyst-dl train --config=./cifar_stages/config.yml
```

### Docker run

For more information about docker image goto `catalyst/docker`.

```bash
export LOGDIR=$(pwd)/logs/cifar_stages
docker run -it --rm --runtime=nvidia \
   -v $(pwd):/src -v $LOGDIR:/logdir/ \
   -e "CUDA_VISIBLE_DEVICES=0" \
   -e "LOGDIR=/logdir" \
   catalyst-image \
   catalyst-dl train --config=./cifar_stages/config.yml --logdir=/logdir
```


### Training visualization

For tensorboard visualization use 

```bash
CUDA_VISIBLE_DEVICE="" tensorboard --logdir=./logs/cifar_stages
```