# made_nlp

Решение расширенного задания из репозитория https://github.com/yandexdataschool/Practical_DL/tree/spring20/homework04

Выполнение этого задания было осложнено объемом данных для работы, поэтому оно выполнено не совсем так, как предполагалось.

На задание по CV нам по запросу выделяли кластеры AWS с лимитом работы на 40 часов, у меня оставалось время, и мне разрешили использовать остатки для этого задания (работать локально или на колабе не выходило — смог сделать только первые 2 basic ноутбука). Но идеально все равно не вышло. Из train датасета надо было приготовить numpy массив с признаками картинок размера 2048х8х8, но не хватало оперативной памяти и пространства хранилища, поэтому я сделал 16 numpy массивов с признаками (если бы места хватило, то их было бы 20), но нужного размера 2048х8х8. В файле prep.py предобработка данных.

Тренировал модель тоже на AWS, для этого тренировался по очереди на каждой из 16 пар numpy массивов и токенизированных описаний. На каждую пару было 50 эпох, заняло около полутора часов. Loss train был около 2.2, loss val был около 2.8.

После обучения сохранял список токенов "vocab", словарь с индексами и токенами "word_to_index" и веса модели из класса "CaptionNet". Файл обучения train.py.

Полученные файлы загрузил на гугл диск и уже использую в ноутбуке advanced_captioning, поэтому кода тут не так много. Ну и из-за ограничений по ресурсам я не стал распыляться, проверяя разные архитектуры модели и т.п., а сразу постарался сделать что-то более-менее работающее. К тому же в субботу (27.06.20) обещали отключить AWS со всеми лежащими там файлами, а только вчера (25.06.20) сказали, что облако можно исплльзовать для ДЗ по NLP. (ну тут и я поздно спросил, стараясь что-то сделать локально или в колабе)

Оба задания из части basic_part тоже выполнил, там немного комментов, потому что просто восстанавливал код по ходу ноутбукjd.
