# DEVLINE

## Overview

Шаблон автоматически ищет камеры и создает связанный с ними элемент данных а также триггер для проверки их состояния.

Для работы требуется:</p>
ПО Intellect версии не ниже 4.11.3.4650 (на предыдущих версиях некорректно работает API)</p>
Веб-сервер 2.0.1

## Author

FoxSusR

## Macros used

There are no macros links in this template.

## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|Cameras discovery|Интервал можно уменьшить, установлен для тестирования.|`HTTP agent`|videoserver.camera.discovery<p>Update: 1m</p>|


## Items collected

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|Videoserver Camera {#CAMERA}|<p>-</p>|`HTTP agent`|videoserver.camera.state.[{#CAMERA}]<p>Update: 1m</p>|


## Triggers

|Name|Description|Expression|Priority|
|----|-----------|----------|--------|
|{#CAMERA} is not working|<p>-</p>|<p>**Expression**: find(/ITV Intellect/videoserver.camera.state.[{#CAMERA}],3m,,"disconnected")=1</p><p>**Recovery expression**: find(/ITV Intellect/videoserver.camera.state.[{#CAMERA}],3m,,"disconnected")=0</p>|average|
