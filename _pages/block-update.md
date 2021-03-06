---
permalink: /block-update.html
title: Блокировка обновлений и доступа к серверам Nintendo
author_profile: true
---
{% include toc title="Разделы" %}

{% spoiler Видеоинструкция %}

{% include youtube.html id="gUGulsJzDKM"  %}
{: .text-center}
{: .notice--info}

{% endspoiler %}

* **Плюсы**
    * Не блокирует доступ к серверам Nintendo, а блокирует возможность авторизации на них. То есть при общении с сервером Nintendo сервер попросту не будет воспринимать консоль как Switch 
    * Будет работать даже если Nintendo изменит способ авторизации, адреса серверов или мало ли ещё  что 
    * Не требует дополнительной настройки 

* **Минусы**
    * Требует взаимодействия с системными файлами через приложение, поэтому потенциально опасен
    * Не поддерживает emunand в SXOS. Используйте stealth-режим прошивки для блокировки обновлений 
	
## Инструкция

### Блокировка доступа к серверам Nintendo  

1. Создайте [резервную копию NAND](backup-nand){:target="_blank"} консоли и поместите её в надёжное место, если ещё не делали этого
{% include inc/launch-hekate.txt %}
1. Установите {% include abbr/kefir_addr.txt %} по инструкции, находящейся в его репозитории
    * Если уже делали, не нужно делать повторно
1. Перейдите в меню "**Payloads**"
    * Если на карте не установлен {% include abbr/kefir_addr.txt %}, то {% include abbr/hekate.txt abbr="hekate" %} загрузится без графического интерфейса. В таком случае `payloads` будет находиться в меню `Launch`, а навигация по hekate будет происходить с помощью кнопок громкости и кнопки включения
1. Выберите "**Incognito_RCM.bin**"
1. Выберите "**Backup (SysNAND)**" или "**Backup (EmuMMC)**" в зависимости от того в каком из разделов вы хотите заблокировать доступ к серверам Nintendo
    * Навигация по меню осуществляется кнопками громкости, а выбор кнопкой (POWER)
    * Если вы не используете EmuNAND, выберите SysNAND 
    * Если вы используете EmuNAND для пиратки, а SysNAND для лицензии, выберите EmuNAND
1. Выберите "**Incognito (SysNAND)**" или "**Incognito (EmuMMC)**" в зависимости от того в каком из разделов вы хотите заблокировать доступ к серверам Nintendo
1. Дождитесь окончания установки и нажмите на любую кнопку 
1. Выберите **Reboot (RCM)** и заново пробросьте пейлоад и войдите в **hekate**
    * Если у вас чип, то выключите приставку и включите, а затем войдите в **hekate**
1. Извлеките карту памяти из приставки и вставьте её в ПК
1. Скопируйте `prodinfo_sysnand.bin` из корня карты памяти в надёжное место - это бекап вашего PRODINFO в не изменённом состоянии
1. Запустите приставку
1. Перейдите в "**Системные настройки**" -> "**Система**" -> "**Серийные номера**". Если в поле "**Консоль**" не указан серийный номер, то всё сделано верно
 
### Восстановление доступа к серверам Nintendo  

1. Скопируйте `prodinfo_sysnand.bin` в корень вашей карты 
{% include inc/launch-hekate.txt %}
1. Установите {% include abbr/kefir_addr.txt %} по инструкции, находящейся в его репозитории
    * Если уже делали, не нужно делать повторно
1. Перейдите в меню "**Payloads**"
    * Если на карте не установлен {% include abbr/kefir_addr.txt %}, то {% include abbr/hekate.txt abbr="hekate" %} загрузится без графического интерфейса. В таком случае `payloads` будет находиться в меню `Launch`, а навигация по hekate будет происходить с помощью кнопок громкости и кнопки включения
1. Выберите "**Incognito_RCM.bin**"
1. Выберите "**Restore (SysNAND)**" или "**Restore (EmuMMC)**" в зависимости от того в какой из разделов вы хотите восстановить PRODINFO
1. Дождитесь окончания установки и нажмите на любую кнопку 

___

[Закрыть страницу](javascript:window.close();)
{: .notice--success}