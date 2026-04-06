<p align="center">
  <img src="icon.png" width="20%" alt="Stealth AI Aimer">
</p>

<p align="center">
<img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=22&pause=2000&color=FF2244&center=true&vCenter=true&width=700&height=45&duration=40&lines=Stealth+AI+Aimer+%F0%9F%8E%AF;YOLOv11+TensorRT+%E2%80%A2+Arduino+HID;Hardware+mouse+%E2%80%A2+undetectable;RTX+5070+%E2%80%A2+sub+1ms+detection">
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/Haillord/Stealth-AI-Aimer?style=for-the-badge&label=LICENSE&color=FF2244&labelColor=1a1a1a" alt="license">
  <img src="https://img.shields.io/github/stars/Haillord/Stealth-AI-Aimer?style=for-the-badge&label=STARS&color=FF2244&labelColor=1a1a1a" alt="stars">
  <img src="https://img.shields.io/github/last-commit/Haillord/Stealth-AI-Aimer?style=for-the-badge&label=LAST+COMMIT&color=FF2244&labelColor=1a1a1a" alt="last commit">
</p>

<div align="center">

[![](https://img.shields.io/badge/🚀_Скачать_v1.0_Stable-FF2244?style=for-the-badge&logoColor=white)](https://github.com/Haillord/ahahha-otsosal/releases/tag/1.0)

</div>

---

<table>
<tr>
<td width="50%" valign="top">
<img src="https://img.shields.io/badge/🎯_YOLOv11_TensorRT-FF2244?style=flat-square&logoColor=white"/>

Детекция целей менее чем за 1 мс на тензорных ядрах RTX
</td>
<td width="50%" valign="top">
<img src="https://img.shields.io/badge/🖱️_Arduino_HID-1a1a1a?style=flat-square&logoColor=white"/>

Аппаратная эмуляция USB-мыши — невидима для античитов
</td>
</tr>
<tr>
<td valign="top">
<img src="https://img.shields.io/badge/🧠_Адаптивный_хитбокс-7D0000?style=flat-square&logoColor=white"/>

Динамическое смещение точки прицеливания по размеру цели
</td>
<td valign="top">
<img src="https://img.shields.io/badge/👤_Human_Behavior-FF2244?style=flat-square&logoColor=white"/>

Случайная задержка, джиттер и шанс намеренного промаха
</td>
</tr>
</table>

---

### 🛠 Стек

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/YOLOv11-FF2244?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/TensorRT-76B900?style=for-the-badge&logo=nvidia&logoColor=white"/>
  <img src="https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white"/>
  <img src="https://img.shields.io/badge/dxcam-1a1a1a?style=for-the-badge&logoColor=white"/>
</p>

---

### 🖥️ Оборудование

<table>
<tr>
<th>Компонент</th>
<th>Рекомендации</th>
</tr>
<tr>
<td><code>Arduino</code></td>
<td>🔌 Leonardo / Pro Micro (ATmega32U4) — USB-HID</td>
</tr>
<tr>
<td><code>Видеокарта</code></td>
<td>🎮 NVIDIA RTX 5070 / 40 / 30 series (TensorRT)</td>
</tr>
<tr>
<td><code>Процессор</code></td>
<td>⚡ Ryzen 5 5600 или выше</td>
</tr>
</table>

---

### 🔧 Установка
```bash
# Установить зависимости
pip install pyserial ultralytics dxcam numpy

# Экспорт модели для TensorRT
python -c "from ultralytics import YOLO; YOLO('yolov11m.pt').export(format='engine', half=True, imgsz=640)"

# Сборка в .exe
pyinstaller --onefile --windowed --add-data "resources;resources" --name "StealthAimer" main.py
```

---

### 🎛️ Настройка

<table>
<tr>
<th>Параметр</th>
<th>Описание</th>
<th>Рекомендация</th>
</tr>
<tr>
<td><code>Confidence</code></td>
<td>🎯 Уверенность детекции</td>
<td>0.45 – 0.55</td>
</tr>
<tr>
<td><code>FOV</code></td>
<td>📐 Область захвата</td>
<td>300 – 500 px</td>
</tr>
<tr>
<td><code>Smooth</code></td>
<td>🖱️ Плавность доводки</td>
<td>0.2 – 0.4</td>
</tr>
<tr>
<td><code>Miss chance</code></td>
<td>🎲 Шанс промаха</td>
<td>0.05 – 0.1</td>
</tr>
</table>

---

### 🔌 Прошивка Arduino

<details>
<summary><b>Показать инструкцию</b></summary>
<br>
<pre>
1. Подключите Arduino к ПК
2. Запустите StealthAimer.exe
3. Вкладка "Прошивка" → выберите COM-порт → "Прошить"
4. Светодиод мигнёт три раза — готово
5. Нажмите F1 для активации в игре
</pre>
</details>

---

### ❓ Устранение неполадок

<details>
<summary><b>Показать решения</b></summary>
<br>
<pre>
Arduino не двигает мышь  → проверьте COM-порт, выберите плату Leonardo
ModuleNotFoundError      → установите pyserial, не serial
Low FPS                  → конвертируйте модель в .engine под вашу видеокарту
</pre>
</details>

---

> ⚠️ Репозиторий создан в образовательных целях. Автор не несёт ответственности за блокировки аккаунтов.

---

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-Python-3776AB?style=for-the-badge&logo=python" alt="python">
  <img src="https://img.shields.io/badge/Powered%20by-NVIDIA%20TensorRT-76B900?style=for-the-badge&logo=nvidia" alt="tensorrt">
  <img src="https://img.shields.io/badge/Developer-Haillord-FF2244?style=for-the-badge&logo=telegram" alt="author">
</p>