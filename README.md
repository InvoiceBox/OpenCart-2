# Описание платежного модуля ИнвойсБокс для OpenCart 2.0+

Платёжный модуль для интеграции платёжной системы «ИнвойсБокс» и CMS OpenCart версии 2.х. Реализована поддержка платёжного API. Протестировано на системе OpenCart 2.3.

## Установка модуля

1. Распакуйте архив в корень сайта;
2. В административной панели OpenCart пройдите в раздел <strong>"Модули / Расширения" -> "Модули / Расширения" -> В фильтре выберите "Оплата"</strong>;
3. Найдите модуль <strong>«InvoiceBox»</strong> и активируйте его в разделе <strong>Действие</strong>.

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
