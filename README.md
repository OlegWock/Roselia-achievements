# Roselia-achievements

This is small module for RenPy, thats implent custom achievements. It's devloping as part of Project Roselia, that \[will\] contain other small scripts with different features for RenPy.

It has:

* One-time achievements
* Achievements with progress
* Steam compatibility (in future)
* Ability to change achievements screen and animation
* Simple architecture that allows you to add new features
* Works over standart **achievement**

## How to use

**Attention!!!**
This module uses persistent data, so after any change you must clear persistent data.

For integration in your project:

* Copy **achievement.rpy** file in your project folder
* In **achievement.rpy** file (at 90th line, after 'Define your achievements here' comment) add your achievements. There is two examples. Achievement has same structure as bellow:

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

Threre

**name** — indentifer. User will not see it

**type** — 0 or 1, 0 — one-time achievement, 1 — with progress

**title** — title for notification
 
**text** — description for notification

**icon** — path to icon. I recomend make it 96х96 pixels

**cur_prog** — only if **type=1**. Current progress

**max_prog** — only if **type=1**. Maximal progress

* Call one of this function:

**$ get_achievement(name, trans=achievement_transform)** — to award a one-time achievement

**$ update_achievement(name, step=1, trans=achievement_transform)** — to update achievement with progress

**step** — how much should be added, by default =1

**trans** — animation for achievement

After that you can use basic functionality.

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

