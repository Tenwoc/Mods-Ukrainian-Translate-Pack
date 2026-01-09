---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: МЕ Площина формування
  icon: formation_plane
  position: 210
categories:
  - devices
item_ids:
  - ae2:formation_plane
---

# Площина формування

<GameScene zoom="8" background="transparent">
  <ImportStructure src="../assets/blocks/formation_plane.snbt" />
</GameScene>

Площина формування розміщує блоки та скидає предмети. Вона працює як <ItemLink id="storage_bus" />, налаштована тільки на вставляння, й замість фактичного «зберігання» предметів, вона розміщує їх або скидає у світі.

<GameScene zoom="8" interactive={true}>
  <ImportStructure src="../assets/assemblies/formation_plane_demonstration.snbt" />
  <IsometricCamera yaw="255" pitch="30" />
</GameScene>

Зверніть увагу, що її поведінка схожа на «шина імпорту -> шина зберігання» та «інтерфейс -> шина зберігання» в [трубних підмережах](../example-setups/pipe-subnet.md).

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/interface_storage_pipe.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Цей [пристрій](../ae2-mechanics/devices.md) використовує механіку, що використовується шинами зберігання в таких речах, як [трубні підмережі](../example-setups/pipe-subnet.md), і може замінити шини зберігання в цих уставах, якщо ви хочете скидати предмети/розміщувати блоки замість транспортування предметів.

Площини є [кабельними компонентами](../ae2-mechanics/cable-subparts.md).

**ПЕРЕКОНАЙТЕСЯ, ЩО FAKE PLAYER УВІМКНЕНО НА ВАШІЙ ПРИВЛАСНЕНІЙ ДІЛЯНЦІ**

## Фільтрація

Усталено площина розміщуватиме/скидатиме будь-що. Предмети, вставлені в її слоти фільтрів, діятимуть як білий список, дозволяючи розміщувати лише їх.

Предмети та рідини можна перетягувати в слоти з JEI/REI, навіть якщо у вас насправді немає жодного з цих предметів.

Клацніть ПКМ за допомогою місткости з рідиною (наприклад, відром або резервуаром), щоб встановити цю рідину як фільтр замість конкретно предмета відра або резервуара.

## Пріоритет

Пріоритети можна встановити, натиснувши на кнопку налаштування у правому верхньому куті інтерфейсу. Предмети, що надходять у мережу, спочатку потрапляють у сховище з найвищим пріоритетом.

## Налаштування

- Площина має налаштування для розміщення блоків у світі або скидання предметів

## Модифікатори

Площина формування підтримує такі [модифікатори](upgrade_cards.md):

- <ItemLink id="capacity_card" /> збільшує кількість слотів для фільтрування
- <ItemLink id="fuzzy_card" /> дозволяє площині фільтрувати за рівнем пошкодження та/або ігнорувати будь-які NBT предметів
- <ItemLink id="inverter_card" /> перемикає фільтр з білого списку на чорний список

## Рецепт

<RecipeFor id="formation_plane" />
