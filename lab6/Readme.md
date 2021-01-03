### Для виконання лабораторної роботи 6 необхідно створити аккаунт на GCP.
   1. Після створення аккаунту потрібно створити віртуалку в сервісі `Compute Engine` , налаштування варто обрати дефолтні.
   2. Після того як віртуалка створиться, необхідно залогінитись в неї, використуючи будь який доступний вам спосіб.
   3. Коли ви отримаєте доступ встановіть `ELK` стек, слідуючи інструкції з цього сайту https://logz.io/blog/elk-stack-google-cloud/
   4. Там ж ви знайдете інструкцію по налаштування правил файрволлу, в якому треба буде відкрити порти, для доступу до сервісів.
   5. Після установки сервісів перейдіть по `http://<vm-external-ip>:5601`, щоб перевірити чи сервіси запрацювали `http://<vm-external-ip>:9200`.
   6. Наступним кроком буде створення `Logic App` на Azure Portal. Створіть цей сервіс на тому ж аккаунті, де ви створювали EventHub.
   7. Перейдіть в новостворенний `Logic App` та оберіть `App Designer`.
   8. Оберіть `Blank App` та налаштуйте його, як показано на скріншоті
      ![alt text](http://img.empeek.net/Screenshot%202021-01-03%20at%2020.53.48.png)
   9. Після цього запустіть лабораторну 5 та відправте дані в `Event Hub`.
   10. Через декілька хвилин ви зможете перевірити чи ці данні були отримані на стороні `ElasticSearch`, для цього перейдіть по
    `http://<vm-external-ip>:9200/labour6/_search?pretty=true&q=*:*&size=1000`. Ви маєте побачити список данних в json форматі.