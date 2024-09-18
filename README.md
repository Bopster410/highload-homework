# ДЗ по курсу "Хайлоад"
## 1. Тема и целевая аудитория
### Тема
**Spotify** - стриминговый сервис для прослушивания музыки  
### Аудитория 
Согласно данным отчета за 2-й квартал 2024 года, суммарное число активных пользователей сервиса за месяц составляет **626 млн**.
```mermaid
pie
    title Распределение по регионам
    "Европа" : 175
    "Северная Америка" :112
    "Латинская Америка" : 137
    "Остальной мир": 206 
```
### Ключевой функционал
* регистрация;
* прослушивать музыку;
* создавать плейлисты;
* серверная история недавно прослушанных песен;
* плейлисты с рекомендациями;
* статистика по исполнителю;
* загрузка музыки;
* поиск музыки.
### Ключевые продуктовые решения
* композиции хранятся на серверах продукта.
## 2.Расчет нагрузки
### Продуктовые метрики
| Метрика                                          	        |             Значение метрики 	|
|----------------------------------------------------------	|-----------------------------:	|
| Месячная аудитория                               	        |                      626 млн 	|
| Дневная аудитория                                	        |                     15.7 млн 	|
| Средний размер хранилища на пользователя         	        |                      ~25 МБ* 	|
| Среднее время прослушивания за день пользователем         | 148 минут (~40 разных песен) 	|
| Среднее количество созданных плейлистов за день	        |                      1.3 млн 	|
| Среднее количество добавлений песен в плейлисты за день	|                     31.4 млн  |
| Среднее количество поисков за день                        |                     62.8 млн 	|
| Среднее число регистраций за день                	        |                    130 тысяч 	|

> \* *20 МБ как максимальный размер аватарки + мета информация о пользователе и его плейлистах*  
### Технические метрики
#### Хранилища
Для вычисления объема хранилища, выделяемого на музыку, примем, что каждая песня сохраняется в 4 вариантах качества: низком, среднем, высоком и очень высоком и что всего их (на сентябрь 2024 года) 108 миллионов. Средний размер их (для песни длиной 3 минуты) соответственно составляет 540 КБ, 2.16 МБ, 3.6 МБ и 7.2 МБ. Таким образом, на каждую композицию выделяется в среднем 13.5 МБ, а общий объем хранилища можно принять равным: $108 млн \times 13.5$ МБ.

| Хранилище    	| Размер, ТБ 	|
|--------------	|-----------:	|
| Пользователи 	|      12520 	|
| Музыка       	|       1458 	|

#### Сетевой трафик
Битрейт песен в зависимости от качества составляет от 24 до 320 Кбит/c. Для вычисления сетевого трафика примем средний битрейт равным: $\frac{320 + 24}{4} = 150$ Кбит/с. 
| Действие пользователя 	| Среднее потребление в течение суток, Гбит/с 	| Пиковое потребление в течение суток, Гбит/с 	| Суммарный суточный, Гбайт/сутки 	|    RPS    	|
|---------------------    	|:-------------------------------------------:	|:-------------------------------------------:	|:-------------------------------:	|:---------:	|
| Прослушивание музыки  	|                    247.19                   	|                    741.6                    	|            20&nbsp;912&nbsp;400   | 1&nbsp;613&nbsp;611 	|
| Поиск                 	|                     8.72                    	|                    26.17                    	|              94&nbsp;200          |    727    	|
| Создание плейлиста    	|                    0.002                    	|                    0.006                    	|               20.8              	|     15    	|
| Добавление в плейлист 	|                     0.03                    	|                     0.09                    	|               314               	|    363    	|
| Регистрация           	|                    0.0002                   	|                    0.0006                   	|               2.1               	|    1.5    	|

## Используемая литература
1. [Spotify](https://open.spotify.com/)
2. [Квартальный отчет](https://investors.spotify.com/financials/default.aspx#quarterly-results)
3. [Hypestat](https://hypestat.com/info/spotify.com)
4. [Insights into Spotify Listening Statistics: Millions of Users and Tracks](https://wifitalents.com/statistic/spotify-listening/)
5. [Exploring Eye-Opening Spotify Playlist Statistics: 4 Billion Playlists Created](https://gitnux.org/spotify-playlist-statistics/)
6. [How Much Data Does Spotify Use?](https://www.whistleout.com.au/MobilePhones/Guides/How-Much-Data-Does-Spotify-Use)

