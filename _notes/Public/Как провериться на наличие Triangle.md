---
title : Как провериться на наличие Triangle
feed: show
date : 02-06-2023
---

## Создать резервную копию с помощью iTunes

- следовать инструкциям по ссылке [https://support.apple.com/ru-ru/HT211229](https://support.apple.com/ru-ru/HT211229)

## Установить скрипт проверки

- открыть Terminal
- выполнить последовательно:

```bash
python3 -m venv triangle-check-env
source triangle-check-env/bin/activate
pip install triangle_check
```

## Выполнить проверку

- в Terminal выполнить:

```bash
python -m triangle_check /путь/до/резервной-копии [пароль-если-был-зашифрован]   
```

### Пример подозрительного вывода

```
==== IDENTIFIED TRACES OF COMPROMISE (Operation Triangulation) ====
2022-*-* SUSPICION Suspicious combination of events: 
* file modification: Library/SMS/Attachments/ab/11
* file attribute change: Library/SMS/Attachments/ab/11
* location service stopped: com.apple.locationd.bundle-/System/Library/LocationBundles/WRMLinkSelection.bundle
* file modification: Library/Preferences/com.apple.ImageIO.plist
* file attribute change: Library/Preferences/com.apple.ImageIO.plist
* file birth: Library/Preferences/com.apple.ImageIO.plist
* file modification: Library/Preferences/com.apple.locationd.StatusBarIconManager.plist
* file attribute change: Library/Preferences/com.apple.locationd.StatusBarIconManager.plist
* file birth: Library/Preferences/com.apple.locationd.StatusBarIconManager.plist
2022-*-* DETECTED Exact match by NetUsage : BackupAgent
2022-*-* DETECTED Exact match by NetTimestamp : BackupAgent
```

## Ссылки

- [https://securelist.ru/operation-triangulation/107470/](https://securelist.ru/operation-triangulation/107470/) - описание атаки и IoC
- [https://github.com/KasperskyLab/triangle_check](https://github.com/KasperskyLab/triangle_check) - скрипт для проверки

## Теги

- [[iOS]]
