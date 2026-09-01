<div align="center">
  <h1>A E G I S</h1>
  
  <p><b>Многофункциональный клиент для маршрутизации трафика и обхода DPI</b></p>

  ![Status](https://img.shields.io/badge/status-active-success)
  ![Type](https://img.shields.io/badge/type-desktop%20app-blue)
  ![License](https://img.shields.io/badge/code-open%20source-lightgrey)

</div>

---

## О проекте

**Aegis** - это десктопное приложение, объединяющее под одним капотом мощные инструменты для обхода сетевых ограничений и управления прокси-соединениями. Проект предоставляет удобный графический интерфейс для управления `xray-core`, `zapret` и `tg ws proxy`, избавляя от необходимости сложной ручной настройки через консоль.

## Стек технологий

![C++](https://img.shields.io/badge/C++-00599C?logo=c%2B%2B&logoColor=white)
![Qt](https://img.shields.io/badge/Qt-41CD52?logo=qt&logoColor=white)
![QML](https://img.shields.io/badge/QML-41CD52?logo=qt&logoColor=white)
![Xray-core](https://img.shields.io/badge/Xray--core-000000?logo=linux&logoColor=white)
![Zapret](https://img.shields.io/badge/Zapret-FF4B4B?logo=linux&logoColor=white)

## Что реализовано

- 🚀 **Интеграция Xray-core:** Прямая поддержка конфигураций `vless` (и аналогичных) прямо "из коробки".
- 🛡️ **Поддержка Zapret:** Интегрирован функционал обхода от *flowseal* с поддержкой выбора стратегий (например, `general.bat`).
- 🔄 **Парсинг обновлений:** Умная система, которая парсит страницу *flowseal* для автоматического получения актуальных стратегий обхода.
- ✈️ **TG WS Proxy:** Встроенный модуль для запуска WebSocket прокси для Telegram в один клик с возможностью настройки хоста, порта и Fake-TLS секрета.
- 🎨 **UI/UX на QML:** Кастомный темный интерфейс (Dark Mode) с плавными переходами и современным дизайном.
- ⚙️ **Системные функции:** Сворачивание в системный трей, автозапуск при старте системы, мультиязычность (RU/EN) и встроенный терминал для чтения логов в реальном времени.

## Архитектура и техническая реализация

### 🖥️ Frontend (Интерфейс)
- Визуальная часть полностью реализована на **QML**, что обеспечивает аппаратное ускорение, высокую плавность интерфейса и гибкость в разработке UI-компонентов.
- Архитектура приложения разделена на логические модули-вкладки: ZAPRET, XRAY, TG PROXY, Настройки.

### ⚙️ Backend (C++)
- На уровне C++ реализовано управление процессами (spawn) - приложение "поднимает" бинарники `xray-core` и `zapret` как дочерние процессы, полностью контролируя их жизненный цикл.
- Перехват стандартных потоков вывода (stdout/stderr) дочерних процессов для вывода логов прямо в UI интерфейс Aegis.
- Сетевой модуль C++ для HTTP-запросов и парсинга данных (актуальные стратегии и обновления от flowseal).

## Скриншоты

<div align="center">
  <img width="451" height="683" alt="image" src="https://github.com/user-attachments/assets/c3eb2205-d31f-49f3-93c3-66a3e98cb07c" />

  <img width="456" height="683" alt="image" src="https://github.com/user-attachments/assets/72f970d6-327b-4af6-b796-03b185456663" />

</div>

