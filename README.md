<p align="center">
  <img width="100%" alt="StealthAimer Banner" src="https://i.imgur.com/AzWq9jP.png">
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/Haillord/aim?style=for-the-badge&color=red" alt="license">
  <img src="https://img.shields.io/github/stars/Haillord/aim?style=for-the-badge&color=red" alt="stars">
  <img src="https://img.shields.io/github/last-commit/Haillord/aim?style=for-the-badge&color=red" alt="last commit">
</p>

<h1 align="center">Stealth AI Aimer</h1>

<<<<<<< Updated upstream
=======
<p align="center">
  <b>Hardware Mouse Aiming System 2026 Edition</b><br>
  Аппаратный аим-ассистент нового поколения на базе YOLOv11 TensorRT и Arduino.
</p>

>>>>>>> Stashed changes
---

<<<<<<< HEAD
### 🧠 Как это работает
=======
## 📌 Оглавление

- [Как это работает](#-как-это-работает)
- [Готовый исполняемый файл (Release)](#-готовый-исполняемый-файл-release)
- [Инструкция по сборке](#-сборка-и-запуск)
---

## 🧠 Как это работает
>>>>>>> c6bb35567ba75a1c4712fb45371d13d6d3c460d2

Система построена на принципе разделения вычислений и действий:

1. **Захват экрана** — `dxcam` вырезает FOV с минимальной задержкой.
2. **Детекция целей** — YOLOv11 (TensorRT) на **RTX 5070** определяет цели < 1 мс.
3. **Адаптивный хитбокс** — динамическое смещение точки прицеливания.
4. **Hardware Mouse** — координаты уходят на **Arduino Leonardo**, которая эмулирует USB-мышь.

---

### 🖥️ Необходимое оборудование

| Компонент | Рекомендации |
| :--- | :--- |
| **Arduino** | Leonardo / Pro Micro (ATmega32U4) |
| **Видеокарта** | RTX 5070 / 40 / 30 series |
| **Процессор** | Ryzen 5 5600 или выше |

---

<<<<<<< Updated upstream
## 🔧 Сборка и запуск
=======
<<<<<<< HEAD
### 📦 Готовый исполняемый файл (Release)
=======
## 🔧 Сборка и запуск
>>>>>>> c6bb35567ba75a1c4712fb45371d13d6d3c460d2
>>>>>>> Stashed changes

> **Сами разберетесь как собрать нахуй блять**

---


## 📦 Готовый исполняемый файл (Release)

🚀 **[Скачать StealthAimer v1.0 Stable](https://github.com/Haillord/ahahha-otsosal/releases/tag/1.0)**

**Порядок запуска:**

1. Подключите Arduino к ПК.
2. Запустите `StealthAimer.exe`.
3. Вкладка **Прошивка** → выберите COM-порт → **Прошить**.
4. Нажмите **F1** для активации в игре.
<<<<<<< Updated upstream
=======
<<<<<<< HEAD

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
=======
>>>>>>> c6bb35567ba75a1c4712fb45371d13d6d3c460d2
>>>>>>> Stashed changes
