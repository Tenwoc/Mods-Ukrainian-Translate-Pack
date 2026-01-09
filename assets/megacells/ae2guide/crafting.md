---
navigation:
  title: Автовироблення MEGA
  icon: 256m_crafting_storage
  parent: index.md
  position: 020
categories:
  - megacells
item_ids:
  - mega_crafting_unit
  - 1m_crafting_storage
  - 4m_crafting_storage
  - 16m_crafting_storage
  - 64m_crafting_storage
  - 256m_crafting_storage
  - mega_crafting_accelerator
  - mega_crafting_monitor
  - mega_pattern_provider
  - cable_mega_pattern_provider
---

# MEGA Cells: Автовироблення

<GameScene zoom="6" background="transparent">
  <ImportStructure src="assets/assemblies/crafting_cpu.snbt" />
  <IsometricCamera yaw="195" pitch="10" />
</GameScene>

## МЕГА [Процесори обробки](ae2:items-blocks-machines/crafting_cpu_multiblock.md)

<Row>
  <BlockImage id="mega_crafting_unit" scale="4" />
  <BlockImage id="1m_crafting_storage" scale="4" />
  <BlockImage id="4m_crafting_storage" scale="4" />
  <BlockImage id="16m_crafting_storage" scale="4" />
  <BlockImage id="64m_crafting_storage" scale="4" />
  <BlockImage id="256m_crafting_storage" scale="4" />
</Row>

Як і у випадку з комірками зберігання даних, MEGA також надає свої більші рівні сховища для крафтових процесорів. Хоча вони також потребують власної спеціалізованої версії <ItemLink id="ae2:crafting_unit" /> для врахування збільшення їхньої потужності, вони все одно легко впораються навіть з найбільшими завданнями крафту завдяки більшій пам'яті, а також виглядатимуть *до біса круто* у чорному кольорі.

<RecipeFor id="mega_crafting_unit" />
<RecipeFor id="1m_crafting_storage" />
<RecipeFor id="4m_crafting_storage" />
<RecipeFor id="16m_crafting_storage" />
<RecipeFor id="64m_crafting_storage" />
<RecipeFor id="256m_crafting_storage" />

Як додатковий бонус, MEGA також надає власний еквівалент на <ItemLink id="ae2:crafting_accelerator" />, хоча з перевагою забезпечення не одного, а *ЧОТИРЬОХ* потоків співпроцесорної обробки в просторі кожного доданого блоку співпроцесора.

<BlockImage id="mega_crafting_accelerator" scale="4" />
<RecipeFor id="mega_crafting_accelerator" />

І просто заради повного набору, існує також MEGA-еквівалент на <ItemLink id="ae2:crafting_monitor" />. Він насправді нічим не відрізняється від звичайного монітора, але він служить доповненням до вищезгаданих пристроїв для користувачів, які хочуть зберегти певну естетичну узгодженість і зберегти той самий елегантний, темний вигляд усього свого мультиблоку процесора.

<BlockImage id="mega_crafting_monitor" scale="4" />
<RecipeFor id="mega_crafting_monitor" />

## МЕГА Постачальник шаблонів

<Row>
  <BlockImage id="mega_pattern_provider" scale="4" />
  <GameScene zoom="4" background="transparent">
    <ImportStructure src="assets/assemblies/cable_mega_pattern_provider.snbt" />
  </GameScene>
</Row>

Доповнюючи <ItemLink id="ae2:pattern_provider" />, **МЕГА Постачальник шаблонів** підтримує тенденцію надання більших варіантів відповідних пристроїв AE2, подвоюючи місткість шаблонів, що дозволяє зберігати та обробляти загалом 18 шаблонів. Однак це також пов'язано з компромісною можливістю зберігати лише [**шаблони обробки**](ae2:items-blocks-machines/patterns.md), тому <ItemLink id="ae2:molecular_assembler" /> не зможе напряму працювати з ним.

<Row>
  <RecipeFor id="mega_pattern_provider" />
  <RecipeFor id="cable_mega_pattern_provider" />
</Row>
