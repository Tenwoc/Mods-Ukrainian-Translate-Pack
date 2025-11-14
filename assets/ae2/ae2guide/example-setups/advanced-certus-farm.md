---
navigation:
  parent: example-setups/example-setups-index.md
  title: Вдосконалена ферма істинного кварцу
  icon: certus_quartz_crystal
  position: 120
---

# Вдосконалена ферма істинного кварцу

Це фактично просто [Напівавтоматична ферма істинного кварцу](semiauto-certus-farm.md), за винятком того, що вона повністю інтегрована у вашу МЕ систему.

Замість того щоб мати великий запас родючих блоків, та оновлювати їх вручну час від часу, ця система використовує [автоматизоване заряджання](charger-automation.md) та [автоматизовану трансформацію](throw-in-water-automation.md) для довершення автоматизації ферми.

Дивіться [Вирощування істинного кварцу](../ae2-mechanics/certus-growth.md) для отримання орієнтовної швидкості ферми.

**ЦЕ СКЛАДНА КОНСТРУКЦІЯ З РЕЧАМИ, ЩО СКЛАДАЮТЬСЯ ОДНА НА ОДНУ, ОБЕРТАЙТЕ СХЕМУ, ЩОБ РОЗГЛЯНУТИ ЇЇ З УСІХ КУТІВ**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/advanced_certus_farm.snbt" />

  <BoxAnnotation color="#ddaaaa" min="3.7 2 1" max="4 3 2">
        (1) Площина руйнування №1: Не має інтерфейсу для налаштування, але може бути зачарована Удачею.
  </BoxAnnotation>

  <BoxAnnotation color="#ddaaaa" min="2 2 1.7" max="3 3 2">
        (2) Шина зберігання №1: Відфільтрована на кристал істинного кварцу.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 2.5 1.5" color="#ff0000">
    Підмережа руйнування друз
  </DiamondAnnotation>

  <BoxAnnotation color="#aaddaa" min="3.7 1 1" max="4 2 2">
        (3) Площина руйнування №2: Не має інтерфейсу для налаштування, але може бути зачарована Шовковим дотиком.
  </BoxAnnotation>

  <BoxAnnotation color="#aaddaa" min="2 1 1.7" max="3 2 2">
        (4) Шина зберігання №2: Відфільтрована на блок істинного кварцу.
        <BlockImage id="quartz_block" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 1.5 1.5" color="#00ff00">
    Підмережа руйнування блоку істинного кварцу
  </DiamondAnnotation>

  <BoxAnnotation color="#ffddaa" min="4 0.7 1" max="5 1 2">
        (5) Площина формування: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#ffddaa" min="2 0.7 2" max="3 1 3">
        (6) Шина імпорту: Відфільтрована на надщерблений родючий кварц.
        <BlockImage id="flawed_budding_quartz" scale="2" />
  </BoxAnnotation>

  <DiamondAnnotation pos="3 0.5 1.5" color="#ddcc00">
    Підмережа розміщення родючого кварцу
  </DiamondAnnotation>

  <BoxAnnotation color="#aaaadd" min="1.7 2 2" max="2 3 3">
        (7) Шина зберігання №3: Відфільтрована на кристал істинного кварцу. Має пріоритет вище, ніж ваше основне сховище.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#aaaadd" min="2 1 2" max="3 2 3">
        (8) Інтерфейс: Встановлений на запасання одного надщербленого родючого кварцу, також має картку вироблення.
        <Row><BlockImage id="flawed_budding_quartz" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="1.5 0.5 0" color="#00ff00">
        До основної мережі, автоматизованого заряджання та автоматизованої трансформації у світі
        <Row>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
        </Row>
    </DiamondAnnotation>

  <IsometricCamera yaw="165" pitch="5" />
</GameScene>

## Конфігурації

### Добувач друз:

* Перша <ItemLink id="annihilation_plane" /> (1) не має інтерфейсу для налаштування, але може бути зачарована Удачею.
* Перша <ItemLink id="storage_bus" /> (2) відфільтрована на <ItemLink id="certus_quartz_crystal" />.

### Забирач блоку істинного кварцу:

* Друга <ItemLink id="annihilation_plane" /> (3) не має інтерфейсу для налаштування, але може бути зачарована Шовковим дотиком.
* Друга <ItemLink id="storage_bus" /> (4) відфільтрована на <ItemLink id="quartz_block" />.

### Розміщувач родючого кварцу:

* <ItemLink id="formation_plane" /> (5) без налаштувань.
* <ItemLink id="import_bus" /> (6) відфільтрована на <ItemLink id="flawed_budding_quartz" />.

### В основній мережі:

* Третя <ItemLink id="storage_bus" /> (7) відфільтрована на <ItemLink id="certus_quartz_crystal" />, та має [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) вище, ніж ваше основне сховище.
* <ItemLink id="interface" /> (8) налаштована запасати 1 надщерблений родючий кварц, а також має встановлену <ItemLink id="crafting_card" />.

## Як це працює

### Добувач друз:

Підмережа добувача друз працює майже так само, як і підмережа у [простій фермі істинного кварцу](simple-certus-farm.md).

1. <ItemLink id="annihilation_plane" /> намагається зламати те, що знаходиться перед ним, але може зламати лише <ItemLink id="quartz_cluster" /> оскільки єдиним сховищем у підмережі є <ItemLink id="storage_bus" />, відфільтрована на <ItemLink id="certus_quartz_crystal" />.
2. <ItemLink id="storage_bus" /> зберігає кристали істинного кварцу у діжці.

### Забирач блоку істинного кварцу

Підмережа забирача блоку істинного кварцу служить для розбиття виснаженого родючого кварцу, коли він перетворюється на звичайний <ItemLink id="quartz_block" />.
Вона працює подібно до добувача друз.

1. <ItemLink id="annihilation_plane" /> намагається зламати те, що знаходиться перед ним, але може зламати лише <ItemLink id="quartz_block" /> оскільки єдиним сховищем у підмережі є <ItemLink id="storage_bus" />, відфільтрована на <ItemLink id="quartz_block" />. Площина повинна мати чари Шовкового дотику, щоб родючий кварц не деградував після розбиття, і таким чином площина не зламала б його передчасно.
2. <ItemLink id="storage_bus" /> зберігає блоки істинного кварцу в <ItemLink id="interface" />, дозволяючи [автоматизованій трансформації у воді](throw-in-water-automation.md) використати його для нового <ItemLink id="flawed_budding_quartz" />.

### Розміщувач родючого кварцу

Підмережа розміщувача родючого кварцу служить для розміщення нового <ItemLink id="flawed_budding_quartz" />, коли підмережа забирача добуває виснажений блок.

1. <ItemLink id="import_bus" /> імпортує родючий блок з <ItemLink id="interface" /> у власне [мережеве сховище](../ae2-mechanics/import-export-storage.md)
2. Єдиним сховищем у підмережі є <ItemLink id="formation_plane" />, яка розміщує блок.

### В основній мережі

* <ItemLink id="storage_bus" /> надає головній мережі (а також [автоматизованому заряднику](charger-automation.md)) доступ до всіх кристалів істинного кварцу у діжці. Їй встановлено високий [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) щоб кристали істинного кварцу переважно поверталися назад у діжку, а не до вашого основного сховища.
* <ItemLink id="interface" /> надає підмережі розміщувача родючого кварцу доступ до <ItemLink id="flawed_budding_quartz" />, а підмережі забирача блоку істинного кварцу — спосіб повернути виснажені блоки назад у головну мережу. <ItemLink id="crafting_card" /> дозволяє інтерфейсу запитувати нові родючі блоки у системи [автовироблення](../ae2-mechanics/autocrafting.md).