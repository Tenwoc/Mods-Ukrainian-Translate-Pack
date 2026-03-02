---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Процесори
  icon: logic_processor
  position: 010
categories:
- misc ingredients blocks
item_ids:
- ae2:logic_processor
- ae2:calculation_processor
- ae2:engineering_processor
- ae2:printed_silicon
- ae2:printed_logic_processor
- ae2:printed_calculation_processor
- ae2:printed_engineering_processor
- ae2:silicon
---

# Процесори

<Row>
  <ItemImage id="logic_processor" scale="4" />

  <ItemImage id="calculation_processor" scale="4" />

  <ItemImage id="engineering_processor" scale="4" />
</Row>

Процесори є одним з основних складників у [пристроях](../ae2-mechanics/devices.md) та машинах AE2. Вони також є одним з ваших перших великих викликів автоматизації. Існує три типи процесорів, в основі яких іде золото, <ItemLink id="certus_quartz_crystal" />, та діамант відповідно. Вони виготовляються за допомогою [штампів](presses.md) через <ItemLink id="inscriber" />, у багатоетапному процесі (зазвичай автоматизація досягається за допомогою декількох штампувальних пресів та фільтрованих логістичних засобів).

## Етапи виробництва

<Column gap="5">
  1.  Зберіть/виготовте необхідні складники: кремній, редстоун, золото, <ItemLink id="certus_quartz_crystal" /> та діамант.

  <RecipeFor id="silicon" />

  <br />

  2.  Відштампуйте необхідні компоненти друкованої схеми

  <Row>
    <RecipeFor id="printed_silicon" />

    <RecipeFor id="printed_logic_processor" />
  </Row>

  <Row>
    <RecipeFor id="printed_calculation_processor" />

    <RecipeFor id="printed_engineering_processor" />
  </Row>

  <br />

  3.  Завершіть збирання

  <Row>
    <RecipeFor id="logic_processor" />

    <RecipeFor id="calculation_processor" />
  </Row>

  <RecipeFor id="engineering_processor" />
</Column>
