---
navigation:
  title: Зберігання MEGA
  icon: item_storage_cell_256m
  parent: index.md
  position: 010
categories:
  - megacells
item_ids:
  - cell_component_1m
  - cell_component_4m
  - cell_component_16m
  - cell_component_64m
  - cell_component_256m
  - mega_item_cell_housing
  - mega_fluid_cell_housing
  - mega_chemical_cell_housing
  - mega_source_cell_housing
  - mega_mana_cell_housing
  - mega_experience_cell_housing
  - item_storage_cell_1m
  - item_storage_cell_4m
  - item_storage_cell_16m
  - item_storage_cell_64m
  - item_storage_cell_256m
  - fluid_storage_cell_1m
  - fluid_storage_cell_4m
  - fluid_storage_cell_16m
  - fluid_storage_cell_64m
  - fluid_storage_cell_256m
  - chemical_storage_cell_1m
  - chemical_storage_cell_4m
  - chemical_storage_cell_16m
  - chemical_storage_cell_64m
  - chemical_storage_cell_256m
  - source_storage_cell_1m
  - source_storage_cell_4m
  - source_storage_cell_16m
  - source_storage_cell_64m
  - source_storage_cell_256m
  - mana_storage_cell_1m
  - mana_storage_cell_4m
  - mana_storage_cell_16m
  - mana_storage_cell_64m
  - mana_storage_cell_256m
  - experience_storage_cell_1m
  - experience_storage_cell_4m
  - experience_storage_cell_16m
  - experience_storage_cell_64m
  - experience_storage_cell_256m
  - portable_item_cell_1m
  - portable_item_cell_4m
  - portable_item_cell_16m
  - portable_item_cell_64m
  - portable_item_cell_256m
  - portable_fluid_cell_1m
  - portable_fluid_cell_4m
  - portable_fluid_cell_16m
  - portable_fluid_cell_64m
  - portable_fluid_cell_256m
  - portable_chemical_cell_1m
  - portable_chemical_cell_4m
  - portable_chemical_cell_16m
  - portable_chemical_cell_64m
  - portable_chemical_cell_256m
  - portable_source_cell_1m
  - portable_source_cell_4m
  - portable_source_cell_16m
  - portable_source_cell_64m
  - portable_source_cell_256m
  - portable_mana_cell_1m
  - portable_mana_cell_4m
  - portable_mana_cell_16m
  - portable_mana_cell_64m
  - portable_mana_cell_256m
  - portable_experience_cell_1m
  - portable_experience_cell_4m
  - portable_experience_cell_16m
  - portable_experience_cell_64m
  - portable_experience_cell_256m
  - sky_bronze_ingot
  - sky_bronze_block
  - sky_osmium_ingot
  - sky_osmium_block
---

# MEGA Cells: Сховище

<GameScene zoom="8" background="transparent">
  <ImportStructure src="assets/assemblies/drive_cells.snbt" />
  <IsometricCamera yaw="195" pitch="10" />
</GameScene>

## МЕГА [комірки зберігання](ae2:items-blocks-machines/storage_cells.md)

<Row>
  <ItemImage id="mega_item_cell_housing" scale="4" />
  <ItemImage id="item_storage_cell_1m" scale="4" />
  <ItemImage id="item_storage_cell_4m" scale="4" />
  <ItemImage id="item_storage_cell_16m" scale="4" />
  <ItemImage id="item_storage_cell_64m" scale="4" />
  <ItemImage id="item_storage_cell_256m" scale="4" />
</Row>

Як згадувалося раніше, <ItemLink id="megacells:accumulation_processor" /> служить першим кроком до створення будь-якої інфраструктури MEGA, і це включає власні вищі рівні комірок зберігання. З цим процесором <ItemLink id="ae2:cell_component_256k" /> можна розширити *ще далі*, від **1М** (еквівалентно «1024К») до найвищого рівня **256М** — понад *тисячу* разів більшої місткості, ніж 256К.

<RecipeFor id="cell_component_1m" />
<RecipeFor id="cell_component_4m" />
<RecipeFor id="cell_component_16m" />
<RecipeFor id="cell_component_64m" />
<RecipeFor id="cell_component_256m" />

Звичайно, для більш потужного сховища потрібен ще потужніший корпус, і саме тут знадобиться ще трохи небесної сталі для створення корпусу комірок для ваших нових компонентів рівня М.

<Row>
  <RecipeFor id="mega_item_cell_housing" />
  <Recipe id="cells/standard/item_storage_cell_1m" />
  <Recipe id="cells/standard/item_storage_cell_1m_with_housing" />
</Row>

Для рідин та всього, що виходить за рамки цього, також існують спеціальні корпуси. Як виявилося, небесний камінь достатньо потужний, щоб сплавлятися з деякими іншими металами, такі як мідь, для виготовлення корпусів рідинних комірок з **небесної бронзи**. Навіть поза цим посібником, все, що ви можете собі уявити, може підтримуватися MEGA та виділеною коміркою з власним типом корпусу.

<Row>
  <ItemImage id="sky_bronze_ingot" scale="4" />
  <ItemImage id="mega_fluid_cell_housing" scale="4" />
  <ItemImage id="fluid_storage_cell_1m" scale="4" />
  <ItemImage id="fluid_storage_cell_4m" scale="4" />
  <ItemImage id="fluid_storage_cell_16m" scale="4" />
  <ItemImage id="fluid_storage_cell_64m" scale="4" />
  <ItemImage id="fluid_storage_cell_256m" scale="4" />
</Row>

<Row>
  <Recipe id="transform/sky_bronze_ingot" />
  <RecipeFor id="mega_fluid_cell_housing" />
</Row>

## МЕГА [Портативні комірки](ae2:items-blocks-machines/storage_cells.md#portable-item-storage)

MEGA також пропонує портативні версії всіх своїх комірок, як і сама AE2, хоча збільшена місткість цих комірок вимагатиме значно більше енергії. Таким чином, зверніть увагу, для їх створення використовується <ItemLink id="ae2:dense_energy_cell" />, а не <ItemLink id="ae2:energy_cell" /> як було б зазвичай.

Хоча ці портативні комірки також підтримують повний спектр [модифікаторів](ae2:items-blocks-machines/upgrade_cards.md), що й звичайні МЕ портативні комірки, їхня збільшена місткість батареї та загальна потреба в енергії означають, що звичайна <ItemLink id="ae2:energy_card" /> *недостатньо* потужна, щоб їх підтримувати. Для цього підійде лише <ItemLink id="megacells:greater_energy_card" />.

<Row>
  <RecipeFor id="portable_item_cell_1m" />
</Row>
