---
navigation:
  parent: example-setups/example-setups-index.md
  title: Інтерфейсне автозапасання
  icon: interface
---

# Інтерфейсне автозапасання

Хтось може запитати: «Як мені зберігати певну кількість різних предметів про запас, виготовляючи більше за потреби?»

Одним із рішень є поєднання <ItemLink id="interface" /> та <ItemLink id="crafting_card" /> для автоматичного запиту нових предметів з вашої системи [автовироблення](../ae2-mechanics/autocrafting.md) вашої мережі. Ця схема більше підходить для підтримки невеликої кількості широкого спектра предметів.

Ця демонстраційна схема скорочена, щоб не бути надто широкою. Ймовірно, оптимальніше використовувати 4 <ItemLink id="interface" /> та 4 <ItemLink id="storage_bus" />, щоб використовувати всі 8 [каналів](../ae2-mechanics/channels.md) у звичайному [кабелі](../items-blocks-machines/cables.md).

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_autostocking.snbt" />

<BoxAnnotation color="#dddddd" min="0 0 0" max="2 1 1">
        (1) Інтерфейси: Налаштовано так, щоб потрібні предмети залишалися всередині. Вони мають картки вироблення.
        <ItemImage id="crafting_card" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="2 1.3 1">
        (2) Шини зберігання: «Режим логістики» встановлено на «вихідний».
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

* <ItemLink id="interface" /> (1) налаштовані на збереження потрібних предметів, що робиться клацанням потрібного предмета у верхні слоти або перетягуванням їхні у верхні слоти з JEI. Над налаштованими предметами з'являється кнопка налаштування, де можна точно вказати їхню кількість. Вони також мають <ItemLink id="crafting_card" />.
* <ItemLink id="storage_bus" /> налаштовані таким чином, що «режим логістики» встановлено на «вихідний».

## Як це працює

1. Якщо <ItemLink id="interface" /> не може отримати достатню кількість налаштованого предмета з [мережевого сховища](../ae2-mechanics/import-export-storage.md), (і він має <ItemLink id="crafting_card" />), він зробить запит до системи [автовироблення](../ae2-mechanics/autocrafting.md) цієї мережі для отримання достатньої кількості предмета.
2. <ItemLink id="storage_bus" /> дозволяють мережі отримувати доступ до вмісту інтерфейсів.