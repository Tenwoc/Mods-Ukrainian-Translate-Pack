---
navigation:
  parent: example-setups/example-setups-index.md
  title: Спорожнювач відер
  icon: minecraft:bucket
---

# Спорожнювач відер

Дивіться також [Наповнювач відер](bucket-filler.md).

Зауважте, що оскільки тут використовується <ItemLink id="pattern_provider" />, він призначений для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md).

Іноді життя незручне, і вам потрібна сама рідина, але ви можете отримувати її лише відрами. Іноді це може зробити машина (наприклад, Fluid Transposer з Thermal Expansion), але у вас не завжди є мод, який робить це зручно для вас. На щастя, у звичайному Minecraft є трохи менш зручний спосіб, <ItemLink id="minecraft:dispenser" />.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/bucket_emptier.snbt" />

<BoxAnnotation color="#dddddd" min="2 1 0" max="3 2 1">
        (1) Постачальник шаблонів: Встановлено блокування вироблення «З сигналом редстоуна» та увімкнено режим блокування з відповідними шаблонами обробки.

        <Row>
        ![Fill Pattern](../assets/diagrams/water_empty_pattern_small.png)
        ![Fill Pattern](../assets/diagrams/lava_empty_pattern_small.png)
        </Row>
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2.1 2 0.1" max="2.9 2.2 0.9">
        (2) Інтерфейс: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.1 2 1.1" max="3.9 2.2 1.9">
        (3) Шина зберігання №1: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="4.05 1.05 0.8" max="4.95 1.95 1">
        (4) Площина руйнування: Немає інтерфейсу для налаштування.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.2 1.2 0.8" max="3.8 1.8 1">
        (5) Шина імпорту: Відфільтрована на відра.
        <ItemImage id="minecraft:bucket" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3 1.1 0.1" max="3.2 1.9 0.9">
        (6) Шина зберігання №2: Без налаштувань.
  </BoxAnnotation>

<DiamondAnnotation pos="0 1.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="225" pitch="45" />
</GameScene>

## Конфігурації

* <ItemLink id="pattern_provider" /> (1) налаштовано на блокування вироблення «З сигналом редстоуна» та увімкнений режим блокування з відповідними <ItemLink id="processing_pattern" />s.
  
    ![Charger Pattern](../assets/diagrams/water_empty_pattern.png)
    ![Charger Pattern](../assets/diagrams/lava_empty_pattern.png)

* <ItemLink id="interface" /> (2) без налаштувань.
* Перша <ItemLink id="storage_bus" /> (3) без налаштувань.
* <ItemLink id="annihilation_plane" /> (4) не має інтерфейсу та не може бути налаштована.
* <ItemLink id="import_bus" /> (5) відфільтрована на відра.
<ItemImage id="minecraft:bucket" scale="2" />
* Друга <ItemLink id="storage_bus" /> (6) без налаштувань.

## Як це працює

1. <ItemLink id="pattern_provider" /> передає складники в <ItemLink id="interface" />. (Насправді, як оптимізація, він ігнорує порожній інтерфейс та передає складники одразу до шини зберігання, яка належить до однієї з інтерфейсом мережі)
2. За допомогою механізмів, описаних у [трубних підмережах](pipe-subnet.md#постачання-складників-у-декілька-місць), відро потрапляє в <ItemLink id="minecraft:dispenser" />.
3. <ItemLink id="minecraft:comparator" /> виявляє відро в роздавачі і таким чином одночасно живить роздавач і блокує <ItemLink id="pattern_provider" />.
4. Роздавач виливає рідину з відра, і тепер має порожнє відро.
5. <ItemLink id="import_bus" /> витягує порожнє відро з роздавача та зберігає його через <ItemLink id="storage_bus" /> у постачальнику шаблонів, повертаючи його до основної мережі.
6. Компаратор бачить, що роздавач порожній, і розблоковує постачальника.