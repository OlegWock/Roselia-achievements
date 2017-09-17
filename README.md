# Roselia-achievements

![screenshot](https://github.com/OlegWock/Roselia-achievements/raw/master/screenshot.png)

This is small module for RenPy, implenting custom achievements. It is being developed as a part of Project Roselia, that \[will\] contain other small scripts with different features for RenPy.

It has:

* One-time achievements
* Achievements with progress
* Steam compatibility (in future)
* The ability to change the achievement -screen and -animation
* A simple architecture, that allows you to add new features
* Works over standard **achievement**

## How to use

**Attention!!!**
This module uses persistent data, so after any change you must clear persistent data.

To integrate in your project:

* Copy the **achievement.rpy** file in your project folder
* In the **achievement.rpy** file (line 90; after 'Define your achievements here' comment) add your achievements. There are two examples. Achievements use the below structure:

```python
# Define your achievements here
persistent.achievements_dict = {"name": {"type": 0, 
                                         "title": "",
                                         "text": "",
                                         "icon": "images/icons/ach.png"
                                        },
                                "name": {"type": 1,
                                         "title": "",
                                         "text": "",
                                         "icon": "images/icons/ach.png",
                                         "cur_prog": 0,
                                         "max_prog": 33
                                        }
                                }
```

### Explanation:

**name** — identifier, the user will not see this

**type** — 0 or 1, 0 — one-time achievement, 1 — achievement with progress

**title** — notification title
 
**text** — notification description

**icon** — icon path, recommended: 96х96 pixels

**cur_prog** — only used if **type=1**, current progress

**max_prog** — only used if **type=1**, maximal progress

## Usage

To implement, use one of these functions:

**Get_achievement:**

**$ get_achievement(name, trans=achievement_transform)** — to award a one-time achievement

**trans** — animation for the achievement

**Update_achievemnt:**

**$ update_achievement(name, step=1, trans=achievement_transform)** — to update an achievement with progress

**step** — how much should be added, by default =1

**trans** — animation for the achievement

After that you can use basic functionality.

-------------------------------------------------------------------------------

# In russian / на русском

Модуль для RenPy для интеграции достижений. Разрабатывается в рамках проекта Roselia, в котором я пишу небольшие и удобные расширения для RenPy.

* Одноразовые достижения
* Достижения с прогрессом
* Совместимость с Steam (который, для RenPy пока недоступен)
* Возможность задавать свои достижения, свою анимацию
* Архитектура построена таким образом, что легко расширяется для дополнительных функций. Например, комната с достижениями, категории достижений
* Работает на основе встроеного механизма achievement

## Как пользоваться
**ВНИМАНИЕ! УВАГА! АХТУНГ! ВОРНИНГ!**
Достижения используют постоянные данные (persistent), поэтому после каждого изменения не забывайте очищать постоянные данные.

Интегрировать систему можно в три простых шага.

* Для начала вам нужно положить файл **achievemnt.rpy** в свой проект, RenPy подключит его автоматически.
* В самом файле **achievemnt.rpy** в 90ой строке, после комментария "Define your achievements here" стоит добавить нужные вам достижения. Там есть два примера. Достижение должно иметь такую струтуру:

```python
# Define your achievements here
persistent.achievements_dict = {"name": {"type": 0, 
                                         "title": "",
                                         "text": "",
                                         "icon": "images/icons/ach.png"
                                        },
                                "name": {"type": 1,
                                         "title": "",
                                         "text": "",
                                         "icon": "images/icons/ach.png",
                                         "cur_prog": 0,
                                         "max_prog": 33
                                        }
                                }
```

А теперь разложим по полочкам. 

**name** — индентификатор. Я рекомендую использовать короткие имена на английском. Оно используется для индентификации, пользователь его не видит

**type** — 0 или 1, 0 — одноразовое достижение, 1 — с прогрессом

**title** — Заголовок (показывается пользователю в уведомлении)
 
**text** — Описание (показывается пользователю в уведомлении)

**icon** — путь к иконке. Я рекомендую размер 96х96 пикселей

**cur_prog** — только если type=1. Текущий прогресс

**max_prog** — только если type=1. Сколько нужно что бы получить достижение

* В нужном месте сценария вызвать функцию:

**$ get_achievement(name, trans=achievement_transform)** — для достижения одноразовой ачивки

**$ update_achievement(name, step=1, trans=achievement_transform)** — для обновления достижения с прогрессом. **step** — сколько нужно прибавить, по умолчанию =1, **trans** — анимация для ачивки

После этого вы сможете использовать базовый функционал. Для расширения же понадобится знание Python.

