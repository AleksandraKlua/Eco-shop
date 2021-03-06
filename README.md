# Eco-shop
Веб-сайт магазина эко-товаров, написанный на языке PHP с использованием HTML, CSS, JavaScript, а также запросов к базе данных на языке HTML. В качестве сервера используется локальный сервер Apache, в качестве базы данных - MySql. Реализуемые функции, права доступа и требования к веб-сайту приведены ниже.

## Функции
Разрабатываемая система должна выполнять следующие функции:
1)	предоставить доступ всем группам пользователей к просмотру товара, формированию корзины интересующих его товаров и оформлению заказа для его приобретения с выпиской счета;
2)	предоставить всем группам пользователей возможность создания личного кабинета, за исключением личного кабинета модератора, который может создаваться только после получения соответствующего разрешения от владельца магазина;
3)	предоставить всем группам пользователей возможность получения уведомления о статусе заказа в качестве смс-сообщений или сообщений на e-mail;
4)	предоставить всем группам пользователей возможность оставлять комментарии на приобретенные товары;
5)	предоставить зарегистрированным покупателям возможность контроля состояния всех покупок, произведенных в магазине из своего личного кабинета;
6)	создать систему поиска товара, в том числе с использованием фильтрации и сортировки;
7)	реализовать систему скидок;
8)	модератору предоставить возможность переводить статус заказа в разные состояния: «оформлен», «оплачен/получен»;
9)	модератор должен иметь право вводить в базу данных информацию о поступлении на склад нового товара;
10)	модератор должен иметь право вносить в базу данных изменения о количестве уже существующего товара (при поступлении его на склад) или об изменении его цены;
11)	владелец магазина должен иметь право определять прибыль, полученную магазином за любой промежуток времени;
12)	владелец магазина должен иметь право определять рейтинг товаров, которые приносят наибольшую прибыль в заданном временном интервале (в рейтинг товара включить первые десять наименований товара). 

## Права доступа к системе
|      **Тип пользователя**        |                     **Права доступа**                       | 
|:---------------------------------|:------------------------------------------------------------|
| Любая группа (в т.ч. гость)      | Просмотр товаров, добавление в корзину, заказ товаров       |
| Покупатель  без личного кабинета | Создание личного кабинета                                   |
| Авторизованный покупатель        | Просмотр прошлых заказов (при наличии) и отложенных товаров |
| Модератор	                       | Добавление, редактирование, удаление товаров                |
| Владелец                         | Полный доступ, за исключением изменения исходного кода      |
| Администратор                    | Полный доступ, изменение исходного кода ИС                  |

## Требования к базе данных системы
Таблицы базы данных должны позволять хранить информацию, представленную ниже.
**О покупателях:**
*	фамилия, имя, отчество покупателя,
*	контактный номер телефона,
*	e-mail,
*	адрес доставки (может меняться с каждым заказом, необязательно, т.к. возможно получение заказа в магазине),
* день рождения (опционально),
*	пароль (для покупателей с личным кабинетом),
*	дата регистрации,
*	заказанные и оплаченные товары,
*	отложенные товары (в списке закладок),
*	дата покупки.

**О товаре, продаваемом в магазине:**
*	название товара,
*	изображение товара,
*	тип товара (продукты питания, бытовые товары, косметика),
*	доступность (в наличии/нет в наличии),
*	закупочная цена товара,
*	цена товара при продаже,
*	дата поставки товара,
*	количество товара в магазине,
*	поставщик,
*	производитель,
*	рейтинг (оценка) товара.

**О менеджерах:**
*	фамилия, имя, отчество,
*	e-mail,
*	пароль.

**О поставщике:**
*	название организации,
*	адрес организации,
*	контактный телефон,
*	e-mail.

**О заказах:**
*	номер заказа,
*	покупатель,
*	товар,
*	дата заказа,
*	цена товара,
*	стоимость заказа,
*	статус (оплачен, оформлен).

**О владельце интернет-магазина:**
*	фамилия, имя, отчество,
*	e-mail, 
*	пароль.

**О системном администраторе магазина:**
*	фамилия, имя, отчество,
*	e-mail,
*	пароль.

## Front-end
Главная страница: поисковая строка, меню, каталог.
Страница категории (продукты питания, бытовые товары, косметика) с выводом списка некоторых товарных позиций в виде плитки с возможностью поиска, сортировки и фильтрации товаров по заданным критериям.
Страница товара: название товара, описание товара, сведения о товаре (цена, поставщик, наличие), поле для ввода желаемого количества заказываемого товара, отзывы о товаре, оценка товара, кнопка добавления товара в корзину.
Страница личного кабинета покупателя: информация о пользователе (данные указанные при регистрации), раздел с заказами (текущие заказы и уже полученные заказы), раздел с настройками (возможность изменить пароль, изменить параметры информационной рассылки и уведомлений о статусе заказа).
Страница регистрации: форма для ввода данных. 
Страница корзины: список товаров с характеристикой каждого товара, итоговая стоимость заказываемых товаров с указанием стоимости доставки и с применением скидок (при наличии).
Страница личного кабинета менеджера: информация о менеджере, раздел с новыми заказами, которые можно принять в оформление, страница с текущими и архивными заказами, страница с товарами, возможность их изменения и удаления.
Страница личного кабинета владельца: стартовая страница после входа, страница с вводом данных для расчета прибыли, страница с данными о прибыли за выбранный период, страница с рейтингом товаров, страница для ввода данных для поиска самых популярных товаров, страница с выводом 10 самых популярных товаров за выбранный период. 

## Файловая структура системы
| **Название файла**|                                     **Назначение**                                    | 
|:------------------|:--------------------------------------------------------------------------------------|
| add.php	          | Обработчик добавления нового модератора |
| add_admin.php    	| Страница добавления нового модератора                                                 | 
| admin_pa.php	    | Главная страница личного кабинета модератора                                          | 
| admin_product.php	| Страница для редактирования и удаления товаров                                        | 
| auth.php	        | Обработчик формы аутентификации                                                       | 
| basket.php	      | Страница корзины товаров                                                              | 
| cancel.php      	| Обработчик для отмены заказа покупателем                                              | 
| catalog.php     	| Страница каталога товаров                                                             | 
| change.php      	| Обработчик для изменения модератором статуса заказа                                   | 
| change_status.php	| Страница изменения статуса заказа                                                     | 
| changeRat.php   	| Обработчик для изменения владельцем рейтинга товара                                   | 
| dbconnect.php	    | Скрипт подключения к базе данных                                                      | 
| deleteUser.php	  | Обработчик для удаления личного кабинета покупателя                                   | 
| editProduct.php	  | Обработчик для формы редактирования и удаления товара                                 | 
| footer.php	      | Подвал страницы                                                                       |  
| form_auth.php	    | Форма для прохождения процедуры аутентификации                                        | 
| form_register.php	| Форма для прохождения процедуры регистрации                                           | 
| free_orders.php	  | Страница со свободными для модераторов заказами                                       | 
| header.php	      | Шапка страницы                                                                        | 
| income.php	      | Страница для ввода промежутка дат для вывода прибыли за этот промежуток               | 
| index.php        	| Главная страница сайта                                                                | 
| items_rating.php	| Страница для ввода промежутка дат для вывода рейтинга товаров с наибольшими продажами | 
| logout.php	      | Скрипт для выхода из личного кабинета                                                 | 
| makeOrder.php	    | Обработчик для оформления заказа                                                      | 
| order_archive.php	| Вывод заказов покупателя                                                              | 
| orderlist.php	    | Детализация отдельного заказа                                                         | 
| owner_pa.php	    | Главная страница личного кабинета владельца                                           | 
| product.php	      | Обработчик для формы добавления товара                                                | 
| rating.php	      | Обработчик для вывода рейтинга товаров                                                | 
| register.php	    | Обработчик формы регистрации                                                          | 
| showIncome.php	  | Обработчик для вывода прибыли                                                         | 
| take_order.php	  | Обработчик для взятия заказа модератором                                              | 
| update.php	      | Страница с выводом товаров для редактирования                                         | 
| user_pa.php	      | Личный кабинет покупателя                                                             | 
| userChange.php	  | Обработчик формы редактирования данных покупателя через личный кабинет                | 
| css/cart.css	    | Стиль для корзины                                                                     | 
| css/panel.css	    | Стиль для дополнительных меню разных групп пользователей                              | 
| css/style.css	    | Стили для всего проекта                                                               | 

