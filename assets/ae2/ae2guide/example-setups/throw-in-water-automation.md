---
navigation:
  parent: example-setups/example-setups-index.md
  title: Автоматизована трансформація у воді
  icon: fluix_crystal
---

# Автоматизована трансформація у воді

Зверніть увагу, що оскільки тут використовується <ItemLink id="pattern_provider" />, ця установка призначена для інтеграції у вашу систему [автовироблення](../ae2-mechanics/autocrafting.md).

Деякі рецепти вимагають кидання предметів у воду (хоча подібну систему можна використовувати для кидання предметів в інші місця). Це можна автоматизувати за допомогою <ItemLink id="formation_plane" />, <ItemLink id="annihilation_plane" />, та деякої допоміжної інфраструктури (це, по суті, 2 модифіковані [трубні підмережі](pipe-subnet.md)).

Ця система призначена для використання в поєднанні з [автоматизованим заряджанням](charger-automation.md) для забезпечення <ItemLink id="charged_certus_quartz_crystal" />.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/throw_in_water.snbt" />

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (1) Постачальник шаблонів: Без налаштувань, з відповідними шаблонами обробки.

        ![Fluix Pattern](../assets/diagrams/fluix_pattern_small.png) ![Flawed Budding Pattern](../assets/diagrams/flawed_budding_pattern_small.png)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1.7 0 1" max="2 1 2">
        (2) Інтерфейс: Без налаштувань.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 .7 1" max="2 1 2">
        (3) Площина формування: Налаштована на скидання предметів.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 2 1" max="2 2.3 2">
        (4) Площина руйнування: Не має інтерфейсу для налаштування.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (5) Шина зберігання: Відфільтрована на результати шаблонів
        <Row><ItemImage id="fluix_crystal" scale="2" /><BlockImage id="flawless_budding_quartz" scale="2" /></Row>
  </BoxAnnotation>

<DiamondAnnotation pos="3.9 0.5 1.5" color="#00ff00">
        До основної мережі та автоматизованого заряджання
        <GameScene zoom="3" background="transparent">
          <ImportStructure src="../assets/assemblies/charger_automation.snbt" />
          <IsometricCamera yaw="195" pitch="30" />
        </GameScene>
    </DiamondAnnotation>

  <IsometricCamera yaw="180" pitch="0" />
</GameScene>

## Конфігурації шаблони

* <ItemLink id="pattern_provider" /> (1) стоїть без змін, з відповідними <ItemLink id="processing_pattern" />s
  * Для <ItemLink id="fluix_crystal" /> базовий рецепт з JEI/REI працює добре:

    ![Fluix Pattern](../assets/diagrams/fluix_pattern.png)

  * <ItemLink id="flawed_budding_quartz" /> ймовірно, найкраще створювати безпосередньо з <ItemLink id="quartz_block" />, що дозволяє уникнути проблем зі складниками одного рецепту, що є результатами іншого, через що шина зберігання не зможе фільтрувати:

    ![Flawed Budding Pattern](../assets/diagrams/flawed_budding_pattern.png)

* <ItemLink id="interface" /> (2) стоїть без змін.
* <ItemLink id="formation_plane" /> (3) налаштовано на скидання складників у воду.
* <ItemLink id="annihilation_plane" /> (4) не має інтерфейсу та не може бути налаштований.
* <ItemLink id="storage_bus" /> (5) відфільтрована на результати шаблонів.

## Як це працює

1.  <ItemLink id="pattern_provider" /> передає складники в <ItemLink id="interface" /> на своєму боці, в зеленіу підмережу
2.  Інтерфейс (не налаштований) намагається передати свій вміст у власне [мережеве сховище](../ae2-mechanics/import-export-storage.md)
3.  Єдиним сховищем у зеленій підмережі є <ItemLink id="formation_plane" />, яка скидає отримані предмети у воду
4.  <ItemLink id="annihilation_plane" /> в помаранчевій підмережі намагається підібрати предмети, які щойно були скинуті, але не може, оскільки <ItemLink id="storage_bus" /> зверху постачальника шаблонів (єдине сховище в помаранчевій підмережі) відфільтрована лише на результати шаблонів
5.  Предмети виконують свою трансформацію в світі.
6.  Площина анігіляції тепер може збирати предмети перед собою, оскільки шині зберігання дозволено їх зберігати.
7.  Шина зберігання зберігає результати у постачальнику шаблонів, тим самим повертаючи їх до мережі.
