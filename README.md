# Глубокое обучение — ДЗ 1

Основное решение — `hw1.ipynb`, сохранённый со всеми выводами и графиками. `hw1_executed.ipynb` содержит ту же выполненную версию. Выполнены обязательные разделы 1–4, 5.1 и 6; выбрана ветка 5.2 (`targeted`). Бонусы отключены.

## Запуск

```bash
python -m pip install -r requirements.txt
```

Откройте `hw1.ipynb` в Jupyter, VS Code или Colab и выберите окружение с установленными зависимостями. Для повторного полного запуска используйте Restart & Run All при `FAST_MODE = False`. При первом запуске нужен интернет: данные сохраняются в `data/`, метрики и три файла весов — в `artifacts/`.

## Результаты запуска

- Python 3.12.0, PyTorch 2.11.0; обучение на Apple MPS.
- CIFAR-10: test accuracy 0.8349 после 20 эпох.
- FashionMNIST, первые 1000 test-объектов: clean accuracy 0.904 у обычной модели и 0.842 у PGD-AT.
- PGD-20 при ε = 0.1: accuracy 0.001 и 0.725 соответственно.

Сохранённые веса дополнительно загружены на CPU: clean accuracy совпала с `artifacts/metrics.json`. Объяснения в ноутбуке основаны на этом запуске. Sanity checks не являются сертификатом устойчивости.

Данные загружаются в Parquet из публичных зеркал: [CIFAR-10](https://huggingface.co/datasets/uoft-cs/cifar10) и [FashionMNIST](https://huggingface.co/datasets/anonyme449/fashion_mnist). Для FashionMNIST отдельно проверено совпадение всех изображений, меток и порядка строк с официальными файлами и контрольными суммами torchvision.
