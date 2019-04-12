Auto Rss
========
Auto RSS — Модуль для автоматического парсинга и импорта RSS-лент для DLE,предназначен для автоматизированного импорта новостей из RSS каналов к себе на сайт. **(НЕ ГРАББЕР!)**

Целью создания было как обычно: "не нашел нужную программу в интернете - написал свою". Модуль может понадобится когда нужно быстро "накидать новостей с картинками" на сайт.


Auto Rss Pro (v1.0.2)
========
Добавленные функции:

1. hashtag 
Поддержка хештегов для публикаций
если поле хештега в админке пустое - данный параметр игнорируется.
Если в поле указано произвольный хештег с необходимым значением, (1 - опубликовать, 0 - не публиковать) то модуль может как опуликовать, так и пропустить данный пост в зависимости от указанных параметров.

Пример хештеков:

	#vk|1

если в теле публикации будет найден текст вида #vk 
то его осдержимое БУДЕТ импортировано на сайт.

	#other|0 

если в теле публикации будет найден текст вида #other 
то его осдержимое НЕ БУДЕТ импортировано на сайт.

2. showLink 
Добавлен чекбокс - скрыть источник публикации.
Если данный чекбокс активирован - то ссылка на источник не добавляется в публикацию при импорте.

3. yandex_rss 
Добавлена поддержка импорта RSS каналов в формате Яндекс Новостей.

4. Добавлена поддержка вставки видео с Youtube в тело краткой новости. Пока не тестировалось.


**Обновление с версии 0.7 до 1.03**

Для обновления БД действующего сайта необходимо через PMA сделать запрос

	ALTER TABLE  `dle_auto_rss` ADD  `showLink` TINYINT( 1 ) NOT NULL DEFAULT  '0' ,
	ADD  `hashtag` TEXT NOT NULL ,
	ADD  `yandex_rss` TINYINT( 1 ) NOT NULL DEFAULT  '0' ;


где dle_auto_rss

это имя таблицы с вашим префиксом.
