---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Фасади
  icon: facade
  icon_components:
    "ae2:facade_item": "minecraft:stone"
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:facade
---

# Фасади

Фасади можна використовувати, щоб зробити вашу базу більш акуратною. Вони можуть приховувати кабелі обох розмірів і створюються з багатьох видів блоків.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/facades_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Вони можуть покривати всі сторони кабелю, але не перекриватимуть [кабельні компоненти](../ae2-mechanics/cable-subparts.md) та з'єднання.

<GameScene zoom="6"  interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Використовуйте їх розумно, щоб покращити естетику вашої бази, або створюйте блоки з різними текстурами з кожного боку.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/facades_3.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Приховування фасадів

Фасади будуть приховані, якщо тримати в будь-якій руці <a href="network_tool.md">мережевий інструмент</a>.

Так ви можете взаємодіяти з блоками за прихованими фасадами, не видаляючи їх.

## Рецепт

Помістіть блок, текстуру якого ви хочете отримати, посередині 4 <a href="cable_anchor.md">кабельних анкерів</a>.

![Рецепт фасаду](../assets/diagrams/facade_recipe.png)
