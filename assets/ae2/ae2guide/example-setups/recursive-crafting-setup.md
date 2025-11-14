---
navigation:
  parent: example-setups/example-setups-index.md
  title: Рекурсивне вироблення
  icon: minecraft:netherite_upgrade_smithing_template
---

# Установка рекурсивного вироблення

Як зазначено в [автовироблені](../ae2-mechanics/autocrafting.md), алгоритм планування автовироблення не може обробляти рецепти, де основним виходом є один зі складників. Наприклад, він не може обробляти клонування <ItemLink id="minecraft:netherite_upgrade_smithing_template" />s.

Одним із рішень є використання здатності <ItemLink id="level_emitter" /> прикидатися [шаблоном](../items-blocks-machines/patterns.md).

Це може бути використано для ввімкнення невеликої установки, яка постійно виконує майстрування. У цьому випадку ми розглянемо установку для клонування <ItemLink id="minecraft:netherite_upgrade_smithing_template" />.

<RecipeFor id="minecraft:netherite_upgrade_smithing_template" />

---

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/recursive_recipe_setup.snbt" />

  <BoxAnnotation color="#dddddd" min="1 0 0" max="2 1 1">
        (1) Інтерфейс: налаштовано на зберігання необхідних додаткових складників: діаманиа та незераку.
        <Row><ItemImage id="minecraft:diamond" scale="2" /> <ItemImage id="minecraft:netherrack" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.3 1 0.3" max="2.7 1.3 0.7">
        (2) Випромінювач рівня: Налаштований на незеритовий ковальський шаблон, встановлено на «Випромінювати редстоун для створення предмета».
        <Row><ItemImage id="minecraft:netherite_upgrade_smithing_template" scale="2" /> <ItemImage id="crafting_card" scale="2" /></Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2 0 0" max="2.3 1 1">
        (3) Шина імпорту №1: Відфільтрована на предмети, які зберігаються в інтерфейсі. Має картку редстоуну. Режим редстоуну встановлено на «Активуватися з сигналом».
        <Row>
        <ItemImage id="minecraft:diamond" scale="2" />
        <ItemImage id="minecraft:netherrack" scale="2" />
        <ItemImage id="redstone_card" scale="2" />
        </Row>
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="4 1.3 2">
        (4) Шина зберігання №1: Встановлено на вищий пріоритет, ніж інша шина зберігання. ДУЖЕ ВАЖЛИВО.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 0 1" max="4 1 2">
        (5) Молекулярний збирач: Містить шаблон для дублювання ковальського шаблону.

        ![Pattern](../assets/diagrams/smithing_template_pattern_small.png)

        Він також має один ковальський шаблон, який вже вставлено вручну, коли ви вперше збираєте це.

  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        (6) Шина імпорту #2: Без налаштувань.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="1 0 1" max="2 1 1.3">
        (7) Шина зберігання №2: Відфільтрована на незеритовий ковальський шаблон. Встановлено на нижчий пріоритет, ніж інша шина зберігання.
        <ItemImage id="minecraft:netherite_upgrade_smithing_template" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="0 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="15" pitch="30" />
</GameScene>

## Конфігурації

- <ItemLink id="interface" /> (1) налаштовано на зберігання необхідних додаткових складників: діаманта та незераку.
- <ItemLink id="level_emitter" /> (2) налаштований на незеритовий ковальський шаблон, встановлено на «Випромінювати редстоун для створення предмета».
- Перша <ItemLink id="import_bus" /> (3) відфільтрована на предмети, які зберігаються в інтерфейсі. Має картку редстоуну. Режим редстоуну встановлено на «Активуватися з сигналом».
- Перша <ItemLink id="storage_bus" /> (4) має _вищий_ [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) ніж друга шина зберігання.
- <ItemLink id="molecular_assembler" /> (5) має шаблон для дублювання ковальського шаблону, а один шаблон кування вже вставлено вручну.

  ![Pattern](../assets/diagrams/smithing_template_pattern.png)

- Друга <ItemLink id="import_bus" /> (6) стоїть без налаштувань.
- Друга <ItemLink id="storage_bus" /> (7) відфільтрована на незеритовий ковальський шаблон. має _нижчий_ [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) ніж перша шина зберігання.

## Як це працює

1. <ItemLink id="level_emitter" /> видає себе за [шаблон](../items-blocks-machines/patterns.md) завдяки встановленій <ItemLink id="crafting_card" /> та налаштований на «Випромінювати редстоун для створення предмета». Таким чином незеритовий ковальський шаблон відображається в [терміналах](../items-blocks-machines/terminals.md) як робоче [автовироблення](../ae2-mechanics/autocrafting.md).
2. При отриманні запиту на створення цього предмета, або від гравця, або від самої системи, вмикається випромінювач рівня.
3. Перша <ItemLink id="import_bus" /> активується випромінювачем рівнів і витягує складники, які зберігає <ItemLink id="interface" />.
4. Єдина <ItemLink id="storage_bus" /> у мережі, яка може зберігати ці складники, це та, що встановлена на збирачі.
5. <ItemLink id="molecular_assembler" /> отримує складники (вже маючи 1 ковальський шаблон всередині) та виконує майстрування, створюючи 2 ковальських шаблони.
6. Друга <ItemLink id="import_bus" /> витягує 1 ковальський шаблон.
7. Перша шина зберігання має вищий пріоритет, тому цей ковальський шаблон повертається до збирача.
8. Друга <ItemLink id="import_bus" /> витягує 1 ковальський шаблон.
9. Збирач не може отримати інший шаблон коваля, тому другий шаблон коваля переходить до шини зберігання з нижчим пріоритетом, передаючи його в інтерфейс.
10. <ItemLink id="interface" />, не бувши налаштованим на стандартні ковальські шаблони, вставляє його в мережу.
