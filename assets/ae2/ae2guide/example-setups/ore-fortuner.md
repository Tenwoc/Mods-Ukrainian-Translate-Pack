---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматичний обробник руди удачею
  icon: minecraft:raw_iron
---

# Автоматизація передобування руди удачею

<ItemLink id="annihilation_plane" /> можна зачарувати будь-яким зачаруванням кайла, включаючи чари Удачі, тому <ItemLink id="formation_plane" /> можна налаштувати на розміщення руд та зачаровану <ItemLink id="annihilation_plane" /> на їх швидке розбиття.

Зверніть увагу, що оскільки <ItemLink id="import_bus" /> «набирає обороти», обробка почнеться повільно, а потім досягне повної швидкості за кілька секунд.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 0 2" max="3 1 3">
      (1) Шина імпорту: Містить кілька карт прискорення.
        <ItemImage id="speed_card" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 2" max="2 1 2.3">
        (2) Площини формування: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 0.7" max="2 1 1">
        (3) Площини руйнування: Не мають інтерфейсу для налаштування, але зачаровані Удачею.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 0" max="3 1 1">
        (4) Шина зберігання: Без налаштувань.
  </BoxAnnotation>

<DiamondAnnotation pos="3.5 0.5 2.5" color="#00ff00">
        Вхід
    </DiamondAnnotation>

<DiamondAnnotation pos="3.5 0.5 0.5" color="#00ff00">
        Вихід
    </DiamondAnnotation>

<DiamondAnnotation pos="4 0.5 1.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

- <ItemLink id="import_bus" /> (1) містить кілька <ItemLink id="speed_card" />. Чим більше площин формування в масиві, тим більше їх потрібно, оскільки вони змушують шину імпорту витягувати більше предметів одночасно.
- <ItemLink id="formation_plane" />s (2) без налаштувань.
- <ItemLink id="annihilation_plane" /> (3) не мають інтерфейсу та не можуть бути налаштовані, але зачаровані Удачею.
- <ItemLink id="storage_bus" /> (4) без налаштувань.

## Як це працює

1.  <ItemLink id="import_bus" /> у зеленій підмережі імпортує блоки з першої діжки в [мережеве сховище](../ae2-mechanics/import-export-storage.md)
2.  Єдиним сховищем у зеленій підмережі є <ItemLink id="formation_plane" />, яка розміщуює блоки.
3.  <ItemLink id="annihilation_plane" /> у помаранчевій підмережі розбиває блоки, застосовуючи до них Удачу.
4.  <ItemLink id="storage_bus" /> у помаранчевій підмережі зберігає результати розбиття у другій діжці.
