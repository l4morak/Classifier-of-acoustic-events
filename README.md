# Classifier of Acoustic Events
Решение задачи "Классификатор акустических событий". (файл main.py)

Средняя точность на известных объектах test выборки - 85 % (Accuracy Score); 97.5 % (ROC AUC Score); 86 % (Mean Average Precision).  
Для обучения модели также использовался датасет ESC-50. (https://github.com/karoldvl/ESC-50)

Модель использует предобученные сверточные слои модели VGGish. 
(https://github.com/tensorflow/models/tree/master/research/audioset - ссылка на оригинальный источник)
(https://github.com/DTaoo/VGGish - VGGish на Keras)  
Результаты VGGish передаются полносвязной сети с тремя слоями. (800 нейронов, 800 нейронов, 8 нейронов)

Для расчета конечного результата используются 10 одинаковых сетей, берется среднее арифметическое их предсказаний. Это сделано из-за того, что конечный результат после обучения модели может сильно отличаться на 5-8 % в худшую сторону.

Для запуска разместите внутри одной папки три папки: audio/, test/ и ESC-50-master. (https://github.com/karoldvl/ESC-50).
В файле main.py значение переменной root_dir замените на путь к этой папке.  

P.S. Рекомендуется использовать GPU. Этап, связанный с VGGish, затягивается на процессоре минут на 5.  
P.P.S Результаты немного улучшились. Заметил опечатку в коде.
