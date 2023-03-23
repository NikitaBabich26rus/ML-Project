# ML-Project

## Условие работы

В рамках данной работы был проведен анализ данных о картинах.    
Были сформулирована гипотеза о предсказании целевого признака `Цена картины`.    

## Первый результат
Использовались признаки: `Автор`, `Техника рисования`, `Материал`, `Стиль`, `Есть ли подпись`, `Размер`, `Город`.    
Модели: `GradientBoostingRegressor`. В качестве метрики использовался `R2`.     
Результат: `0.019`.

## Второй результат
После получения неудовлетворительного результата было приято решение использовать признак `EstimateFrom`.

Использовались признаки: `Автор`, `Техника рисования`, `Материал`, `Стиль`, `Есть ли подпись`, `Размер`, `Город`, `EstimateFrom`.     
Модели: `GradientBoostingRegressor`, `LinearRegression`, `DecisionTreeRegressor`.        
В качестве метрики использовался `mean R2`.          
Результат:        
`LinearRegression`, mean R2: 0.82       
`DecisionTreeRegressor`, mean R2: 0.75       
`GradientBoostingRegressor`, mean R2: 0.83       

## Третий результат
После показания лучшего результата модели `GradientBoostingRegressor`, были подобраны параметры для данной модели.

Использовались признаки: `Автор`, `Техника рисования`, `Материал`, `Стиль`, `Есть ли подпись`, `Размер`, `Город`, `EstimateFrom`.     

Модели: `GradientBoostingRegressor`.        

Параметры:           
loss: `['squared_error', 'absolute_error', 'huber', 'quantile']`             
n_estimators: `[1, 10, 100, 500, 1000]`         
criterion: `['friedman_mse', 'squared_error']`      
max_features: `['auto', 'sqrt', 'log2']`               

В качестве метрики использовался `mean R2`.          
Результат:           
`GradientBoostingRegressor`, mean R2: 0.84     

Лучшие параметры: `{'criterion': 'squared_error', 'loss': 'absolute_error', 'max_features': 'auto', 'n_estimators': 500}`




