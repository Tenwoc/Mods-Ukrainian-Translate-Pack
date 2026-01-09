---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Зарядний пристрій
  icon: charger
  position: 310
categories:
- machines
item_ids:
- ae2:charger
---

# Зарядний пристрій

<BlockImage id="charger" scale="8" />

Зарядний пристрій є засобом для заряджання предметів із внутрішньою енергетичною місткістю, та щоб перетворювати <ItemLink id="certus_quartz_crystal" /> на заряджений.

Живлення може подаватись зверху або знизу, через [кабелі](cables.md) AE2 або інших модів. Він може приймати живлення AE2 (AE) або енергію Forge (FE). Предмети можна вставляти або виймати з будь-якого боку. Видаляти можна лише результати, тому немає потреби у фільтрах для запобігання видаленню складника замість результата. Можна обертати, використовуючи <ItemLink id="certus_quartz_wrench" />, для полегшення автоматизації.

Може використовуватися, щоб створювати <ItemLink id="charged_certus_quartz_crystal" /> використовуючи <ItemLink id="certus_quartz_crystal" />, та <ItemLink id="meteorite_compass" /> використовуючи <ItemLink id="minecraft:compass" />.

Щоб живити його вручну, помістіть <ItemLink id="crank" /> зверху або знизу та клацайте ПКМ, доки предмет не зарядиться.

Він також служить робочою станцією для [дослідника флюїкса](fluix_researcher.md).

## Проста автоматизація

Як приклад, можливість обертання дозволяє напівавтоматизувати зарядні пристрої ось так:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/charger_hopper.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Рецепт

<RecipeFor id="charger" />
