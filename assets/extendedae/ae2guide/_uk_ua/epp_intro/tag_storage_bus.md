---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME Теґова шина зберігання
    icon: extendedae:tag_storage_bus
categories:
- extended devices
item_ids:
- extendedae:tag_storage_bus
---

# ME Теґова шина зберігання

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../structure/cable_tag_storage_bus.snbt"></ImportStructure>
</GameScene>

ME Теґова шина зберігання — це <ItemLink id="ae2:storage_bus" />, яку можна відфільтрувати за теґами предмета чи рідини та деякими базовими логічними операторами.

Ось кілька прикладів:

- Приймати лише необроблену руду

c:raw_materials/*

- Приймати всі злитки та дорогоцінні камені

c:ingots/* | c:gems/*

