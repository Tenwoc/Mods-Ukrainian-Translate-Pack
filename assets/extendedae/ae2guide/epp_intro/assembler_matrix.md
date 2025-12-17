---
navigation:
  parent: epp_intro/epp_intro-index.md
  title: Матричний збирач
  icon: extendedae:assembler_matrix_frame
categories:
  - extended devices
item_ids:
  - extendedae:assembler_matrix_frame
  - extendedae:assembler_matrix_wall
  - extendedae:assembler_matrix_glass
  - extendedae:assembler_matrix_pattern
  - extendedae:assembler_matrix_crafter
  - extendedae:assembler_matrix_speed
---

# Матричний збирач

<Row>
<BlockImage id="extendedae:assembler_matrix_frame" p:formed="true" p:powered="true" scale="5"></BlockImage>
<BlockImage id="extendedae:assembler_matrix_wall" scale="5"></BlockImage>
<BlockImage id="extendedae:assembler_matrix_glass" scale="5"></BlockImage>
</Row>
<Row>
<BlockImage id="extendedae:assembler_matrix_pattern" scale="5"></BlockImage>
<BlockImage id="extendedae:assembler_matrix_crafter" scale="5"></BlockImage>
<BlockImage id="extendedae:assembler_matrix_speed" scale="5"></BlockImage>
</Row>

Матричний збирач — це багатоблокова структура, яка комбінує <ItemLink id="ae2:molecular_assembler" /> та <ItemLink id="ae2:pattern_provider" />.
Він може виконувати багато завдань майстрування одночасно (на їх кількість впливає <ItemLink id="ae2:crafting_accelerator" /> у вашій МЕ мережі) й економити канали для вас.

## Конструкція

<GameScene zoom="3" background="transparent" interactive={true}>
  <ImportStructure src="../structure/assembler_matrix.snbt"></ImportStructure>
</GameScene>

Це повинен бути паралелепіпед з довжиною ребра від 3 до 7.

- Краї повинні складатися з каркаса матричного збирача.
- Грані повинні складатися зі стін/скла матричного збирача.
- Усередині конструкція повинна бути заповнена ядрами шаблонів/вироблення/прискорення матричного збирача.

Дійсний матричний збирач повинен містити принаймні одне ядро ​​шаблону та ядро вироблення.
Усередині конструкції не повинно бути порожніх місць.
Коли матричний збирач правильно сформований і живиться, лінії на рамці матричного збирача стануть синіми.

## Ядра матричного збирача

Існує 3 різних ядра матричного збирача.

- Ядро шаблонів матричного збирача

Матричний збирач користується шаблонами лише зі своїх ядер шаблонів. Кожне ядро ​​шаблонів забезпечує 36 слотів для шаблонів матричного збирача.

- Ядро вироблення матричного збирача

Матричний збирач призначає отримані завдання майстрування своїм ядрам вироблення. Кожне ядро ​вироблення ​може виконувати до 8 завдань майстрування одночасно.

- Ядро прискорення матричного збирача

Та ж <ItemLink id="ae2:speed_card" />, тільки для матричного збирача. 5 ядер прискорення дозволяють матричному збирачу працювати на повній швидкости.
Встановлення понад 5 ядер прискорення не дасть додаткового приросту швидкости.

## Інтерфейс

Клацніть ПКМ на сформованому та приєднаному до мережі матричному збирачі, щоб відкрити його інтерфейс.

![GUI](../pic/assembler_matrix.png)

Ви можете додавати або шукати в ньому шаблони та переглядати, скільки завдань майстрування він зараз виконує.
