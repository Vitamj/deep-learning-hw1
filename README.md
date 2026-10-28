# Deep Learning — HW1

Решение находится в `hw1_executed.ipynb`: ноутбук выполнен целиком, графики и выводы сохранены. Исходный `hw1.ipynb` оставлен без сохранённых runtime-выводов. Реализованы свёртка и backward, BatchNorm, слияние Conv-BN, MyAdamW, cosine schedule, ResNet для CIFAR-10, атаки и adversarial training для Fashion-MNIST. Выбран вариант `ATTACK_TRACK = 'targeted'`; дополнительные бонусы не включены.

## Запуск

```bash
python -m pip install -r requirements.txt
jupyter notebook hw1.ipynb
```

Оставьте `FAST_MODE = False` для полного прогона. При первом запуске датасеты CIFAR-10 и Fashion-MNIST загружаются в `data/`; метрики и веса сохраняются в `artifacts/`. Нужен доступ в интернет для загрузки датасетов. Полный прогон выполнялся на Apple MPS.

В этом запуске ResNet-20 получил test accuracy 0.8349 после 20 эпох. PGD adversarial training за заданные 5 эпох показал низкую clean accuracy (0.1400) и низкую точность под атакой; это ограничение эксперимента явно разобрано в ноутбуке.

Данные — стандартные разбиения CIFAR-10 и Fashion-MNIST в Parquet: [CIFAR-10](https://huggingface.co/datasets/uoft-cs/cifar10), [Fashion-MNIST](https://huggingface.co/datasets/anonyme449/fashion_mnist).
