===============================================
Использование Google Images для ваших продуктов
===============================================

Целесообразно использование изображений продуктов в системе Модули,
например, чтобы быстро найти продукт или проверить,
отсканировали ли вы нужный товар. Но подбирать изображения для каждого продукта
вручную может быть довольно затруднительно. Поисковая технология **Google Custom Search** позволяет
автоматически находить изображение
продукта на основе
штрих-кода, экономя много времени и ресурсов.

.. _product_images/configuration:

Настройки
=========

Эта функция требует настройки как в Google, так и в системе Модули.

Имея бесплатный аккаунт Google, вы можете получать до 100 бесплатных изображений в день.
Если вам нужен более высокий показатель,
то потребуется перейти на платный аккаунт.

.. _product_images/google-api-dashboard:

Панель инструментов API Google
------------------------------

#. Перейдите на страницу `Google Cloud Platform API & Services <https://console.developers.google.com/>`_,
   чтобы сгенерировать учетные данные Google Custom Search API.
   Войдите в систему под своей учетной записью Google.

#. Выберите или создайте проект API для хранения учетных данных. Придумайте характерное название
   проекта (например, Изображения Модули).

#. В разделе учетных данных нажмите на **Создать учетные данные** и выберите **Ключи API**.

   .. image:: product_images/gcp-api-services.png
      :align: center
      :alt: API & Services page on Google Cloud Platform

#. Сохраните свой **API ключ**. Он понадобится вам для следующего шага в системе!

#. В строке поиска найдите **Google Custom Search API**.


   .. image:: product_images/gcp-search.png
      :align: center
      :alt: Search bar containing "Custom Search API" on Google Cloud Platform

#. Включите API.

   .. image:: product_images/gcp-custom-search-api.png
      :align: center
      :alt: "Custom Search API" tile with Enable button highlighted on Google Cloud Platform

.. _product_images/google-pse-dashboard:

Панель инструментов программируемой поисковой системы Google
------------------------------------------------------------

#. Перейдите на страницу `Google Programmable Search Engine <https://programmablesearchengine.google.com/>`_ и
   нажмите на кнопку **Начать**. Войдите в систему под своей учетной записью Google.

   .. image:: product_images/google-pse.png
      :align: center
      :alt: Google Programmable Search Engine page with the **Get Started** button on the up-right
            of the page

#. Выберите язык и введите название поисковой системы. Используйте точное название
   (например, Изображения Модули).

   .. note::
      Google не позволяет создать поисковую систему без ввода хотя бы одного конкретного
      сайта для поиска. Для этого шага вы можете указать любой сайт (например, www.google.com)
      и удалить его позже.

#. Утвердите форму, нажав на **Create**. Затем перейдите в режим
   редактирования поисковой системы,
   которую вы создали (для этого нажмите на **Control Panel** на странице подтверждения
   или кликните по названию вашей поисковой системы на главной странице).

#. На вкладке **Basics** включите параметры **Image Search**, **SafeSearch** и
   **Search the entire web**.

   .. note::
      После включения **Search the entire web** вы можете безопасно удалить сайт,
      который вы указали в предыдущем шаге.


#. Сохраните свой **Search Engine Id**. Он понадобится вам для следующего шага в системе!

.. _product_images/setup-in-odoo:

Система Модули
--------------

#. Перейдите в меню: :menuselection:`Настройки --> Общие настройки --> Интеграции` и
   активируйте функцию **Google Images**. Нажмите **Сохранить**.

#. Вернитесь в :menuselection:`Настройки --> Общие настройки --> Интеграции`, введите свой
   **Ключ API**
   и **Search Engine ID** в настройках **Google Images**.

.. _product_images/get-product-images:

Автоматический поиск изображений продуктов
==========================================

Автоматический поиск изображений продуктов доступен
на любой странице со списком продуктов или вариантов продуктов.
Ниже приводится пошаговая инструкция для приложения *Склад*.

#. Перейдите в меню Продукты (:menuselection:`Продукты --> Продукты`
   или :menuselection:`Продукты -->
   Варианты продукта`) из любого приложения, использующего продукты, например Склад или Продажи.

#. Из списка выберите продукты, для которых необходимо подобрать изображение.

   .. important::
      Будут обработаны только 10 000 первых выбранных продуктов или вариантов продуктов.

   .. note::
      - Система использует только продукты или варианты продуктов со штрихкодом и без изображения.
      - Если выбрать продукт, у которого есть один или несколько вариантов из списка продуктов,
        будет обработан каждый вариант, соответствующий предыдущим критериям.

#. В меню действий выберите **Get Pictures from Google Images** и подтвердите выбор, нажав на кнопку
   **Получить изображение**.

#. Изображения начнут постепенно появляться.

   .. note::
     - Только 10 первых изображений будут сразу загружены. Если вы выбрали более 10, остальные будут
       подгрузятся в фоновом режиме.
      - Система обрабатывает около 100 изображений в минуту. По достижению определенного лимита
        в платной или бесплатной версии Google, загрузка изображений будет приостановлена
        на 24 часа. После этого загрузка будет возобновлена с того места,
        где ранее была приостановлена.

