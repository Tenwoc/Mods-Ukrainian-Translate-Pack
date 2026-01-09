---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизація печі
  icon: minecraft:furnace
---

# Автоматизація печі

Зверніть увагу, що оскільки тут використовується <ItemLink id="pattern_provider" />, він призначений для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md). Якщо ви просто хочете автоматизувати окрему піч, використовуйте лійки, скрині тощо.

Автоматизація <ItemLink id="minecraft:furnace" /> трохи складніша, ніж автоматизація простіших машин, таких як [зарядний пристрій](../example-setups/charger-automation.md). Піч вимагає введення з двох окремих сторін та вилучення з третьої. Предмет, який потрібно витопити, потрібно проштовхнути у верхню грань, паливо потрібно проштовхнути в бічну грань, а результат потрібно витягнути знизу.

Це можна зробити, використовуючи <ItemLink id="pattern_provider" /> зверху, <ItemLink id="export_bus" /> збоку для постійної подачі палива та <ItemLink id="import_bus" /> знизу для імпорту результатів у мережу. Однак, це займе 3 [канали](../ae2-mechanics/channels.md).

Ось як це можна зробити лише з 1 каналом:

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/furnace_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Постачальник шаблонів: Спрямований варіант, що отримується застосуванням кварцового ключа, з відповідними шаблонами обробки.

        ![Iron Pattern](../assets/diagrams/furnace_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (2) Інтерфейс: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="1.3 2 1">
        (3) Шина зберігання #1: Відфільтрована на вугілля.
        <ItemImage id="minecraft:coal" scale="2" />
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 2 0" max="1 2.3 1">
        (4) Шина зберігання #2: Відфільтрована на НЕ вугілля за допомогою картки інвертора.
        <Row><ItemImage id="minecraft:coal" scale="2" /><ItemImage id="inverter_card" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

* <ItemLink id="pattern_provider" /> (1) не має налаштувань, з відповідними <ItemLink id="processing_pattern" />. Його напрямок визначається застосуванням <ItemLink id="certus_quartz_wrench" />.

  ![Iron Pattern](../assets/diagrams/furnace_pattern.png)

* <ItemLink id="interface" /> (2) не має налаштувань.
* Перша <ItemLink id="storage_bus" /> (3) відфільтрована на вугілля або будь-яке інше паливо, яке ви хочете використовувати.
* Друга <ItemLink id="storage_bus" /> (4) відфільтрована на усе, що не є паливом за допомогою <ItemLink id="inverter_card" />.

## Як це працює

1. <ItemLink id="pattern_provider" /> передає складники в <ItemLink id="interface" />. (Насправді, як оптимізація, він ігнорує порожній інтерфейс та передає складники одразу до шини зберігання, яка належить до однієї з інтерфейсом мережі)
2. Інтерфейс налаштовано так, щоб нічого не зберігати, тому він намагається завантажувати складники в [мережеве сховище](../ae2-mechanics/import-export-storage.md).
3. Єдиним сховищем у зеленій підмережі є <ItemLink id="storage_bus" />. Шина, відфільтрована до вугілля, передає вугілля в паливний слот печі через бічну грань. Шина, відфільтрована до НЕ вугілля, передає предмети, що підлягають витопленню, у верхньому слоті, через верхню грань.
4. Піч робить свою пічкову штуку.
5. Лійка витягує результати з дна печі та передає їх у слоти повернення постачальника, тим самим повертаючи їх до основної мережі.
