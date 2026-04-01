# NVIDIA-P104-100-Gaming-Guide
The ultimate guide to using mining GPUs (P104-100) for gaming on legacy platforms like LGA 1155.
### 🌐 Select Language / Выберите язык:
* [🇺🇸 English Version](#english-version)
* [🇷🇺 Русская версия (Russian)](#russian-version)

---

<a name="english-version"></a>
# 🛠 ULTIMATE GUIDE: REVIVING NVIDIA P104-100 FOR GAMING

> **IMPORTANT:** This manual is specifically designed for the **NVIDIA P104-100** (a direct equivalent of the **GTX 1070 8GB**) running via Intel Integrated Graphics. These methods may work for other mining cards as well. See the **"📚 FACT SHEET"** section at the end for details.

**FROM THE AUTHORS:** Information gathered and field-tested by **EasySkeld** (on an **Intel Core i5-3570 + NVIDIA P104-100 8GB** setup). Technical support, structuring, and enhancements by **Gemini 3 Flash**.

---

## 📑 TABLE OF CONTENTS
* [⚠️ WARNING PAGE](#1-warning-page)
* [⚡ MAIN TIP: FIXING STUTTERS & FREEZES](#2-main-tip-fixing-stutters)
* [📦 STEP 1: PREPARATION](#3-step-1-preparation-software-pack)
* [🚀 STEP 2: INSTALLATION](#4-step-2-installation-step-by-step)
* [⚙️ STEP 3: GRAPHICS SETTINGS](#step-3-graphics-settings-windows-1011)
* [🆘 TROUBLESHOOTING (5 FULL METHODS)](#5-troubleshooting-5-full-methods)
* [🛠 STEP 5: MAINTENANCE & SOFTWARE](#step-5-maintenance--software-first-aid)
* [📚 FACT SHEET](#6-fact-sheet-technical-intel)

---

## ⚠️ 1. WARNING PAGE
* **IGPU Driver on Legacy Sockets:** If installing Win 11 on LGA 1155 (like the author), the standard driver might fail. **Solution:** Download the **Windows 8.1 driver** from your motherboard manufacturer’s site (e.g., **GA-H77-DS3H**). It works perfectly on Win 11.
* **Socket Myths:** Don't believe those who say you need 1150+ only. **LGA 1155** and even **775** — everything works! Verified by the author on an **i5-3570**.
* **Fake BIOSes:** Never flash a BIOS claiming to "unlock HDMI ports" or "PCIe lanes." It is physically impossible and will brick your card.
* **Call to Action:** Go to **GPU-Z** and upload your BIOS to the database (**Submit BIOS**) to help others recover their cards via programmer!
* **Platform:** Tested on **Intel**. AMD users — proceed at your own risk.

---

## ⚡ 2. MAIN TIP: FIXING STUTTERS
If your gameplay is "choppy" or stuttering — stop choking the Integrated Graphics! It struggles to output the data stream.

1. Enter your **BIOS**.
2. Find **DVMT Pre-Allocated** or **Internal Graphics Memory**.
3. Set it to the **MAXIMUM memory** (**Max** or **512MB/1024MB**).

> **Note:** If you get a black screen after this, lower the value slightly until you find the stable limit.

---

## 📦 3. STEP 1: PREPARATION (SOFTWARE PACK)
* **DDU (Display Driver Uninstaller):** For a clean system wipe.
* **NVIDIA GTX 1070 Driver:** Clean official installer.
* **NVIDIA Patch:** Special files/scripts to enable the mining card as a GPU.

**Important:** Driver and Patch versions must be **strictly identical**!

---

## 🚀 4. STEP 2: INSTALLATION (STEP-BY-STEP)
1. **Isolation:** Disconnect the Internet so Windows doesn't download junk drivers.
2. **Merge:** Unpack the driver installer, drop the patch files into the root folder, and replace all files.
3. **Clean:** Enter **Safe Mode**, run **DDU**. Wipe both NVIDIA and Intel drivers.
4. **Install:** In normal mode, run the patched **setup.exe** as Administrator.

**Important:** Choose **"Graphics Driver Only."** Do **NOT** install NVIDIA APP or GeForce Experience, or the patch might break!

---

## 🆘 5. TROUBLESHOOTING (5 FULL METHODS)

### **Method #1: Tricking the System via Registry (EasySkeld Method)**
This is a hard command override: the system sees Intel, but executes via NVIDIA.
1. Press `Win + R`, type `regedit`. Path: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\Class\`
2. **Finding the folder:** Open `0000`, `0001`, etc. Look at **DriverDesc**. If it says **"NVIDIA..."** — that's your card. If it says **"Intel..."** — that's your iGPU.
3. From the **NVIDIA** folder, copy the values of `OpenGLDriverName` and `OpenGLDriverNameWoW`.
4. Go to the **Intel** folder and replace its original values with the NVIDIA data. **Reboot.**

### **Method #2: Windows 11 LTSC**
The ideal OS for these cards thanks to the updated graphics scheduler. Enable **HAGS** in settings.

### **Method #3: Rolling back to Windows 8.1 / 7 (Classic)**
If modern OS versions hard-block the card at the level of the kernel. Older systems give the driver more control over the output.

### **Method #4: Forcefully Disabling Intel HD**
In Device Manager, disable **Intel HD Graphics**. The UI might lag, but the system will be forced to run everything via P104-100.

### **Method #5: Fixing Crashes (Stability)**
1. Go to **Settings -> System -> Display -> Graphics**.
2. Click **"Change default graphics settings"**.
3. **TURN OFF** the toggle for **"Hardware-accelerated GPU scheduling" (HAGS)**.
4. **TURN OFF** the toggle for **"Optimizations for windowed games"**.

**REBOOT REQUIRED.** This often removes patch-to-system conflicts.

---

## 📚 6. FACT SHEET: TECHNICAL INTEL

### **Full List of Mining GPUs (NVIDIA):**
* **P106-090:** Equivalent to **GTX 1050**. Usually 3GB or 6GB.
* **P106-100:** Equivalent to **GTX 1060 6GB**. The most common card.
* **P104-100:** Equivalent to **GTX 1070 8GB**. Uses fast GDDR5X memory. **The best value.**
* **P102-100:** Equivalent to **GTX 1080 Ti**. Usually 5GB or 11GB. High power & heat.
* **CMP 30HX:** Equivalent to **GTX 1660 Super**. Turing gen, runs cool.
* **CMP 40HX:** Equivalent to **RTX 2060 Super / RTX 2070**. Great for 1080p.
* **CMP 50HX:** Equivalent to **RTX 2080 Ti**. Very high performance.
* **CMP 70HX / 90HX:** Equivalent to **RTX 3080**. Requires a beefy PSU.

### **🕵️ BRAND RATINGS (RUMORS & FEEDBACK):**
* **ASUS (Mining/Turbo):** Rumored to be the most durable and long-lasting.
* **EVGA:** Legendary build quality, but rare to find.
* **Gigabyte:** Good cooling, but watch out for "leaky" thermal pads (needs maintenance).
* **MSI:** Mid-tier, fans often need replacement after long mining sessions.
* **Chinese Brands:** Cheap and noisy; only work well in high-airflow cases.

---

<a name="russian-version"></a>

# 🇷🇺 УЛЬТИМАТИВНОЕ РУКОВОДСТВО: ОЖИВЛЕНИЕ NVIDIA P104-100

> **ВАЖНО:** Данная инструкция написана специально для **NVIDIA P104-100** (аналог **GTX 1070 8GB**), работающей через встройку Intel. Методы могут подойти и для других майнинг-карт. Подробности — в разделе **«📚 СТРАНИЦА ФАКТОВ»**.

---

**ОТ АВТОРОВ:** Информация раздобыта и проверена на практике пользователем **EasySkeld** (связка **i5-3570 + P104-100 8GB**). Техническая поддержка, структурирование и дополнение — **Gemini 3 Flash**.

---

## 📑 СОДЕРЖАНИЕ
* [⚠️ СТРАНИЦА ПРЕДУПРЕЖДЕНИЙ](#1-страница-предупреждений)
* [⚡ ГЛАВНЫЙ СОВЕТ: УСТРАНЕНИЕ ФРИЗОВ](#2-главный-совет-устранение-фризов)
* [📦 ЭТАП 1: ПОДГОТОВКА](#3-этап-1-подготовка-software-pack-1)
* [🚀 ЭТАП 2: УСТАНОВКА](#4-этап-2-установка-пошагово)
* [⚙️ ЭТАП 3: НАСТРОЙКА ГРАФИКИ](#этап-3-настройка-графики-windows-1011)
* [🆘 ЧАСТЫЕ ПРОБЛЕМЫ (5 СПОСОБОВ)](#5-частые-проблемы-5-полных-способов-решения-1)
* [🛠 ЭТАП 5: ОБСЛУЖИВАНИЕ](#этап-5-обслуживание-и-софт-первая-помощь)
* [📚 СТРАНИЦА ФАКТОВ](#6-страница-фактов-технический-ликбез-1)

---

## ⚠️ 1. СТРАНИЦА ПРЕДУПРЕЖДЕНИЙ
* **Драйвер встройки:** На старых сокетах (1155 и т.д.) в Win 11 ставьте драйвер от **Windows 8.1** с сайта материнки (напр. **H77-DS3H**). Он работает стабильнее всех.
* **Миф о сокетах:** **LGA 1155** и **775** — всё работает! Проверено автором на **i5-3570**.
* **Биосы:** Не шлейте биосы для «разблокировки HDMI». Это физически невозможно и окирпичит карту.
* **Призыв к действию:** Зайдите в **GPU-Z** и выложите свой BIOS в базу данных (**Submit BIOS**), чтобы помочь другим в восстановлении.

---

## ⚡ 2. ГЛАВНЫЙ СОВЕТ: УСТРАНЕНИЕ ФРИЗОВ
В BIOS найдите **DVMT Pre-Allocated** или **Internal Graphics Memory**.

1. Выдайте встройке **МАКСИМУМ памяти** (**Max** или **512MB/1024MB**).
2. Если система не грузится — чуть снизьте значение до стабильного предела.

---

## 📦 3. ЭТАП 1: ПОДГОТОВКА (SOFTWARE PACK)
* **DDU (Display Driver Uninstaller):** Для полной очистки системы.
* **Драйвер NVIDIA GTX 1070:** Чистый официальный установщик.
* **Патч NVIDIA:** Специальные файлы для активации майнинг-карты.

**Важно:** Версии драйвера и патча должны быть **строго одинаковыми**!

---

## 🚀 4. ЭТАП 2: УСТАНОВКА (ПОШАГОВО)
1. **Изоляция:** Отключите интернет.
2. **Слияние:** Распакуйте драйвер, закиньте в него файлы патча с заменой всех файлов.
3. **Чистка:** Перейдите в **Безопасный режим**, запустите **DDU**. Удалите драйверы NVIDIA и Intel.
4. **Инсталляция:** Запустите патченный **setup.exe** от имени администратора.

**Важно:** Не устанавливайте NVIDIA APP или GeForce Experience, иначе патч может слететь!

---

## 🆘 5. ЧАСТЫЕ ПРОБЛЕМЫ (5 ПОЛНЫХ СПОСОБОВ РЕШЕНИЯ)

### **Способ №1: Обман системы через реестр (Метод EasySkeld)**
Это жесткая подмена команд: система видит Intel, но выполняет NVIDIA.
1. Нажми `Win + R`, введи `regedit`. Путь: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\Class\`
2. **Поиск папки:** Открывай `0000`, `0001` и т.д. Смотри **DriverDesc**. Если **«NVIDIA»** — это карта, если **«Intel»** — встройка.
3. Из папки **NVIDIA** скопируй `OpenGLDriverName` и `OpenGLDriverNameWoW`.
4. В папке **Intel** замени ими родные значения. **Ребут.**

### **Способ №2: Windows 11 LTSC**
Идеальная система для таких карт благодаря свежему планировщику графики. Включите **HAGS** в настройках.

### **Способ №3: Откат на Windows 8.1 / 7 (Классика)**
Если современные ОС наглухо блокируют карту на уровне ядра. В старых системах драйвер имеет больше прав над выводом изображения.

### **Способ №4: Принудительное отключение Intel HD**
В Диспетчере устройств отключи **Intel HD**. Система потеряет аппаратное ускорение интерфейса, но будет вынуждена работать через P104-100.

### **Способ №5: Борьба с вылетами (Стабильность)**
1. В настройках графики нажми **«Изменение стандартных параметров графики»**.
2. **ВЫКЛЮЧИ** тумблер **«Планирование GPU с аппаратным ускорением»**.
3. **ВЫКЛЮЧИ** тумблер **«Оптимизация для игр в оконном режиме»**.

**ОБЯЗАТЕЛЬНО ПЕРЕЗАГРУЗИСЬ.** Часто это убирает конфликты патча с системой.

---

## 📚 6. СТРАНИЦА ФАКТОВ: ТЕХНИЧЕСКИЙ ЛИКБЕЗ

### **Полный список майнинг-видеокарт (NVIDIA):**
* **P106-090:** Аналог **GTX 1050**. Обычно 3GB или 6GB.
* **P106-100:** Аналог **GTX 1060 6GB**. Самая массовая карта.
* **P104-100:** Аналог **GTX 1070 8GB**. Имеет быструю память GDDR5X. **Самый топ.**
* **P102-100:** Аналог **GTX 1080 Ti**. Имеет 5GB или 11GB. Очень мощная и горячая.
* **CMP 30HX:** Аналог **GTX 1660 Super**. Поколение Turing, холодная.
* **CMP 40HX:** Аналог **RTX 2060 Super / RTX 2070**. Хороший вариант для 1080p.
* **CMP 50HX:** Аналог **RTX 2080 Ti**. Очень высокая производительность.
* **CMP 70HX / 90HX:** Аналоги **RTX 3080**. Потребует мощный БП.

### **🕵️ РЕЙТИНГ ФИРМ (СЛУХИ И ОТЗЫВЫ):**
* **ASUS (Mining/Turbo):** Считаются самыми живучими.
* **EVGA:** Легендарное качество, но большая редкость.
* **Gigabyte:** Хорошие, но следи за прокладками (**«текут»**).
* **MSI:** Средне, часто после майнинга нужно менять вентиляторы.
* **Китайские бренды:** Дешево, шумно, но работают в продуваемых корпусах.
