---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME Порогова шина експорту
    icon: extendedae:threshold_export_bus
categories:
- extended devices
item_ids:
- extendedae:threshold_export_bus
---

# ME Порогова шина експорту

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_threshold_export_bus.snbt"></ImportStructure>
</GameScene>

ME Порогова шина експорту працює, коли кількість речі, що зберігається в мережі ME, вище/нижче порогового значення.

## Приклади

![GUI](../pic/thr_bus_gui1.png)

Поріг міді встановлено на 128, тому система експортує мідь, коли збереженої міді більше ніж 128.

![GUI](../pic/thr_bus_gui2.png)

Поріг такий самий, як і раніше, але режим встановлено на НИЖЧЕ. Система експортує мідь, коли збереженої міді менше ніж 128.