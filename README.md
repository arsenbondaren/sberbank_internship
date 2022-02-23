# sberbank_internship
В данном репозитории находится проект выполненный в рамках онлайн стажировки в Сбере.
Задачей проекта было построить модель прогнозирующую стабильную часть средств, на счетах клиентов банка, на определенную дату. Горизонт прогноза - 12 месяцев. 
После анализа данных  было принято решение построить модель, базирующуюся на трёх прогнозах моделей: 
1. Модель Винтера-Хольтерса с растущим трендом;
2. Модель Винтера-Хольтерса с затухающим трендом;
3. Линейная регрессия.
Итоговый прогноз модели является усредненным значением прогноза трёх данных моделей.
В модели линейной регрессии прогноз строится только на данных за предшествующий прогнозу год, т.к. при более длинных периодах качество прогноза линейной регрессии уже недостаточно высоко. При этом ожидается, что следующий год будет подобен текущему и регрессия прогнозирует максимально близкие значения.
В данных также наблюдается сезонность. Сезонные поправки учтены во всех моделях. Период сезона составляет 365 дней.
В моделях Винтера-Хольтерса прогноз строится на данных за последние 4 года, т.к. более старые данные уже неактуальны и не несут информатвиности.
Модель завернута в класс TimerowPredictor(). При определении класса ему на вход сразу подается временной ряд. 
Прогноз, в виде Series, можно получить вызвав метод predicted_values(). Чтобы посмотреть прогноз на графике - метод prediction_plot(). 
Если нужно посмотреть прогноз на тренировочных данных и его визуализацию на грфике, с посчитаной ошибкой в % - методы predicted_train_values() и prediction_plot() соответственно.
