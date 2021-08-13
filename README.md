***Определение удельной стоимость коммерческой недвижимости в аренду.***   
*Задача*: Построить модель для определения стоимость квадратного метра офиса (задача регрессии).  
*Данные и фичи*: признаки (40 признаков, в т.ч. сильно коррелирующие или косвенно влияющие на формирование целевого признака- их количество после анализа значительно сокращено), характеризующие офисную недвижимость. Целевой признак: 'price_per_m2'.  
*Стек инструментов*: Применены StandardScaler, OrdinalEncoder, GridSearchCV, cross_val_score, train_test_split, 3 модели (RandomForestRegressor, GradientBoostingRegressor	, CatBoostRegressor) + Stacking.   
*Результаты*: Данные оказались с аномальными значениями (миллиарды в показателях) площади и цен, также целевой признак рассчитан невсегда корректно- данный факт проверен при добавлении расчетного столбца удельной цены. Много пропусков, по итогу обработки выборки сохранено порядка 30% для предсказания по метрике заданного бизнесом показателя. Выбор лучшей модели по метрике MAE- хороший синергический эффект показала VotingRegressor(): на тесте- 16294 руб./ трейне- 16153 руб. при средней стоимости квадратного метра по выборке- 53000-57000 руб. Детализация таргета и признаков выведена допопнительно в Tableau.  
[*Проект*](https://github.com/k-vero2021/ML/blob/main/Office_2021.ipynb)  
