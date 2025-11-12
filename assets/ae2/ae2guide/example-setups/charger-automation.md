---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизація зарядного пристрою
  icon: charger
---

# Автоматизація зарядного пристрою

Зверніть увагу, що оскільки тут використовується <ItemLink id="pattern_provider" />, він призначений для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md). Якщо ви просто хочете автоматизувати окремий <ItemLink id="charger" />, використовуйте лійки, скрині тощо.

Автоматизація <ItemLink id="charger" /> досить проста. <ItemLink id="pattern_provider" /> завантажує складник у зарядний пристрій, а потім [підмережева труба](pipe-subnet.md) або інша предметна труба завантажує результат назад у постачальника.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/charger_automation.snbt" />

<BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Постачальник шаблонів: Без налаштувань, з відповідними шаблонами обробки. Також забезпечує живлення зарядного пристрою.

        ![Charger Pattern](../assets/diagrams/charger_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 0" max="1 1.3 1">
        (2) Шина імпорту: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 1 0" max="2 1.3 1">
        (3) Шина зберігання: Без налаштувань.
  </BoxAnnotation>

<DiamondAnnotation pos="4 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

* <ItemLink id="pattern_provider" /> (1) без налаштувань, з відповідними <ItemLink id="processing_pattern" />. Він також забезпечує <ItemLink id="charger" /> [енергією](../ae2-mechanics/energy.md) оскільки діє як [кабель](../items-blocks-machines/cables.md).
  
    ![Charger Pattern](../assets/diagrams/charger_pattern.png)

* <ItemLink id="import_bus" /> (2) без налаштувань.
* <ItemLink id="storage_bus" /> (3) без налаштувань.

## Як це працює

1. <ItemLink id="pattern_provider" /> завантажує складники в <ItemLink id="charger" />.
2. Зарядний пристрій робить свою заряджальну штуку.
3. <ItemLink id="import_bus" /> у зеленій підмережі витягує результат із зарядного пристрою та намагається зберегти його в [мережевому сховищі](../ae2-mechanics/import-export-storage.md).
4. Єдиним сховищем у зеленій підмережі є <ItemLink id="storage_bus" />, яка зберігає результати у постачальник шаблонів, повертаючи їх до основної мережі.
