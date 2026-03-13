---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизація процесорів
  icon: logic_processor
---

# Автоматизація вироблення процесорів

Існує багато способів автоматизації [процесорів](../items-blocks-machines/processors.md), і це один з них.

Цю схему можна реалізувати з будь-яким типом труб, провідників чи вузлів або як там це називається в моді, який ви збираєтесь використовувати.

![The Process FLow Diagram](../assets/diagrams/processor_flow_diagram.png)

Тут детально описано, як це зробити лише за допомогою AE2, використовуючи [трубні підмережі](pipe-subnet.md).

Зверніть увагу, що оскільки тут використовується <ItemLink id="pattern_provider" />, він призначений для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md). Якщо ви просто хочете автоматизувати процесори окремо, замініть постачальника шаблонів іншою діжкою та безпосередньо поміщайте інгредієнти у верхню діжку.

Це забезпечує зворотну сумісність з попередніми версіями AE2, оскільки навіть якщо <ItemLink id="inscriber" /> стоїть у суворому режимі сторін, трубні підмережі все одно рухають предмети з правильних граней.

## Урок кодування шаблонів

Часто [шаблон](../items-blocks-machines/patterns.md) який потрібно закодувати, **НЕ ВІДПОВІДАТИМЕ ТОМУ, ЩО ВИ БАЧИТЕ В JEI**, або тому, що JEI виводить, коли ви натискаєте кнопку +. У цьому випадку JEI виводить 2 окремі шаблони, по одному для друкованих схем і по одному для готових процесорів, і шаблон друкованих схем включатиме [штамп](../items-blocks-machines/presses.md). Це не те що нам потрібно, тому що це не те що робитиме наша схема. Нам потрібен 1 шаблон, який вводить необроблені ресурси та виводить завершений процесор, і оскільки штампи вже знаходиться в пресах, нам не слід розміщувати їх у шаблоні.

---

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/processor_automation.snbt" />

  <BoxAnnotation color="#dddddd" min="5 1 0" max="6 2 1" thickness=".05">
        (1) Pattern Provider: Без налаштувань, з відповідними шаблонами обробки.

        <Row>
            ![Logic Pattern](../assets/diagrams/logic_pattern_small.png)
            ![Calculation Pattern](../assets/diagrams/calculation_pattern_small.png)
            ![Engineering Pattern](../assets/diagrams/engineering_pattern_small.png)
        </Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4.7 2 0" max="5 3 1" thickness=".05">
        (2) Шина зберігання №1: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 0" max="4.3 2 1" thickness=".05">
        (3) Шина експорту №1: Відфільтрована на кремній, має 2 картки прискорення
        <Row><ItemImage id="silicon" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 4 0" max="4.3 3 1" thickness=".05">
        (4) Шина експорту №2: Відфільтрована на золотий злиток, має 2 картки прискорення
        <Row><ItemImage id="minecraft:gold_ingot" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 5 0" max="4.3 4 1" thickness=".05">
        (5) Шина експорту №3: ​​Відфільтрована на кристал істинного кварцу, має 2 картки прискорення
        <Row><ItemImage id="certus_quartz_crystal" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 6 0" max="4.3 5 1" thickness=".05">
        (6) Шина експорту №4: Відфільтрована на діамант, має 2 картки прискорення
        <Row><ItemImage id="minecraft:diamond" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 3 0" max="2 2 1" thickness=".05">
        (7) Шина експорту №5: Відфільтрована на редстоуновий пил, має 2 картки прискорення
        <Row><ItemImage id="minecraft:redstone" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 1 0" max="3 2 1" thickness=".05">
        (8) Штампувальний прес №1: Без налаштувань. Має кремнієвий штамп та 4 картки прискорення
        <Row><ItemImage id="silicon_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 3 0" max="3 4 1" thickness=".05">
        (9) Штампувальний прес №2: Без налаштувань. Має логічний штамп та 4 картки прискорення
        <Row><ItemImage id="logic_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 4 0" max="3 5 1" thickness=".05">
        (10) Штампувальний прес №3: Без налаштувань. Має обчислювальний штамп та 4 картки прискорення
        <Row><ItemImage id="calculation_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4 5 0" max="3 6 1" thickness=".05">
        (11) Штампувальний прес №4: Без налаштувань. Маєn інженерний штамп та 4 картки прискорення
        <Row><ItemImage id="engineering_processor_press" scale="2" /> <ItemImage id="speed_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 2 0" max="1 3 1" thickness=".05">
        (12) Штампувальний прес №5: Без налаштувань. Has 4 Acceleration Cards
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 2 0" max="3 1 1" thickness=".05">
        (13) Шина імпорту №1: Без налаштувань, має 2 картки прискорення
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 4 0" max="3 3 1" thickness=".05">
        (14) Шина імпорту №2: Без налаштувань, має 2 картки прискорення
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 5 0" max="3 4 1" thickness=".05">
        (15) Шина імпорту №3: Без налаштувань, має 2 картки прискорення
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 6 0" max="3 5 1" thickness=".05">
        (16) Шина імпорту №4: Без налаштувань, має 2 картки прискорення
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 3 0" max="1 3.3 1" thickness=".05">
        (17) Шина зберігання №2: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1.7 0" max="1 2 1" thickness=".05">
        (18) Шина зберігання №3: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 2 0" max="0.7 3 1" thickness=".05">
        (19) Шина імпорту №5: Без налаштувань, має 2 картки прискорення
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="5 0.7 0" max="6 1 1" thickness=".05">
        (20) Шина зберігання №4: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.3 2.7 0.3" max="3.7 3 0.7" thickness=".05">
        Кварцове волокно живить усі 3 преси, оскільки преси діють як кабелі та таким чином передають енергію далі
  </BoxAnnotation>

<DiamondAnnotation pos="7 1.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="185" pitch="5" />
</GameScene>

## Конфігурації

* <ItemLink id="pattern_provider" /> (1) не має налаштувань, але містить необхідні <ItemLink id="processing_pattern" />. Зверніть увагу, що шаблони закодовані на отримання процесорів безпосередньо від початкових ресурсів та **НЕ** включають [штампи](../items-blocks-machines/presses.md).

  ![Logic Pattern](../assets/diagrams/logic_pattern.png)
  ![Calculation Pattern](../assets/diagrams/calculation_pattern.png)
  ![Engineering Pattern](../assets/diagrams/engineering_pattern.png)

* <ItemLink id="storage_bus" /> (2, 17, 18, 20) не мають налаштувань.
* <ItemLink id="export_bus" /> (3-7) фільтруються за відповідним складником. Вони мають по 2 <ItemLink id="speed_card" />.
    <Row>
      <ItemImage id="silicon" scale="2" />
      <ItemImage id="minecraft:gold_ingot" scale="2" />
      <ItemImage id="certus_quartz_crystal" scale="2" />
      <ItemImage id="minecraft:diamond" scale="2" />
      <ItemImage id="minecraft:redstone" scale="2" />
    </Row>
* <ItemLink id="import_bus" /> (13-16, 19) не мають налаштувань. Вони мають по 2 <ItemLink id="speed_card" />.
* <ItemLink id="inscriber" /> не мають налаштувань. Вони мають по відповідному [штампу](../items-blocks-machines/presses.md), та по 4 <ItemLink id="speed_card" />.
   <Row>
     <ItemImage id="silicon_press" scale="2" />
     <ItemImage id="logic_processor_press" scale="2" />
     <ItemImage id="calculation_processor_press" scale="2" />
     <ItemImage id="engineering_processor_press" scale="2" />
   </Row>

## Як це працює

1. <ItemLink id="pattern_provider" /> переміщує складники в діжку.
2. Перша [трубна підмережа](pipe-subnet.md) (помаранчева) витягує кремній, редстоуновий пил та відповідний складник процесора (золотий злиток, кристал істинного кварцу або діамант) з діжки та поміщає їх у відповідний <ItemLink id="inscriber" />.
3. Перші чотири <ItemLink id="inscriber" /> штапмують <ItemLink id="printed_silicon" />, та <ItemLink id="printed_logic_processor" />, <ItemLink id="printed_calculation_processor" />, чи <ItemLink id="printed_engineering_processor" />.
4. Друга та третя [трубні підмережі](pipe-subnet.md) (зелені) витягують друковані схеми з перших чотирьох <ItemLink id="inscriber" /> та поміщають їх у п'ятий <ItemLink id="inscriber" /> для завершувального збирання.
5. П'ятий <ItemLink id="inscriber" /> збирає [процесор](../items-blocks-machines/processors.md).
6. Четверта [трубна підмережа](pipe-subnet.md) (фіолетова) поміщає процесор у постачальника шаблонів, тим самим повертаючи його до основної мережі.