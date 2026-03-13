---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME Точна шина експорту
    icon: extendedae:precise_export_bus
categories:
- extended devices
item_ids:
- extendedae:precise_export_bus
---

# ME Точна шина експорту

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_precise_export_bus.snbt"></ImportStructure>
</GameScene>

ME Точна шина експорту експортує предмети/рідини у вказаних кількостях. Експорт здійснюється лише тоді, коли місткість може повністю прийняти весь вивід.

## Приклад

![GUI](../pic/pre_bus_gui1.png)

Це налаштування визначає експорт 3 кругляки за операцію. Експорт припиняється, коли кількість кругляка в мережі стає меншою за 3.

![GUI](../pic/pre_bus_gui2.png)

Експорт також припиняється, коли цільовий контейнер не може вмістити весь експортований обсяг. Скриня тепер може вмістити лише 2 кругляки, тому шина експорту зупиняється.