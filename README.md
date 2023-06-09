# Project_GasOilAnalisis
В данном проекте наша команда анализирует данные о капитализации крупнейших нефтегазовых компаний России, а также то, как капитализации соотносятся со следующими показателями:

1. Стоимость барреля нефти Brent
2. Стоимость барреля нефти WTI
3. Стоимость Природного газа
4. Курс рубля к доллару
5. Количество болеющих covid-19 на опредённую дату

## Сбор данных

В качестве источника данных мы использовали сайт https://ru.investing.com/ . На нём мы нашли готовые файлы по стоимости нефти и газа, а также курса рубля к доллару, котировки акций по датам (файлы в репозитории: Brent.csv, WTI.csv, USD_RUB.csv, gaz.csv, gazp.csv, LKOH.csv, NVTK.csv, SNGS.csv, ROSN.csv).

Информацию об общем количестве акций и дополнительных эмиссиях акций мы брали на сайте Московской Биржи. У 4 компаний из 5 количество акций со временем не изменялось, поэтому для поиска их капитализаций можно просто было умножить количество акций на их цену. У Лукойла были дополнительные эмиссии, инорфмацию по ним мы добавляли в файле **itog.ipnyb**.

https://www.moex.com/n21804
https://www.moex.com/n24862
https://www.moex.com/n27153

Информацию о курсе евро к рублю мы взяли с сайта: https://bhom.ru/currencies/eur/?startdate=alltime (был скачан готовый файл)

Для того, чтобы учесть влияние пандемии, мы решили добавить в наш датасет данные по количеству болеющих в мире covid-19. Это связано с тем, что пандемия глобально влияет на спрос на торговые мощности, и, как следствие, на спрос на энергетические ресурсы. Эти факторы могут оказывать влияние на капитализацию нефтегазовых компаний, в том числе и в России. 

### Парсинг
Информацию по заболевшим мы спарсили с сайта: https://coronavirus-graph.ru/mir
Код с парсингом мы сохранили в файл **parsim.ipnyb** . Файл с датафреймом по парсингу covid.csv, который у нас вышел мы загрузили в репозиторий, чтобы в последующем его можно было открывать в коде.
Также в этом пункте мы использовали ChatGPT (мы забыли, как делать парсинг, и он нам подсказал основы, с помощью которых мы справились с задачей).


<a href="https://ibb.co/syZBnmN"><img src="https://i.ibb.co/r4VWY7z/Nfwew-Uz-XZ94.jpg" alt="Nfwew-Uz-XZ94" border="0"></a>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/tYrGJcK/D369c0kiap-Q.jpg" alt="D369c0kiap-Q" border="0"></a>

## Первичная обработка данных, Визуализация и Проверка гипотез
Создание итогового датафрейма, которое использует файлы формата .csv, которые лежат в репозитории и результаты парсинга (файл covid.csv) находится в файле **itog.ipnyb** .
В этом же файле находятся и первичная обработка данных, визуализация и проверка гипотез.

## Машинное обучение
Нашей целью было найти модель, которая может предсказывать суммарную капитализацию рассматриваемых компаний на основе данных о 5 параметрах, которые перечислены в начале файла Readme. 

Обучение линейной регрессии лежит в файле **mashinka.ipnyb**

Обучение модели "случайный лес" и бустингу находится в файле **randomforest_boosting.ipnyb**




