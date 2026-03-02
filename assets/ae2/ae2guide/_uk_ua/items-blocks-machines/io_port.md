---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: МЕ Порт зберігання
  icon: io_port
  position: 210
categories:
- devices
item_ids:
- ae2:io_port
---

# Порт зберігання

<BlockImage id="io_port" p:powered="true" scale="8" />

Порт зберігання дозволяє швидко заповнювати або спорожняти [комірки сховища](../items-blocks-machines/storage_cells.md) до або з [мережевого сховища](../ae2-mechanics/import-export-storage.md).

It can be rotated with a <ItemLink id="certus_quartz_wrench" />.

## Налаштування

*   Порт зберігання можна налаштувати на переміщення комірки до вихідних слотів, коли комірка спорожниться, заповниться або коли робота завершиться.
*   Якщо вставлена <ItemLink id="redstone_card" />, будуть доступні опції для різних умов редстоуну
*   У центрі графічного інтерфейсу є стрілка, щоб вказати напрямок передачі елементів: з комірки до [мережевого сховища](../ae2-mechanics/import-export-storage.md) або зі сховища до комірки.

## Модифікатори

Порт зберігання підтримує такі [модифікатори](upgrade_cards.md):

*   <ItemLink id="speed_card" /> збільшує кількість речей, які можна перемістити за операцію
*   <ItemLink id="redstone_card" /> додає керування редстоуном, що дозволяє роботу за високим та низьким сигналами або одноразово за імпульс

## Рецепт

<RecipeFor id="io_port" />
