---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Канали
  icon: controller
---

# Канали

[МЕ мережі](me-network-connections.md) в Applied Energistics 2 потребують каналів для підтримки [пристроїв](../ae2-mechanics/devices.md), які використовують мережеве сховище або інші мережеві служби. Уявіть собі канали як USB-кабелі для всіх ваших пристроїв. Комп'ютер має обмежену кількість USB-портів і може підтримувати лише певну кількість підключених до нього пристроїв. Більшість машин, пристроїв з повним блоком і стандартних кабелів можуть пропускати тільки до 8 каналів. Ви можете уявити собі пристрої з повним блоком і стандартні кабелі як пучок з 8 «канальних дротів». Однак [щільні кабелі](../items-blocks-machines/cables.md#щільний-кабель) можуть підтримувати до 32 каналів. Єдині інші пристрої, здатні передавати 32 канали, — це <ItemLink id="me_p2p_tunnel" /> та [квантовий мережевий міст](../items-blocks-machines/quantum_bridge.md). Кожного разу, коли пристрій використовує канал, уявіть, що ви витягуєте USB-«провід» із пучка, що, очевидно, означає, що «провід» більше не доступний далі по лінії.

<GameScene zoom="7" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_demonstration_1.snbt" />

  <LineAnnotation color="#33ff33" from="1 .4 .7" to="2.4 .4 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .7" to="2.4 .6 .7" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .6" to="2.6 .4 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .6 .6" to="2.6 .6 .6" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.4 .6 .7" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .4 .7" to="2.4 .4 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .6 .6" to="2.6 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 .6" to="2.6 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.1 .6 1.5" to="2.4 .6 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.6 .4 1.5" to="2.9 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="2.6 .6 1.5" to="2.6 .9 1.5" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="2.4 .1 1.5" to="2.4 .4 1.5" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .4" to="3.5 .6 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="3.5 .6 .4" to="3.5 .9 .4" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="3.5 .1 .4" to="3.5 .4 .4" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1 .6 .3" to="1.5 .6 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1 .4 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#33ff33" from="1.5 .6 .3" to="1.5 .9 .3" alwaysOnTop={true}/>
  <LineAnnotation color="#33ff33" from="1.5 .1 .3" to="1.5 .4 .3" alwaysOnTop={true}/>

  <LineAnnotation color="#ff3333" from="3.5 .5 .5" to="5.5 .5 .5" alwaysOnTop={true}>
  Всі 8 каналів у кабелі вже використовуються, тому привід не отримує жодного.  
  </LineAnnotation>

  <LineAnnotation color="#993333" from="1 .5 .5" to="1.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="1.5 .5 .5" to="1.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2 .5 .5" to="2.25 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="2.5 .5 .5" to="2.75 .5 .5" alwaysOnTop={true}/>
  <LineAnnotation color="#993333" from="3 .5 .5" to="3.25 .5 .5" alwaysOnTop={true}/>

  <DiamondAnnotation pos="3.6 0.5 0.5" color="#ff0000">
        Всі 8 каналів у кабелі вже використовуються, тому привід не отримує жодного.
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

Простий спосіб побачити, як канали використовуються і проходять через вашу мережу — це використовувати [розумні кабелі](../items-blocks-machines/cables.md), які відображають на собі шляхи та використання каналів.

Канали споживають 1⁄128 ae/т на кожен вузол, який вони перетинають, це означає, що додавши <ItemLink id="controller" /> для мережі з 8 пристроями й понад 96 вузлами, ваше енергоспоживання може фактично зменшитися, оскільки це змінює спосіб розподілу каналів.

Слід зазначити, що **КАНАЛИ НЕ МАЮТЬ НІЯКОГО ВІДНОШЕННЯ ДО КОЛЬОРУ КАБЕЛІВ**, колір кабелів лише обмежує їх з'єднання.

## Маршрутизація каналів

Коли використовується <ItemLink id="controller" />, канали проходять 3 етапи. Спочатку вони проходять найкоротшим шляхом через сусідні машини до найближчого [звичайного кабелю](../items-blocks-machines/cables.md) (скляного, огорнутого, або розумного). Потім вони проходять найкоротшим шляхом через цей звичайний кабель до найближчого [щільного кабелю](../items-blocks-machines/cables.md) (щільного, або розумного щільного). Потім вони проходять найкоротшим шляхом через цей щільний кабель у <ItemLink id="controller" />. Якщо найкоротший шлях вже вичерпаний, деякі [пристрої](devices.md) можуть не отримати необхідні канали. Використовуйте кольорові кабелі, кабельні анкери та тунелі на свою користь, щоб переконатися, що ваші канали проходять по бажаному шляху.

Наприклад, у цьому випадку деякі приводи не отримують каналів, оскільки, хоча в кабелях є достатня пропускна здатність, канали намагаються пройти найкоротшим шляхом, перевантажуючи деякі кабелі, а інші залишаючи порожніми.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 3.6" to="1.4 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.4 0.5 3.6" to="1.4 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 1.6" to="0.6 .5 1.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 1.6" to="0.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#ff3333" from="0.6 .5 3.4" to="1.4 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#ff3333" from="3 .5 3.4" to="1.6 .5 3.4" alwaysOnTop={true} thickness="0.05"/>

  <BoxAnnotation color="#dddddd" min="1.2 0.2 3.2" max="1.8 0.8 3.8" alwaysOnTop={true} thickness="0.05">
        Більше 8 каналів намагаються пройти тут, тому деякі з них відрізані.
  </BoxAnnotation>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

Це можна виправити, більш ретельно обмежуючи шляхи, якими можуть рухатися канали. Мережі повинні бути деревоподібними.
Петлі та неоднозначні шляхи каналів повинні бути мінімізовані.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/channel_path_length_issue_fix.snbt" />

  <LineAnnotation color="#33ff33" from="3 .5 1.4" to="0.4 0.5 1.4" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 .5 1.4" to="0.4 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="0.4 0.5 5.6" to="1 0.5 5.6" alwaysOnTop={true} thickness="0.05"/>

  <LineAnnotation color="#33ff33" from="3 0.5 3.6" to="1.6 0.5 3.6" alwaysOnTop={true} thickness="0.05"/>
  <LineAnnotation color="#33ff33" from="1.6 0.5 3.6" to="1.6 0.5 5" alwaysOnTop={true} thickness="0.05"/>

  <IsometricCamera yaw="90" pitch="90" />

</GameScene>

## Автономні мережі

Мережа, що не використовує <ItemLink id="controller" />, вважається автономною і може підтримувати до 8 каналів, що використовують пристрої. Якщо кількість пристроїв перевищить 8, канали мережі, що використовують пристрої, будуть вимкнені. Ви можете або видалити пристрої, або все ж додати <ItemLink id="controller" />.

На відміну від *контролерних* мереж, [розумні кабелі](../items-blocks-machines/cables.md) в автономних мережах показують кількість каналів, що використовуються в мережі, а не кількість каналів, що проходять через конкретний кабель.

Під час використання автономних мереж кожен пристрій використовуватиме 1 канал у всій мережі, що значно відрізняється від того, як <ItemLink id="controller" /> розподіляє канали на основі найкоротшого шляху.

## Дизайн

Як уже згадувалося раніше в розділі [Маршрутизація каналів](channels.md#маршрутизація-каналів), найкраще проєктувати мережу у вигляді деревоподібної структури, з щільними кабелями, що відгалужуються від контролера, звичайними кабелями, що відгалужуються від щільних, і [пристроями](../ae2-mechanics/devices.md) у кластерах по 8 або менше на звичайних кабелях.

Ось приклад того, чого не слід робити:

Слідуючи шляхам каналів:

1. Відразу виходячи з контролера праворуч, ми стикаємося з вузьким місцем у 8 каналів, оскільки привід діє як звичайний кабель.
Однак, оскільки ми не використовуємо тут розумний кабель, ми не можемо побачити, скільки каналів використовується. Залишається 8 каналів.
1. Привід займає один канал.
Залишається 7 каналів.
1. 2 канали йдуть до терміналів.
Залишається 5 каналів.
1. Продовжуючи праворуч, інтерфейс займає ще один канал.
Залишається 4 канали.
1. 1 канал йде до постачальника шаблонів.
Залишається 3 канали.
1. Продовжуючи праворуч, 1 канал підключається до шини імпорту.
Залишається 2 канали.
1. Кластер постачальників шаблонів, що живлять збирачі, отримує лише 2 канали, тому інші 2 постачальники не отримують каналів.

Зрештою, помилка полягає в створенні вузького місця в каналах і в тому, що не продумано, як будуть розподілятися канали.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/bad_network_structure.snbt" />

<LineAnnotation color="#33ff33" from="6.5 .5 1.5" to="6 .5 1.5" alwaysOnTop={true} thickness="0.4">
  32 канали
</LineAnnotation>

<LineAnnotation color="#33ff33" from="6 .5 1.5" to="5.5 .5 1.5" alwaysOnTop={true} thickness="0.2">
  8 каналів
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 1.5 1.5" alwaysOnTop={true} thickness="0.1">
  2 канали
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="5.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 1.5 1.5" to="5.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 2.5 1.5" to="5.5 2.5 1.1" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="5.5 .5 1.5" to="4.5 .5 1.5" alwaysOnTop={true} thickness="0.158">
  5 каналів
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 .3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="4.5 1.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="4.5 .5 1.5" to="3.5 .5 1.5" alwaysOnTop={true} thickness="0.122">
  3 канали
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="3.5 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 2.5 1.5" to="3.7 2.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="3.5 .5 1.5" to="1.5 .5 1.5" alwaysOnTop={true} thickness="0.1">
  2 канали
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="1.5 0.3 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="1.5 0.5 1.5" to="0.5 0.5 1.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#33ff33" from="0.5 0.5 1.5" to="0.5 0.5 0.5" alwaysOnTop={true} thickness="0.071">
  1 канал
</LineAnnotation>

<LineAnnotation color="#ff3333" from="0.5 1.5 1.5" to="0.5 1.3 1.5" alwaysOnTop={true} thickness="0.071">
  нестача каналів
</LineAnnotation>

<LineAnnotation color="#ff3333" from="1.5 1.5 0.5" to="1.5 1.3 0.5" alwaysOnTop={true} thickness="0.071">
  нестача каналів
</LineAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

---

Ось приклад хорошої структури:

<GameScene zoom="2.5" interactive={true}>
  <ImportStructure src="../assets/assemblies/treelike_network_structure.snbt" />

    <BoxAnnotation color="#dddddd" min="6.9 0 4.9" max="9.1 4 7.1" thickness="0.05">
        Зверніть увагу, що постачальники шаблонів розділені на окремі групи по 8 приладів.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 4 4" max="8 5 5" thickness="0.05">
        Чотири заповнені каналами звичайні кабелі йдуть разом, що значить, що вам потрібен щільний кабель.
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="5 0 13" max="8 1 14" thickness="0.05">
        Для запобігання з'єднанню сусідніх кабелів використовуються кабелі різних кольорів.
    </BoxAnnotation>


  <IsometricCamera yaw="315" pitch="30" />
</GameScene>

## Режими каналів

Для Minecraft з версії 1.18 AE2 10.0.0+ представляє нові опції для зміни поведінки каналів AE2 у вашому світі. У загальному розділі конфігурацій з'явилася нова опція (`channels`), яка контролює поведінку каналів, а також нова ігрова команда для операторів, що дозволяє змінювати режим і конфігурацію зсередини гри. Команда `/ae2 channelmode <mode>` дозволяє змінити режим, а `/ae2 channelmode` — показати поточний. Коли режим змінюється в грі, всі наявні мережі перезавантажуються і відразу починають використовувати новий режим.

Це відновлює та покращує опцію, яка була доступна в Minecraft 1.12, і пропонує кращі опції для гравців, які просто хочуть трохи більш спокійного ігрового процесу, але не хочуть, щоб механіку було повністю видалено.


У наступній таблиці перелічено доступні режими як у файлі конфігурації, так і в команді.

| Налаштування    | Опис                                                                                                                                                                                                                               |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `default`  | Стандартний режим з пропускною здатністю каналів кабельних і автономних мереж, як описано на цій сторінці                                                                                                                           |
| `x2`       | Всі пропускні здатності каналів подвоєні (16 на звичайному кабелі, 64 на щільному кабелі, автономні мережі підтримують 16 каналів)                                                                                                                           |
| `x3`       | Всі пропускні здатності каналів потроєні (24 на звичайному кабелі, 92 на щільному кабелі, автономні мережі підтримують 24 канали)                                                                                                                           |
| `x4`       | Всі пропускні здатності каналів збільшені в чотири рази (32 на звичайному кабелі, 128 на щільному кабелі, автономні мережі підтримують 32 канали)                                                                                                                       |
| `infinite` | Всі обмеження каналів зняті. Контролери все ще *значно* зменшують енергоспоживання мереж. Розумні кабелі будуть перемикатися тільки між повністю вимкненим станом (канали не передаються) і повністю увімкненим станом (передається 1 або більше каналів). |