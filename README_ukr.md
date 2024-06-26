# Розробка плати SLS для шлюзів Xiaomi

Прийшов до розробки власної плати для шлюзу SLS. Тому що замовляти плати із Росії стало не зручно і хочеться додати щось своє. Плата підходить для шлюзів Xiaomi, а за рахунок додавання прорізу під ще одну клямку, підходить і до інших шлюзів Aqara та Xiaomi, де одна клямка зміщена. Іноді потрібна невелика модифікація корпусу шлюзу типу видалення штирьків, які упираються в платню або тунелю датчика світла. Все підганяється за місцем.

Сьогодні плата SLS може працювати як зі штатною платою живлення шлюзу та світлодіодами, так і окремо. Для окремої роботи є варіанти корпусів друку на 3D принтері. На плату додано один адресний діод для індикації роботи шлюзу в режимі авто або можна керувати діодом окремо задаючи свої ефекти. Також розроблене кільце з адресними діодами для встановлення замість штатної плати живлення шлюзу. У такому виконанні ще знадобиться блок живлення для підключення шлюзу до розетки.

Плата розроблялася з нуля під модулі RF-star CC2652P. Використовувалася програма EasyEDA. Повний опис зроблений після збирання та перевірки в роботі. Плата буде доступна для продажу в Україні для любителів самостійного складання.

[Процес розробки та перевірки тут](development_ukr.md)

## Принципова схема пристрою
![схема](img/SCH.png)

## Зібрана плата та роз'єм для встановлення в шлюз
<img src="img/3.jpg" style="height:450px;"> <img src="img/4.jpg" style="height:450px;">

Для використання плати окремо від шлюзу Xiaomi роз'єм запаювати не потрібно. Дістати такі роз'єми в Україні виявилося не просто, але начебто можна замовити на Алі

Для встановлення потрібно вкоротити тонель датчика світла. У мене Aqara M1S. Таке доопрацювання потрібне ще для деяких шлюзів Xiaomi. Ще видалив один маленький напрямний штир, який упирався в ESP32.
<img src="img/5.jpg" style="height:450px;">

Для любителів самостійного складання:
1. [Гербер](production/Gerber_1.0_PCB1_2023-03-31.zip) файл для замовлення основної плати
2. [BOM](production/BOM_Board1_PCB1_2023-03-31.xlsx) файл деталей 

## Розробка плати живлення замість штатної

[Процес розробки та перевірки плати живлення та світлодіодів](power_led_ukr.md)

Була розроблена плата живлення для заміни штатної плати шлюзів Xiaomi та Aqara, для того щоб встановити на неї адресні діоди на штатні місця. Тільки у штатних місцях світло діодів потрапляє на відбивач і проходить через розсіювач. Отримуємо м'яке та змащене світло. Жодних видимих крапок! Навіть якщо світиться один світлодіод – отримуємо плавний перелив світла по всьому кільцю. Далі буде відео роботи світлових ефектів.

Блок живлення 5В 2А, що був у мене, підходить із запасом. Але він вищий за вільне місце. Потрібно прорізати плату і встановлювати блок живлення крізь неї. Вийшло так.

## Зовнішній вигляд готової та зібраної плати
<img src="img/LED4.jpg" style="height:400px;"> <img src="img/LED5.jpg" style="height:400px;">

Для остаточного складання підключив БП до платного переходу за допомогою дротів. Для підключення до мережі 220 зі шматочків мідної фольги зробив дві напів трубки і одягнув на штирі живлення 220В. Припаявся проводами. Ось що вийшло.

## Встановлення плати живлення
<img src="img/LED6.jpg" style="width:600px;">
<img src="img/LED7.jpg" style="width:600px;">
<img src="img/LED8.jpg" style="width:600px;">

У зібраному вигляді не відрізняється від штатного шлюзу.

## Налаштування
![схема](img/set1.jpg) ![схема](img/set2.jpg)

З дод. платою зі світлодіодами потрібно в налаштуваннях поставити кількість діодів 18

## Зовнішній вигляд
<img src="img/vid2.jpg" style="width:600px;">
<img src="img/vid3.jpg" style="width:600px;">

## Відео роботи світла
<a href="https://youtu.be/n97AixJyFCw" target="_blank"><img src="img/vid4.jpg" style="width:600px;"></a>

---
Матеріали для вивчення (російською):
* [SLS Github](https://github.com/slsys/Gateway)
* [SLS Сообщество](https://t.me/slsys)
