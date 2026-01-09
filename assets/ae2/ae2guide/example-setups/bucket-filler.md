---
navigation:
  parent: example-setups/example-setups-index.md
  title: Наповнювач відер
  icon: minecraft:water_bucket
---

# Наповнювач відер

Дивіться також [Спорожнювач відер](bucket-emptier.md).

Зауважте, що оскільки тут використовується <ItemLink id="pattern_provider" />, він призначений для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md).

Іноді життя незручне, і вам потрібна рідина у відрі, але ви можете отримувати її лише саме рідиною. Іноді це може зробити машина (наприклад, Fluid Transposer з Thermal Expansion), але у вас не завжди є мод, який робить це зручно для вас. На щастя, у звичайному Minecraft є трохи менш зручний спосіб, <ItemLink id="minecraft:dispenser" />.

**Зверніть увагу, що зазвичай вам не потрібно цього робити, оскільки заміни рідини в [терміналі кодування шаблонів](../items-blocks-machines/terminals.md#термінал-кодування-шаблонів) дозволяють використовувати саму рідину в рецепті майстрування замість відра.**

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/bucket_filler.snbt" />

<BoxAnnotation color="#dddddd" min="2 1 0" max="3 2 1">
        (1) Постачальник шаблонів: Встановлено блокування вироблення «З сигналом редстоуна» та увімкнено режим блокування з відповідними шаблонами обробки.

        <Row>
        ![Fill Pattern](../assets/diagrams/water_fill_pattern_small.png)
        ![Fill Pattern](../assets/diagrams/lava_fill_pattern_small.png)
        </Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1.1 0.1" max="3.2 1.9 0.9">
        (2) Інтерфейс: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.1 1.1 0.8" max="3.9 1.9 1">
        (3) Шина зберігання №1: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="4.05 1.05 0.8" max="4.95 1.95 1">
        (4) Площина формування: Відфільтована на НЕ відра за допомогою картки інвертора.
        <Row><ItemImage id="minecraft:bucket" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.2 2 1.2" max="3.8 2.2 1.8">
        (5) Шина імпорту: Відфільтована на НЕ відра за допомогою картки інвертора.
        <Row><ItemImage id="minecraft:bucket" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2.1 2 0.1" max="2.9 2.2 0.9">
        (6) Шина зберігання №2: Без налаштувань.
  </BoxAnnotation>

<DiamondAnnotation pos="0 1.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="225" pitch="45" />
</GameScene>

## Конфігурації

* <ItemLink id="pattern_provider" /> (1) налаштовано на блокування вироблення «З сигналом редстоуна» та увімкнений режим блокування з відповідними <ItemLink id="processing_pattern" />.
  
    ![Charger Pattern](../assets/diagrams/water_fill_pattern.png)
    ![Charger Pattern](../assets/diagrams/lava_fill_pattern.png)

* <ItemLink id="interface" /> (2) без налаштувань.
* Перша <ItemLink id="storage_bus" /> (3) без налаштувань.
* <ItemLink id="formation_plane" /> (4) відфільтована на НЕ відра за допомогою картки інвертора. <Row><ItemImage id="minecraft:bucket" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
* <ItemLink id="import_bus" /> (5) відфільтована на НЕ відра за допомогою картки інвертора. <Row><ItemImage id="minecraft:bucket" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
* Друга <ItemLink id="storage_bus" /> (6) без налаштувань.

## Як це працює

1. <ItemLink id="pattern_provider" /> передає складники в <ItemLink id="interface" />. (Насправді, як оптимізація, він ігнорує порожній інтерфейс та передає складники одразу до шини зберігання, яка належить до однієї з інтерфейсом мережі)
2. За допомогою механізмів, описаних у [трубних підмережах](pipe-subnet.md#постачання-складників-у-декілька-місць) та <ItemLink id="formation_plane" />, відро потрапляє в <ItemLink id="minecraft:dispenser" />, а рідина розміщується перед ним.
3. <ItemLink id="minecraft:comparator" /> виявляє відро в роздавачі і таким чином одночасно живить роздавач і блокує <ItemLink id="pattern_provider" />.
4. Роздавач забирає рідину у відро, і тепер має повне відро.
5. <ItemLink id="import_bus" /> витягує повне відро з роздавача та зберігає його через <ItemLink id="storage_bus" /> у постачальнику шаблонів, повертаючи його до основної мережі.
6. Компаратор бачить, що роздавач порожній, і розблоковує постачальника.
