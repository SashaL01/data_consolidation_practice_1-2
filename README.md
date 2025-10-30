# data_consolidation_practice_1-2


Лабораторная работа 1-2. Современный парсинг динамических веб-сайтов investing
студент Ли АА

Бизнес-кейс Анализ акций с высокой активностью: сбор данных.

задача Собрать тикер, название,цену. Найти акции с наибольшим процентным изменением за день.

**в задании поменял finance.yahoo.com/mostactive на trending-stocks **

Цель работы: научиться извлекать данные с веб-страниц, которые подгружают контент динамически с помощью JavaScript. Освоить использование библиотеки Selenium для управления браузером и языка XPath для точного поиска элементов на странице.

Объект парсинга: страница "trending stocks" сайта investing.com.

Анализ структуры сайта

Сайт Investing.com это веб-сайт, на котором можно просматривать финансовую информацию, котировки акций, статистику, Теханализ Финансов разных компаний. В рамках проекта был проведён парсинг страницы «Трендовые акции» — https://ru.investing.com/equities/trending-stocks

На странице представлена таблица с актуальными данными по акциям российских компаний. 

Название — имя компании ,<br>
Послед. — последняя цена акции,<br>
Макс. — максимальная цена за день,<br>
Мин. — минимальная цена за день,<br>
Изм. — абсолютное изменение цены,<br>
Изм.% — процентное изменение цены,<br>
Объём — объём торгов.<br>

Каждая строка таблицы <tr> это одна компания и содержит несколько ячеек <td>, внутри каждой из которых хранится отдельный показатель:
Название компании — текст внутри элемента <span class="block overflow-hidden text-ellipsis whitespace-nowrap>;
Последняя цена — в <td> с блоке с классом <td class = datatable-v2_cell__IwP1U dynamic-table-v2_col-other__zNU4A text-right rtl:text-right>; 
Максимальная и минимальная цена — в блоке с классом <td class = "datatable-v2_cell__IwP1U dynamic-table-v2_col-other__zNU4A text-right rtl:text-right">; 
Изменение  — в блоке с классом <td class = "datatable-v2_cell__IwP1U datatable-v2_cell--up__lVyET datatable-v2_cell--bold__cXQUV dynamic-table-v2_col-other__zNU4A text-right font-bold rtl:text-right">; 
Объём торгов — в элементе <td data-test="volume-cell">. 

Структура сайта
<img width="1885" height="352" alt="image" src="https://github.com/user-attachments/assets/470c1f29-82a4-4b38-84ba-25e9ae3bc5f1" />
