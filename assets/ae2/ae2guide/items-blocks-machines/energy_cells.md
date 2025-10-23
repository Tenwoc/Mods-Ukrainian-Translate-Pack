---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Енергетичні комірки
  icon: energy_cell
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:energy_cell
- ae2:dense_energy_cell
- ae2:creative_energy_cell
---

# Енергетичні комірки

<Row gap="20">
  <BlockImage id="energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="dense_energy_cell" scale="8" p:fullness="4" />

  <BlockImage id="creative_energy_cell" scale="8" />
</Row>

Енергетичні комірки надають мережі більшу місткість [енергії](../ae2-mechanics/energy.md). Деякий обсяг енергетичного буфера допомагає згладити сплески споживання енергії, коли велика кількість предметів вставляється або витягується, дозволяє мережі працювати, коли енергія не генерується (наприклад, вночі за допомогою сонячних панелей), або дає обробляти величезне миттєве споживання енергії [просторового зберігання](../ae2-mechanics/spatial-io.md).

## Смуги заповнення

<Row>
<BlockImage id="energy_cell" scale="4" p:fullness="0" />
<BlockImage id="energy_cell" scale="4" p:fullness="1" />
<BlockImage id="energy_cell" scale="4" p:fullness="2" />
<BlockImage id="energy_cell" scale="4" p:fullness="3" />
<BlockImage id="energy_cell" scale="4" p:fullness="4" />
</Row>

Смуги на текстурі комірки відповідають кількості енергії, яку вона має.

*   0 при заряді нижче 25%
*   1 при заряді від 25% до 50%
*   2 при заряді від 50% до 75%
*   3 при заряді від 75% до 99%
*   4 при заряді вище 99%

## Типи комірок

*   <ItemLink id="energy_cell" /> може зберігати 200 тис. AE, і лише її однієї має бути достатньо для більшості випадків використання, легко справляючись зі стрибками напруги під час звичайного використання мережі.
*   <ItemLink id="dense_energy_cell" /> може зберігати 1,6 млн AE і призначена для випадків, коли ви хочете запускати мережу від накопиченої енергії або обробляти величезне миттєве споживання енергії великими установками [просторового зберігання](../ae2-mechanics/spatial-io.md).
*   <ItemLink id="creative_energy_cell" /> – це творчий предмет налаголдження, що забезпечує НЕСКІНЧЕННУ ПОТУЖНІСТЬ чи щось таке.

## Рецепти

<Row>
  <RecipeFor id="energy_cell" />

  <RecipeFor id="dense_energy_cell" />
</Row>
