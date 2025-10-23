---
navigation:
  parent: example-setups/example-setups-index.md
  title: Аметистова ферма
  icon: minecraft:amethyst_shard
---

# Фарм аметиста

Хоча <ItemLink id="growth_accelerator" /> працює на аметисті, звичайні методи фільтрування [друз істинного кварцу](../items-blocks-machines/budding_certus.md), в яких використовується <ItemLink id="annihilation_plane" /> не працюють на аметистових друзах. На відміну від зародків істинного кварцу, які дають <ItemLink id="certus_quartz_dust" />, зародки аметисту нічого не дають, тому площина анігіляції завжди їх руйнує, оскільки мережа завжди може зберігати «нічого».

Щоб обійти це, потрібно зачарувати площину анігіляції Шовковим дотиком. Тоді зародки аметисту матимуть дроп на кожній стадії та таким чином можуть бути відфільтровані.

Потім <ItemLink id="formation_plane" /> повинна знову розмістити аметистову друзу, щоб друга <ItemLink id="annihilation_plane" /> без Шовкового дотику отримала з неї <ItemLink id="minecraft:amethyst_shard" />.

Зверніть увагу, що через спрямованість друзи, прямо навпроти площини формування повинна бути тверда поверхня блоку.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/amethyst_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="2.7 1 1" max="3 2 2">
        (1) Площина анігіляції #1: Не має інтерфейсу налаштування, але зачарована на Шовковий дотик.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 1 1" max="2.3 2 2">
        (2) Площина формування: Відфільтрована на аметистову друзу.
        <ItemImage id="minecraft:amethyst_cluster" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1.3 0.7 1" max="2 1 2">
        (3) Площина анігіляції #2: Не має інтерфейсу налаштування, але може бути зачарована на Удачу.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="1.3 1 2">
        (4) Шина зберігання #1: Відфільтрована на аметистовий уламок.
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="0 0 .7" max="1 1 1">
        (5) Шина зберігання #2: Відфільтрована на аметистовий уламок. Має вищій налаштований пріоритет, ніж основне сховище.
        <ItemImage id="minecraft:amethyst_shard" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Налаштування

* Перша <ItemLink id="annihilation_plane" /> (1) не має інтерфейсу та не може бути налаштована, але повинна бути зачарована на Шовковий дотик.
* <ItemLink id="formation_plane" /> (2) відфільтрована на <ItemLink id="minecraft:amethyst_cluster" />.
* Друга <ItemLink id="annihilation_plane" /> (3) не має інтерфейсу та не може бути налаштована, але може бути зачарована на Удачу.
* Перша <ItemLink id="storage_bus" /> (4) відфільтрована на <ItemLink id="minecraft:amethyst_shard" />.
* Друга <ItemLink id="storage_bus" /> (5) відфільтрована на <ItemLink id="minecraft:amethyst_shard" /> та має вищій [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ), ніж ваше основне сховище.

## Як це працює

1. Перша <ItemLink id="annihilation_plane" /> намагається розбити те, що знаходиться перед нею, але може розбити тільки аметистову друзу, оскільки єдиним сховищем у підмережі є <ItemLink id="formation_plane" />, відфільтрована на аметистову друзу. Це працює тільки тому, що площина зачарована Шовковим дотиком, інакше вона могла б розбити незрілі друзи, оскільки вони нічого не дають.
2. <ItemLink id="formation_plane" /> розміщує друзи навпроти себе
3. Друга <ItemLink id="annihilation_plane" /> руйнує друзу, отримуючи <ItemLink id="minecraft:amethyst_shard" />.
4. Перша <ItemLink id="storage_bus" /> зберігає уламки у діжці. Технічно це не потрібно фільтрувати, оскільки єдине, з чим повинна стикатися друга площина анігіляції, — це повністю дозрілі друзи.
5. Друга <ItemLink id="storage_bus" /> надає основній мережі доступ до всіх аметистових уламків в діжці. Вона встановлена на високий [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ), щоб аметистові уламки переважно поверталися в діжку, а не в основне сховище.