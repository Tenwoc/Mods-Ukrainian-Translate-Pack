---
navigation:
  title: МЕ Комірка матерії
  icon: matter_cell_256k
  parent: index.md
item_ids:
  - matter_cell_housing
  - matter_cell_1k
  - matter_cell_4k
  - matter_cell_16k
  - matter_cell_64k
  - matter_cell_256k
  - mega_matter_cell_housing
  - matter_cell_1m
  - matter_cell_4m
  - matter_cell_16m
  - matter_cell_64m
  - matter_cell_256m
---

# Applied Replicatics: МЕ Комірки матерії

<Row>
  <ItemImage id="matter_cell_housing" scale="4"/>
  <ItemImage id="matter_cell_1k" scale="4"/>
  <ItemImage id="matter_cell_4k" scale="4"/>
  <ItemImage id="matter_cell_16k" scale="4"/>
  <ItemImage id="matter_cell_64k" scale="4"/>
  <ItemImage id="matter_cell_256k" scale="4"/>
</Row>

[Storage Cells](ae2:items-blocks-machines/storage_cells.md) Це комірки, які можуть зберігати реплікаційну матерію.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="structures/matter_cells.snbt" />
  <IsometricCamera yaw="195" pitch="30" />

  <BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 0.3">
    Щоб вона з'явилася, використайте повний бак матерії двічі.
  </BoxAnnotation>
</GameScene>

Базові властивості цих комірок не відрізняються від [звичайних](ae2:items-blocks-machines/storage_cells.md); 1 байт комірки уміщує 256 одиниць матерії.

Для додаткової інтеграції з MEGA Cells, у цьому аддоні також присутня варіація МЕГА комірок матерії.

---

## Примітка

Щоб обмінюватися матерією із реплікаційною мережею, вам знадобиться <ItemLink id="replication_connector" />.
Зауважте, що він не сумісний з іншими модами-мостами для AE2-Replication.
