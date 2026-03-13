---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Просторові комірки
  icon: spatial_storage_cell_128
  position: 410
categories:
- tools
item_ids:
- ae2:spatial_storage_cell_2
- ae2:spatial_storage_cell_16
- ae2:spatial_storage_cell_128
- ae2:spatial_cell_component_2
- ae2:spatial_cell_component_16
- ae2:spatial_cell_component_128
---

# Просторові комірки

  <Row>
    <ItemImage id="spatial_storage_cell_2" scale="4" />

    <ItemImage id="spatial_storage_cell_16" scale="4" />

    <ItemImage id="spatial_storage_cell_128" scale="4" />
  </Row>

Просторові комірки використовуються для [зберігання фізичних об'ємів простору](../ae2-mechanics/spatial-io.md). Вони використовуються в <a href="spatial_io_port.md"> порті просторового зберігання</a>.

На відміну від [комірок зберіганняls](../items-blocks-machines/storage_cells.md), просторові комірки не можна переформатувати.

Знову ж таки, **ВИ НЕ МОЖЕТЕ СКИНУТИ, ПЕРЕФОРМАТУВАТИ АБО ЗМІНИТИ РОЗМІР ПРОСТОРОВОЇ КОМІРКИ ПІСЛЯ ЇЇ ВИКОРИСТАННЯ.** Створіть нову комірку, якщо хочете використовувати інші розміри.


## Рецепти

  <Row>
    <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_16_cubed_storage" />

    <Recipe id="network/cells/spatial_storage_cell_128_cubed_storage" />
  </Row>

# Корпуси

Комірки можна створювати з просторовим компонентом та корпусом або з рецептом корпусу навколо просторового компонента:

<Row>
  <Recipe id="network/cells/spatial_storage_cell_2_cubed" />

  <Recipe id="network/cells/spatial_storage_cell_2_cubed_storage" />
</Row>

Самі корпуси створюються так:

  <RecipeFor id="item_cell_housing" />

# Просторові компоненти

Просторові компоненти є ядром комірок простору. Кожен рівень у 8 разів збільшує обсяги об'єму, який можна зберегти.

  <Row>
    <RecipeFor id="spatial_cell_component_2" />

    <RecipeFor id="spatial_cell_component_16" />

    <RecipeFor id="spatial_cell_component_128" />
  </Row>