---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Контролер
  icon: controller
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:controller
---

# Контролер

<BlockImage id="controller" p:state="online" scale="8" />

Контролер є центром маршрутизації [МЕ мережі](../ae2-mechanics/me-network-connections.md). Без нього мережа стає «автономною» і може мати максимум 8 каналів, що використовують [пристрої](../ae2-mechanics/devices.md) total.

Неможливо мати 2 контролери в одній [МЕ мережі](../ae2-mechanics/me-network-connections.md).

Контролер забезпечує 32 [канали](../ae2-mechanics/channels.md) на кожну грань.

Для функціонування контролера потрібно 6 AE/т на блок контролера. Кожен блок контролера може зберігати 8000 AE, тому більші мережі можуть потребувати додаткового накопичення енергії. Дивіться розділ [енергії](../ae2-mechanics/energy.md) для отримання детальної інформації.

Багатоблокові контролери можна створювати у достатньо вільній формі.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controllers.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Однак, є кілька правил, яких необхідно дотримуватися:

1.  Усі блоки контролера в [МЕ мережі](../ae2-mechanics/me-network-connections.md) мають бути з'єднані; інакше блоки стануть червоними.
2.  Розмір контролера має бути в межах 7x7x7; інакше він стане червоним.
3.  Контролер може мати 2 суміжні блоки тільки на 1 осі; якщо блок порушує це правило, він вимкнеться та стане червоним.

<GameScene zoom="2" background="transparent">
  <ImportStructure src="../assets/assemblies/controller_rules.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Якщо всі правила дотримано та ввімкнено, контролер повинен світитися та змінювати кольори.

Ви можете клацнути ПКМ на контролері, щоб отримати той самий графічний інтерфейс, що й <ItemLink id="network_tool" />

## Рецепт

<RecipeFor id="controller" />
