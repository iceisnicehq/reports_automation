# Reports Automation 📄
_Программа тестировалась на _Python 3.13.2_ на операционной системе Microsoft Windows 11 Version 24H2_

This project aims to automate the process for creating reports on repetitive lab experiments (provided by [AU_team](https://au-team.ru/))

# **Автоматизация создания лабораторных отчетов с динамическим заполнением шаблонов**
## Features ✨
- **Автоматическое заполнение шаблона**  
  Поддержка плейсхолдеров в документе Word:
  - `%DISCIPLINE%` - Название дисциплины
  - `%NUM%` - Номер отчета
  - `%REPORT_NAME%` - Название отчета
  - `%LAST_NAME%` - Фамилия студента
  - `%FIRST_NAME%` - Имя студента
  - `%PATRON_NAME%` - Отчество студента (если есть)
  - `%GROUP%` - Группа студента
  
- **Умный ввод данных**
  - Выбор из предустановленных дисциплин:
     - Администрирование сетей передачи информации
     - Администрирование операционных систем
     - Безопасность операционных систем
     - Современные операционные системы
     - Разработка корпоративных дистрибутивов
     - Специализированные языки и технологии программирования
   
  - Автоматическая капитализация названия отчета
  - Валидация пустых полей

- **Работа с изображениями**  
  - Последовательная обработка изображений (PNG/JPG/JPEG/GIF)
  - Автоматическая нумерация рисунков
  - Центрирование изображений и подписей
  - Форматирование подписей: "Рис. 1. Описание..."

- **Форматирование документа**  
  - Автоматическое применение стилей:
    - Times New Roman 14pt
    - Межстрочный интервал 1.5
    - Отсутствие переноса между абзацами
  - Сохранение исходного форматирования шаблона

- **Конвертация pdf файла с ТЗ в DOCX для дальнейшей вставки в отчет**
  - Прорграмма предлагает преобразовать pdf файл в docx, при его наличии в рабочей директории.
  
## Установка 📦
1. Клонировать репозиторий:
```bash
https://github.com/iceisnicehq/Reports_Automation
```
Или скачать файлы `automato.py` и `requirements.txt`
2. Установка зависимостей:
```python
pip install -r requirements.txt
```
---
## Использование 🖥️
1. Подготовка директории:
  - Поместите шаблон отчета (.docx или .doc) с плейсхолдерами в директорию.
  - Добавьте изображения для отчета. Изображения будут обработаны в порядке их именования.
2. Запуск системы:
```python
automato.py
```
3. Ввод параметров.
- Ввести метаданные отчета:
   - Фамилия, имя, отчество (если есть)
   - Группа (в формате КХ-22-01)
   - Номер отчета
   - Название отчета
   - Дисциплина (выбор из списка или ручной ввод)
- Указать путь к рабочей директории.
- Выбрать шаблон.
4. Обработка изображений.
- Просмотр изображений в порядке их именования.
- Ввод описаний для каждого рисунка (описание отображается под рисунком в формате "Рис. 1. Описание").
5. Генерация отчета.
  - Запрос название отчета у пользвателя.
  - Система создаст файл "<название>.docx" в указанной в 3 пункте дирректории.
  - Сохранит все исходные файлы без изменений.
---
## Требования шаблона
Пример структуры шаблона doc(x) файла:
```text
[Шапка]

Лабораторная работа №%RE%
По дисциплине: "%DISCIPLINE%"
Тема: "%REPORT_NAME%"
...
Выполнил студент: группы %GROUP% %LAST_NAME% %FIRST_NAME% %PATRON_NAME%
[Футер]
```
---
### Лицензия
Этот проект распространяется под лицензией MIT. Подробности см. в файле [LICENSE](https://github.com/iceisnicehq/Reports_Automation/blob/main/LICENSE).
