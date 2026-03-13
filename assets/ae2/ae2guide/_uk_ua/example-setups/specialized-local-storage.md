---
navigation:
  parent: example-setups/example-setups-index.md
  title: Спеціалізоване локальне сховище
  icon: drive
---

# Спеціалізоване локальне сховище

Використовуючи одну зі [спеціальних поведінок інтерфейсу](../items-blocks-machines/interface.md#особливі-взаємодії), [підмережа](../ae2-mechanics/subnetworks.md) може представляти вміст свого сховища основній мережі, не маючи змоги бачити сховище основної мережі та займаючи лише 1 [канал](../ae2-mechanics/channels.md).

Це корисно для локального сховища на деякій фермі, щоб ресурси не переповнювали ваше основне сховище.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/local_storage.snbt" />

<BoxAnnotation color="#dddddd" min="4 0 0" max="5 2 1">
        (1) Деякий метод імпорту предметів (у цьому випадку інтерфейс)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 0 0" max="4 1 1">
        (2) Привід: Містить кілька комірок. Комірки слід розгалузити за усіма вихідними ресурсами ферми. Комірки можуть мати Картки рівного розподілу та Картки знищення переповнення.
        <Row><ItemImage id="item_storage_cell_4k" scale="2" /> <ItemImage id="equal_distribution_card" scale="2" /> <ItemImage id="void_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1 0" max="4 2 0.3">
        (3) Термінал майстрування: Він може бачити вміст привода в підмережі, але не вміст сховища вашої основної мережі.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (4) Інтерфейс №2: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 0" max="2 1 1">
        (5) Шина сховища: Має пріоритет, встановлений вище, ніж в основного сховища, може бути відфільтрована до будь-яких виходів ферми.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 2 0.3">
        Термінал майстрування: Він може бачити як вміст сховища основної мережі *та* підмережі.
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

* Перший <ItemLink id="interface" /> (1) просто приймає ресурси з будь-якої вашої ферми та завантажує їх у підмережу.
* <ItemLink id="drive" /> (2) містить деякі [комірки](../items-blocks-machines/storage_cells.md). Комірки повинні бути [розгалужені](../items-blocks-machines/cell_workbench.md) за усіма вихідними ресурсами ферми. Комірки можуть мати <ItemLink id="equal_distribution_card" /> та <ItemLink id="void_card" />.
* Другий <ItemLink id="interface" /> (4) стоїть без змін.
* <ItemLink id="storage_bus" /> має [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) вищий, ніж основне сховище. Його можна фільтрувати за будь-якими ресурсами ферми.

## Як це працює

* <ItemLink id="interface" /> підмережі показує <ItemLink id="storage_bus" /> з основної мережі вміст <ItemLink id="drive" />. Це означає, що шина зберігання може безпосередньо витягувати речі з комірок привода та передавати їх до них.
* Шина сховища має високий [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) щоб речі переважно поверталися назад у підмережу, а не в основне сховище.
* Важливо, що якщо комірки в підмережі заповнюються, речі не переповняться в основну мережу. Якщо ферма має тип, який виходить з ладу при переповненні, для видалення зайвих речей можна використовувати <ItemLink id="void_card" />. 
* Якщо ферма виводить кілька ресурсів, <ItemLink id="equal_distribution_card" /> може запобігти заповненню всіх комірок одним предметом і не дозволити іншим ресурсам переповнити комірку.