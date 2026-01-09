---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: МЕ Площина руйнування
  icon: annihilation_plane
  position: 210
categories:
- devices
item_ids:
- ae2:annihilation_plane
---

# Площина руйнування

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/blocks/annihilation_plane.snbt" />
</GameScene>

Площина руйнування розбиває блоки та підбирає предмети. Вона працює як <ItemLink id="import_bus" /> завантажуючи предмети в [мережеве сховище](../ae2-mechanics/import-export-storage.md). Щоб предмети можна було підібрати, вони повинні зіткнутися з поверхнею площини, вона не підбирає предмети в певній області.

Площину руйнування можна зачарувати будь-яким зачаруванням кайла, тому так, ви можете встановити шалені рівні Удачі та [автоматизувати обробку руди](../example-setups/ore-fortuner.md) якщо ваш модпак це дозволяє. Крім того, Шовковий дотик робить те, що ви очікуєте, Ефективність зменшує витрати енергії на розбиття блоку, а Незламність дає шанс не спожити енергію.

Площини є [кабельними компонентами](../ae2-mechanics/cable-subparts.md).

**ПЕРЕКОНАЙТЕСЯ, ЩО FAKE PLAYER УВІМКНЕНО НА ВАШІЙ ПРИВЛАСНЕНІЙ ДІЛЯНЦІ**

## Фільтрація

Площина руйнування розіб'є блок або підбере предмет лише тоді, коли зможе зберегти результат у своїй мережі. Це означає, що для фільтрації *ви повинні обмежити те, що може зберігатися в його мережі*, найімовірніше, розмістивши його в [підмережі](../ae2-mechanics/subnetworks.md). <ItemLink id="storage_bus" /> або [комірка](../items-blocks-machines/storage_cells.md) може бути [розгалужена/відфільтрована](cell_workbench.md) для досягнення цього.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/annihilation_filtering.snbt" />

  <DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        Відфільтровано до будь-чого, що випадає з предмета, який ви хочете розбити.
  </DiamondAnnotation>

  <DiamondAnnotation pos=".5 0.5 2.5" color="#00ff00">
        Розгалужено до будь-чого, що випадає з предмета, який ви хочете розбити.
  </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Знову ж таки, фільтр площини працює за *дропом предметів*, тому, наприклад, якщо ви хочете отримувати <ItemLink id="minecraft:amethyst_cluster" />, вам потрібна додаткова площина, зачарована Шовковим дотиком, інакше вона розбиватиме кожну попередню стадію зародка, оскільки технічно здатна зберегти «нічого», яке випадає з них.

## Рецепт

<RecipeFor id="annihilation_plane" />
