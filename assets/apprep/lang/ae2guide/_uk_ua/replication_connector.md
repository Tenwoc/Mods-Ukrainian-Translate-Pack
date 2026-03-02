---
navigation:
  title: МЕ-реплікаційний сполучник
  icon: replication_connector
  parent: index.md
item_ids:
  - replication_connector
---

# Applied Replicatics: МЕ-реплікаційний сполучник

<BlockImage id="replication_connector" scale="4" />

Цей блок поєднує реплікаційну та МЕ мережі.

Він дозволяє зберігати матерію з реплікаційної мережі у МЕ мережі, а також передавати її назад для виконання задач реплікації.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="structures/replication_connector_basic.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Автовироблення

Предмети, зацифровані у реплікаційних чіпах, будуть відображатися як шаблони вироблення у МЕ мережі.
Виходом для вироблених реплікаторами предметів стане МЕ-реплікаційний сполучник, який передасть їх до МЕ мережі.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="structures/auto_craft.snbt" />
  <IsometricCamera yaw="195" pitch="30" />

  <BlockAnnotation color="#dddddd" x="0" y="0" z="1">
    Автовироблення використовує матерію, збережену у МЕ комірках матерії.
  </BlockAnnotation>
</GameScene>
