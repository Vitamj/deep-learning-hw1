# Deep Learning — HW1

The assignment solution is in `hw1.ipynb`. It implements the required convolution, normalization, optimizer, CIFAR-10 ResNet, targeted attack, and Fashion-MNIST adversarial-training tasks. The selected option is `ATTACK_TRACK = 'targeted'`; optional bonus tasks are disabled.

## Run

```bash
python -m pip install -r requirements.txt
jupyter notebook hw1.ipynb
```

Keep `FAST_MODE = False` for the full run. On the first run, the notebook downloads CIFAR-10 and Fashion-MNIST Parquet files into `data/`; it writes metrics and model state dictionaries to `artifacts/` at the end. The tests and experiments run on CPU if CUDA or Apple MPS is unavailable.

The image datasets are standard CIFAR-10 and Fashion-MNIST splits, served in Parquet format from public Hugging Face dataset repositories: [CIFAR-10](https://huggingface.co/datasets/uoft-cs/cifar10) and [Fashion-MNIST](https://huggingface.co/datasets/anonyme449/fashion_mnist).
