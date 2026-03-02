---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Родючий істинний кварц
  icon: flawless_budding_quartz
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:flawless_budding_quartz
- ae2:flawed_budding_quartz
- ae2:chipped_budding_quartz
- ae2:damaged_budding_quartz
- ae2:small_quartz_bud
- ae2:medium_quartz_bud
- ae2:large_quartz_bud
- ae2:quartz_cluster
---

# Родючий істинний кварц

(також дивіться [Вирощування істинного кварцу](../ae2-mechanics/certus-growth.md))

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Друзи істинного кварцу проростають з блоків родючого істинного кварцу, подібних до аметисту. Вони знаходяться в [метеоритах](../ae2-mechanics/meteorites.md). Існує 4 рівні блоків родючого істинного кварцу: бездоганні, надщерблені, пошкоджені та дефектні. Їх найлегше ідентифікувати за допомогою модів, таких як HWYLA, Jade, The One Probe тощо (або на екрані f3).

З надщербленими, пошкодженими та дефектними родючими блоками, щоразу, коли зародок виростає на наступну стадію, родючий блок має шанс деградувати на один рівень, зрештою перетворюючись на звичайний <ItemLink id="quartz_block" />.

Бездоганний родючий істинний кварц не деградує від зростання друз і діє як нескінченне джерело.

При розбитті звичайним кайлом родючий істинний кварц деградує на 1 рівень. Якщо його розбити кайлом, зачарованим Шовковим дотиком, він не здеградує, якщо тільки він не був бездоганним. **Це означає, що бездоганний родючий істинний кварц не можна підняти та перемістити кайлом**. Натомість для переміщення бездоганного родючого істинного кварцу можна використовувати [просторове зберігання](../ae2-mechanics/spatial-io.md).

## Рецепти

Надщерблений, пошкоджений та дефектний родючі істинні кварци можна створити, кинувши попередній рівень блоку (або <ItemLink id="quartz_block" />) у воду, додавши один <ItemLink id="charged_certus_quartz_crystal" /> чи декілька.

Бездоганний родючий істинний кварц не можна створити, його можна лише знайти у світі.

<Row>
  <RecipeFor id="damaged_budding_quartz" />

  <RecipeFor id="chipped_budding_quartz" />

  <RecipeFor id="flawed_budding_quartz" />
</Row>
