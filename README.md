# Periodic Table Database

## 📌 Описание проекта

Этот проект — часть обучения SQL и Bash на freeCodeCamp. База данных `periodic_table` содержит информацию о химических элементах, а скрипт `element.sh` позволяет находить элемент по атомному номеру, символу или названию.

## 🗄️ Структура базы данных

### Таблица `elements`
| Колонка | Тип | Ограничения |
|:---|:---|:---|
| atomic_number | INT | PRIMARY KEY |
| symbol | VARCHAR(2) | NOT NULL, UNIQUE |
| name | VARCHAR(40) | NOT NULL, UNIQUE |

### Таблица `properties`
| Колонка | Тип | Ограничения |
|:---|:---|:---|
| atomic_number | INT | PRIMARY KEY, FOREIGN KEY (elements) |
| atomic_mass | DECIMAL | NOT NULL |
| melting_point_celsius | NUMERIC | NOT NULL |
| boiling_point_celsius | NUMERIC | NOT NULL |
| type_id | INT | NOT NULL, FOREIGN KEY (types) |

### Таблица `types`
| Колонка | Тип | Ограничения |
|:---|:---|:---|
| type_id | INT | PRIMARY KEY |
| type | VARCHAR(30) | NOT NULL |

## 📁 Файлы проекта

| Файл | Описание |
|:---|:---|
| `element.sh` | Bash-скрипт для поиска элементов |
| `periodic_table.sql` | Дамп базы данных |
| `atomic_mass.txt` | Справочные значения атомных масс |

## 🚀 Использование

### 1. Восстановить базу данных

psql -U freecodecamp postgres < periodic_table.sql



###2. Запустить скрипт
bash
./element.sh
###3. Поиск элемента
bash
./element.sh 1        # по атомному номеру
./element.sh H        # по символу
./element.sh Hydrogen # по названию
###Пример вывода:
text
The element with atomic number 1 is Hydrogen (H). It's a nonmetal, with a mass of 1.008 amu. Hydrogen has a melting point of -259.1 celsius and a boiling point of -252.9 celsius.

###🛠️ Технологии
PostgreSQL — база данных

Bash — скриптовый язык

Git — контроль версий

###📄 Лицензия
Проект создан в образовательных целях в рамках freeCodeCamp.
