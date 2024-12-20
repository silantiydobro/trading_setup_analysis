# Аналіз торгової стратегії "SILVER BULLET"
Цей проект аналізує торгову стратегію "SILVER BULLET" для основних американських індексів SP500 та NAS100. Основна мета — оцінити результати, які могла б принести торгівля за цією стратегією на дистанції 3 роки (2021, 2022, 2023), а також виявити приховані закономірності для оптимізації торгівлі в майбутньому.

## Цілі проекту
- Оцінка результатів стратегії.
- Визначення впливу сезонності.
- Виявлення закономірностей.
- Аналіз впливу ліквідності на результати торгівлі.
- Вивчення впливу днів тижня на прибутковість трейдів.

## Джерело даних
- Дані були зібрані вручну під час бектесту ринку індексів (SP500 та NAS100).
- Зберігаються у форматі CSV і доступні в папці `data`.

## Структура даних
- `date`
- `session`: Торгова сесія (Лондонська сесія 3-4am UTC-4 NY, Нью-Йоркська 10-11am UTC-4 NY).
- `time`: Час входу в трейд.
- `pair`: Торговий актив.
- `rr`: Співвідношення ризик/прибуток.
- `result`: Результат угоди (TakeProfit/StopLoss/BreakEven).
- `direction`: Напрямок угоди (Long/Short).
- `profit`: Прибуток. 
- `loss`: Збиток.
- `liquidity`: Ліквідність, яку зняла ціна безпосередньо перед входом (сформована до Торгової сесії чи під час неї).
- `screen`: Cкріншот угоди.
- `swp_bfr_ott`: Чи відбувся свіп ліквідності до початку Торгової сесії.

## Ризик-менеджмент
Всі дані наведені для депозиту в 10,000 USD, з ризиком 2% від загальної суми депозиту на кожен трейд.

## Використані інструменти
- **Google Sheets**: Для зберігання, сортування та очищення даних про угоди.
- **Google Looker Studio**: Для створення дашборду, який відображає результати торговлі в різних торгових сесіях, ефективність стратегії на дистанції та загальну прибутковість.

## Візуалізації
На дашборді в Google Looker Studio можна переглянути:

- Ключові метрики (відсоток прибуткових угод, кількість трейдів, середнє співвідношення ризик/прибуток, загальний профіт). 
- Прибуток та Збиток по місяцям.
- Прибуток та Збиток по дням тижня.
- Кількість трейдів по місяцям.
- Відсотковий розподіл по результатам трейдів (прибуток/збиток/беззбиток).
- Розподіл за ліквідністю. 
- Розподіл трейдів по напрямку (long/short).

[Переглянути дашборд](https://lookerstudio.google.com/reporting/5afb8ce2-f730-4e19-9141-bc2b835bedc8)

## Інструкція
1. Завантажте дані про трейди з папки `data`.
2. Відкрийте дашборд у Google Looker Studio за посиланням вище, щоб переглянути візуалізації.
3. Можна самостійно фільтрувати угоди по рокам, активу або торговій сесії для більш детального аналізу.

## Файли
- **data/backtest_silver_bullet.csv**: Основний файл з даними про всі угоди.
- **dashboard/screenshot_1.PNG**: Скріншот дашборду.
- **(https://youtu.be/qxtFSoRdmjc)**: Відеоогляд дашборду.

## Висновки
- Чітко вираженої сезонності стратегія немає (немає такого, що в якісь певні місяці року стратегія працює дуже погано, а в якісь дуже добре). Місяці спаду або зростання змінюються з року в рік, що свідчить про їхню залежність від глобальних циклів ринку.
- SP500 показує вищий відсоток прибуткових угод, але дає менше трейдів, ніж NAS100.
- Немає істотної різниці, чи була ліквідність сформована до чи під час торгової сесії.
- Середа виявляється найменш успішним днем тижня за співвідношенням прибуткових і збиткових угод.
- З усіх днів тижня торговля в лондонську сесію по цій стартегії прибуткова тільки в четвер (2800 прибуток, 400 збиток). Всі інші дні суто збиткові.

## Рекомендації
- Не зосереджуйтеся на тому, чи була ліквідність сформована до або під час торгової сесії. Важливіше, щоб на рівні було достатньо стопів трейдерів, а також щоб ціна демонструвала агресивний прайс-екшен.
- Для збільшення відсотку прибуткових угод торгуйте тільки SP500, але враховуйте, що угод буде менше.
- По можливості використовуйте обережніші підходи в торговлі в середу або намагайтеся уникати входів в цей день.

## Контакти
- [LinkedIn профіль](https://www.linkedin.com/in/hlib-inozemtsev-670ba8124/)
- [GitHub репозиторій](https://github.com/silantiydobro/trading_setup_analysis/tree/main)
