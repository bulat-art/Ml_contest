# Ml_contest

### Задача
Нужно предсказать, сможет ли пользователь успешно закончить онлайн курс Анализ данных в R.
Мы будем считать, что пользователь успешно закончил курс, если он правильно решил больше 40 практических заданий.
В данных: 
* submission_data_test.csv
  * step_id - id стэпа 
  * user_id - анонимизированный id юзера 
  * timestamp - время наступления события в формате unix date 
  * action - событие, возможные значения: 
discovered - пользователь перешел на стэп
viewed - просмотр шага,
started_attempt - начало попытки решить шаг, ранее нужно было явно нажать на кнопку - начать решение, перед тем как приступить к решению практического шага
passed - удачное решение практического шага
* events_data_test.csv
  * step_id - id стэпа
  * timestamp - время отправки решения в формате unix date
  * submission_status - статус решения
  * user_id - анонимизированный id юзера
хранится информация о решениях и действиях для 6184 студентов за первые два дня прохождения курса. Это 6184 студентов, которые проходили курс в период с мая 2018 по январь 2019. 
Используя данные о первых двух днях активности на курсе нужно предсказать, наберет ли пользователь более 40 баллов на курсе или нет.

### Инструменты
*Язык* : Python  
*Библиотеки* : Pandas, NumPy, sklearn, sqlite3  
Для обработки данных создается база данных и обращение, используя sqlite3.   Для обучения модели был выбран алгоритм **RandomForest**.   Метрика качетсва **ROC_AUC**. 
### Результат
Формируется csv файл с колонками user_id, is_gone - вероятность ученика остаться на курсе. 

**Финальный ROC_AUC :  0.83**
