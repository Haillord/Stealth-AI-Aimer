<p align="center">
  <img src="icon.png" alt="FinCat Banner" style="max-width: 100%; width: auto; height: auto;">
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/Haillord/aim?style=for-the-badge&color=red" alt="license">
  <img src="https://img.shields.io/github/stars/Haillord/aim?style=for-the-badge&color=red" alt="stars">
  <img src="https://img.shields.io/github/last-commit/Haillord/aim?style=for-the-badge&color=red" alt="last commit">
</p>

<h1 align="center">Stealth AI Aimer</h1>

<p align="center">
  <b>Hardware Mouse Aiming System 2026 Edition</b><br>
  Аппаратный аим-ассистент нового поколения на базе YOLOv11 TensorRT и Arduino.
</p>

> **⚠️ Внимание:** Данный репозиторий создан в образовательных целях. Название и контент являются частью авторского стиля.

---

### 🧠 Как это работает

Система построена на принципе разделения вычислений и действий, что делает её невидимой для софтверных античитов:

1. **Захват экрана** — библиотека `dxcam` вырезает центральную область (FOV) с минимальной задержкой.
2. **Детекция целей** — YOLOv11 (TensorRT) на тензорных ядрах **RTX 5070** определяет противников менее чем за 1 мс.
3. **Адаптивный хитбокс** — точка прицеливания динамически смещается в зависимости от размера цели.
4. **Имитация человеческого поведения**:
   - Случайная задержка реакции (50–250 мс).
   - Плавное сглаживание с джиттером.
   - Вероятность намеренного промаха.
5. **Аппаратное движение мыши** — координаты отправляются по Serial на **Arduino Leonardo**, которая эмулирует USB-мышь.

---

### 🖥️ Необходимое оборудование

| Компонент | Рекомендации |
| :--- | :--- |
| **Arduino** | [Leonardo / Pro Micro (ATmega32U4)](https://www.arduino.cc/en/Main/ArduinoBoardLeonardo) — наличие USB-HID. |
| **Видеокарта** | **NVIDIA RTX 5070** / 40 / 30 series (для TensorRT). |
| **Процессор** | [Ryzen 5 5600](https://www.amd.com/en/products/cpu/amd-ryzen-5-5600) или выше. |

---

### 📦 Готовый исполняемый файл (Release)

Если вы не хотите возиться с Python, скачайте стабильную версию:

🚀 **[Скачать StealthAimer v1.0 Stable](https://github.com/Haillord/ahahha-otsosal/releases/tag/1.0)**

**Порядок запуска:**
1. Подключите Arduino к ПК.
2. Запустите `StealthAimer.exe`.
3. Вкладка **Прошивка** → выберите COM-порт → **Прошить**.
4. Нажмите **F1** для активации в игре.

---

### 🔧 Сборка из исходников

#### 1. Установите зависимости:
```bash
pip install pyserial ultralytics dxcam numpy
```

#### 2. Подготовка модели (.engine)
Для максимального FPS на RTX 5070 выполните экспорт:
```python
from ultralytics import YOLO
model = YOLO("yolov11m.pt")
model.export(format="engine", half=True, imgsz=640)
```

#### 3. Сборка в .exe:
```bash
pyinstaller --onefile --windowed --add-data "resources;resources" --name "StealthAimer" main.py
```

---

### 🔌 Прошивка Arduino

В папке resources находится готовый файл firmware.hex. Скрипт flasher.py автоматически загрузит его через avrdude.
После прошивки светодиод на плате мигнёт три раза.

---

### 🎛️ Настройка параметров

| Параметр | Описание | Рекомендация |
|---|---|---|
| Confidence | Уверенность детекции | 0.45 – 0.55 |
| FOV (px) | Область захвата | 300 – 500 px |
| Smooth | Плавность доводки | 0.2 – 0.4 |
| Miss chance | Шанс промаха | 0.05 – 0.1 |

---

### 🔧 Устранение неполадок

✅ Arduino не двигает мышь: Проверьте COM-порт в настройках и убедитесь, что выбрана плата Leonardo.
✅ ModuleNotFoundError: Убедитесь, что установлена библиотека pyserial, а не serial.
✅ Low FPS: Проверьте, что модель сконвертирована в .engine под вашу конкретную видеокарту.

---

### 📄 Лицензия

Проект распространяется под лицензией MIT. Автор не несет ответственности за блокировки аккаунтов. Используйте на свой страх и риск.

---

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-Python-3776AB?style=for-the-badge&logo=python" alt="python">
  <img src="https://img.shields.io/badge/Powered%20by-NVIDIA%20TensorRT-76B900?style=for-the-badge&logo=nvidia" alt="tensorrt">
  <img src="https://img.shields.io/badge/Developer-Haillord-red?style=for-the-badge&logo=telegram" alt="author">
</p>