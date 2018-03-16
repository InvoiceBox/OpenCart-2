# Описание платежного модуля ИнвойсБокс для OpenCart 2.0+

Платёжный модуль для интеграции платёжной системы «ИнвойсБокс» и CMS OpenCart версии 2.х. Реализована поддержка платёжного API. Протестировано на системе OpenCart 2.3.

## Установка модуля

1. Распакуйте архив в корень сайта;
2. В административной панели OpenCart пройдите в раздел <strong>"Модули / Расширения" -> "Модули / Расширения" -> В фильтре выберите "Оплата"</strong>;
3. Найдите модуль <strong>«InvoiceBox»</strong> и активируйте его в разделе <strong>Действие</strong>.

### OCMOD функции

Для корректной работы **отсроченной оплаты** необходимо установить OCMOD-расширение модуля.

1. В "Панель администратора" - "Модули" - "Установка расширений" нажмите кнопку "Загрузить" и выберите файл ocmod/invoicebox_laterpay.ocmod из  дистрибутива.
1. После появления надписи "Модуль успешно установлен!" необходимо перейти в "Панель администратора" - "Модули" - "Модификаторы" и нажать кнопку "Обновить"

## Настройка модуля

1. В административной панели OpenCart пройдите в раздел <strong>"Модули / Расширения" -> "Модули / Расширения" -> В фильтре выберите "Оплата"</strong>;
2. Нажмите на активную кнопку редактирования;
3. В открывшемся окне редактирования настроек заполните поля:
    - "Идентификатор магазина"
    - "Региональный код магазина"
    - "Ключ безопасности магазина"
4. Настройте статусы заказов, выбирая для каждого статус из списка возможных;
5. Укажите порядок сортировки модуля и выберите статус для модуля: <strong>Включено</strong>.

### Специфические настройки 

Тестовый режим - включите его для проведения тестовых платежей, при включении этого режима, вы пройдете все шаги в платежном терминале ИнвойсБокс,
но деньги с вашей карты списаны не будут.

	
Статус заказа после оплаты - После успешной оплаты заказа, заказу будет установлен выбранный статус.
	
Статус заказа после подтверждения - При нажатии на кнопку "Подтвердить" на последнем этапе оформления заказа, заказу будет установлен выбранный статус.
   
Статус заказа после неудачной оплаты - Если Invoicebox вернет покупателя после неудачного платежа, заказу будет установлен выбранный статус.
    
Статус заказа для отсроченной оплаты -  После проверки заказа менеджер магазина выставит данный статус, покупатель будет уведомлен по e-mail и сможет оплатить заказ.
Также, ссылка на оплату появится в личном кабинете покупателя в разделе "Мои заказы".

БУДЬТЕ ВНИМАТЕЛЬНЫ!
Если данный статус будет совпадать со "статус заказа после подтверждения" - режим отсроченной оплаты будет отключен и покупатели будут перенаправляться на сайт "INVOICEBOX" для оплаты сразу после нажатия на кнопку "Оформить заказ".
    
Режим отсроченной оплаты - При включенном режиме отсроченной (отложенной) оплаты покупатель сможет оплатить заказ только после проверки заказа менеджером магазина.
Если Вам необходимо, чтобы у покупателя была возможность произвести оплату сразу после оформления заказа без подтверждения менеджером - не включайте эту опцию.

Название - Название метода оплаты на странице оформления заказа.
    
Инструкция по оплате - Инструкция по оплате выводится при подтверждении заказа. Если поле не заполнено - инструкция по оплате выводиться не будет.

Отображать иконку "Оплатить заказ" в ЛК покупателя, если оплата заказа прервана.

Как это работает? Покупатель перешел на сайт платежной системы и не стал оплачивать заказ (передумал, не хватило денег, отключили электричество в доме или офисе и пр.). Тогда в его Личном Кабинете (ЛК) в списке истории заказов появится иконка "P", нажав на которую покупатель сможет снова попробовать оплатить свой заказ. Иконка появится только в том случае, если текущий статус  заказа покупателя совпадает со статусом заказа, указанных в полях "Статус заказа после подтверждения" и "Статус заказа после неудачной оплаты".
    
Текст кнопки button_confirm ("Потвердить заказ") - Кнопка выводится на последнем этапе оформления заказа. При нажатии на нее заказ будет сформирован окончательно и покупатель будет отправлен для оплаты на сайт платежной системы (если режим отсроченной оплаты отключен).

### Настройка панели ИнвойсБокс:

1. Для настройки панели управления ИнвойсБокс пройдите по url - https://login.invoicebox.ru/ ;
1. Авторизуйтесь и пройдите в раздел "Мои магазины". "Начало работы" -> "Настройки" -> "Мои магазины";
1. Пройдите по вкладку "Уведомления по протоколу" -> выберите "Тип уведомления" "Оплата/HTTP/Post (HTTP POST запрос с данными оплаты в переменных)"
1. В поле "URL уведомления" укажите:

    `<домен_сайта>/index.php?route=extension/payment/invoicebox/callback`

1. Сохраните изменения.
