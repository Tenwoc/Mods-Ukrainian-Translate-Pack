---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Вирощування істинного кварцу
  icon: quartz_cluster
---

# Вирощування істинного кварцу

## В основному просто скопійовано зі сторінки «Вступ»

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/budding_certus_1.snbt" />
</GameScene>

Друзи істинного кварцу проростають із [блоків родючого кварцу](../items-blocks-machines/budding_certus.md), як аметист. Якщо ви зламаєте неповноцінний зародок
кристала, він скине один <ItemLink id="certus_quartz_dust" />, незалежно від удачі на інструменті. <ItemLink id="certus_quartz_crystal" /> падає із повноцінної
друзи у кількости 4 одиниць, і удача вже може збільшити це число.

Існує 4 рівні якости родючого істинного кварцу: бездоганний, надщерблений, пошкоджений та дефектний, і ви і спочатку їх можна знайти в [метеоритах](../ae2-mechanics/meteorites.md).

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_blocks.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Кожного разу, коли друза зростає, родючий блок має шанс погіршитися на один рівень,
зрештою перетворюючись на звичайний блок істинного кварцу. Їх можна відновити (і створити нові родючі блоки),
кинувши родючий блок (або блок істинного кварцу) та один <ItemLink id="charged_certus_quartz_crystal" /> або більше у воду.

<RecipeFor id="damaged_budding_quartz" />

Бездоганні істинні родючі блоки не бідніють і генерують істинний кварц нескінченно. Однак їх неможливо створити або перемістити за допомогою кайла, навіть із використанням Шовкового дотику (проте їх все ж можна перемістити за допомогою [просторового зберігання](./spatial-io.md)).

Самі по собі друзи істинного кварцу ростуть дуже повільно. На щастя <ItemLink id="growth_accelerator" /> значно
прискорює цей процес, якщо розмістити його поруч із родючим блоком. Вам слід побудувати кілька таких пристроїв якомога скоріше.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/budding_certus_2.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Складні взаємодії означають, що кожна закрита сторона родючого блоку сповільнює сукупну швидкість зростання, що зрештою переважає ефект більшої кількості прискорювачів. Емпіричні випробування показують наступне:

![Предмети / видобуток за хвилину](../assets/diagrams/certus_farm_speed_chart_1.png)

![загальні устави](../assets/diagrams/certus_farm_speed_chart_2.png)

Якщо у вас недостатньо кварцу, щоб також створити <ItemLink id="energy_acceptor" /> або <ItemLink id="vibration_chamber" />,
ви можете створити <ItemLink id="crank" /> і прикріпити його до кінця прискорювача.

Автоматичний збір істинного кварцу [описаний тут](../example-setups/simple-certus-farm.md).
