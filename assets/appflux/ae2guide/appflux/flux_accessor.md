---
navigation:
  parent: appflux/appflux-index.md
  title: Флаксовий приймач
  icon: appflux:flux_accessor
categories:
  - flux accessor
item_ids:
  - appflux:flux_accessor
  - appflux:part_flux_accessor
---

# Флаксовий приймач

<Row>
<BlockImage id="appflux:flux_accessor" scale="8"></BlockImage>
<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/flux_accessor.snbt"></ImportStructure>
</GameScene>
</Row>

Флаксовий приймач може передавати енергію з та у вашу МЕ мережу. Усталено вони не мають обмежень вводу/виводу, і їх можна змінити в конфігурації Appflux.

Він має швидкий та звичайний режими. У швидкому режимі приймач виводить енергію кожного такту, що може спричиняти затримки під час інтенсивного використання. У звичайному режимі приймач виводить енергію, спираючись на місткість енергії цілі, що не спричинить проблем із затримкою.

- Примітка: «Енергія», згадана тут, — це FE, що зберігається у ваших [FE комірках](./flux_cells.md), а не енергія [енергетичних комірок](ae2:items-blocks-machines/energy_cells.md).
