---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Прискорювач росту
  icon: growth_accelerator
  position: 310
categories:
- machines
item_ids:
- ae2:growth_accelerator
---

# Прискорювач росту

<BlockImage id="growth_accelerator" p:powered="true" scale="8"/>

Прискорювач росту значно прискорює [ріст](../ae2-mechanics/certus-growth.md) істинного кварцу або аметисту, якщо його розмістити поруч із родючим блоком.

Цікаво те, що він *також* може прискорити ріст різних рослин.

Він робить це, застосовуючи «випадкові такти» до блоків поряд, на додаток до випадкових тактів, які відбуваються природним чином.
Теоретично це означає, що 1 прискорювач повинен змушувати рослини рости приблизно в 90 разів швидше, ніж зазвичай, і ефект сумується.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/growth_accelerator.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Живлення може подаватись зверху або знизу, через [кабелі](cables.md) AE2 або інші модові кабелі живлення. Він може приймати живлення AE2 (AE) або енергію Forge (FE).

Щоб живити прискорювач вручну, розмістіть <ItemLink id="crank" /> зверху або знизу та прокручуйте його.

Верх і низ прискорювача можна ідентифікувати за фіолетовими флюїкосвими кільцями.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/accelerator_connections.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Рецепт

<RecipeFor id="growth_accelerator" />
