---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Приймач енергії
  icon: energy_acceptor
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_acceptor
---

# Приймач енергії

<Row gap="20">
<BlockImage id="energy_acceptor" scale="8" /> 

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/cable_energy_acceptor.snbt" />
</GameScene>
</Row>

Приймач енергії перетворює поширені форми енергії з інших технічних модів у внутрішню форму AE2, [енергію](../ae2-mechanics/energy.md) AE. Хоча <ItemLink id="controller" /> також може це робити, грані контролера є цінними, тому часто краще використовувати приймач енергії.

Коефіцієнти для перетворення енергії Forge та Techreborn такі:

*   2 FE = 1 AE (Forge)
*   1 E  = 2 AE (Fabric)

Швидкість перетворення повністю залежить від того, скільки AE може зберігати ваша мережа, з причин, які пояснюються на [цій сторінці](../ae2-mechanics/energy.md).

## Варіанти

Приймачі енергії бувають 2 різних варіантів: звичайний та плаский/[кабельний](../ae2-mechanics/cable-subparts.md). Це дозволяє зробити деякі установки компактнішими.

Приймачі енергії можна перемикати між звичайним та пласким у сітці майстрування.

## Рецепт

<RecipeFor id="energy_acceptor" />

<RecipeFor id="cable_energy_acceptor" />