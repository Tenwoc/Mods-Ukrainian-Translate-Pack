---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Шина перемикання
  icon: toggle_bus
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:toggle_bus
- ae2:inverted_toggle_bus
---

# Шина перемикання

<GameScene zoom="8" background="transparent">
<ImportStructure src="../assets/assemblies/toggle_bus.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

Шина, яка функціонує як <ItemLink id="fluix_glass_cable" /> чи інші кабелі, але дозволяє перемикати стан її з'єднання редстоуновим сигналом. Це дозволяє відрізати ділянки [МЕ мережі](../ae2-mechanics/me-network-connections.md).

Коли подається сигнал редстоуну, компонент дозволяє з'єднання, а <ItemLink id="inverted_toggle_bus" /> забезпечує зворотну поведінку, вимикаючи з'єднання.

Зверніть увагу, що перемикання цих компонентів може призвести до перевантаження мережі та перерахунку підключених пристроїв.

Ці прилади є [кабельними компонентами](../ae2-mechanics/cable-subparts.md).

## Рецепти

<RecipeFor id="toggle_bus" />

<RecipeFor id="inverted_toggle_bus" />
