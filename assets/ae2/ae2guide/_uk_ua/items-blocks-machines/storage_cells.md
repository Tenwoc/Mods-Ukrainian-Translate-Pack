---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Комірки зберігання
  icon: item_storage_cell_1k
  position: 410
categories:
- tools
item_ids:
- ae2:item_cell_housing
- ae2:fluid_cell_housing
- ae2:cell_component_1k
- ae2:cell_component_4k
- ae2:cell_component_16k
- ae2:cell_component_64k
- ae2:cell_component_256k
- ae2:item_storage_cell_1k
- ae2:item_storage_cell_4k
- ae2:item_storage_cell_16k
- ae2:item_storage_cell_64k
- ae2:item_storage_cell_256k
- ae2:fluid_storage_cell_1k
- ae2:fluid_storage_cell_4k
- ae2:fluid_storage_cell_16k
- ae2:fluid_storage_cell_64k
- ae2:fluid_storage_cell_256k
---

# Комірки зберігання

<Column>
  <Row>
    <ItemImage id="item_storage_cell_1k" scale="4" />

    <ItemImage id="item_storage_cell_4k" scale="4" />

    <ItemImage id="item_storage_cell_16k" scale="4" />

    <ItemImage id="item_storage_cell_64k" scale="4" />

    <ItemImage id="item_storage_cell_256k" scale="4" />
  </Row>

  <Row>
    <ItemImage id="fluid_storage_cell_1k" scale="4" />

    <ItemImage id="fluid_storage_cell_4k" scale="4" />

    <ItemImage id="fluid_storage_cell_16k" scale="4" />

    <ItemImage id="fluid_storage_cell_64k" scale="4" />

    <ItemImage id="fluid_storage_cell_256k" scale="4" />
  </Row>
</Column>

Комірки зберігання є одним з основних методів зберігання в Applied Energistics. Вони розміщуються в <ItemLink id="drive" /> або <a href="chest.md">МЕ Скриню</a>.

Пояснення їхньої місткості в байтах та типах дивіться у в розділі про [Байти та типи](../ae2-mechanics/bytes-and-types.md) for an explanation of their capacities in bytes and types.

Компоненти зберігання можна видалити з корпусу, якщо комірка порожня, натиснувши Shift+ПКМ із відповідною коміркою в руці.

<Row>
    <Recipe id="upgrade/item_storage_cell_1k_to_4k" />

    Ви можете покращити комірки зберігання до вищих рівнів, поєднуючи їх з компонентами зберігання вищого рівня в сітці майстрування. Їхній вміст буде збережено, а компонент нижчого рівня буде повернуто.
</Row>

## Місткість зберігання з різною кількістю типів

[Початкова вартість типів](../ae2-mechanics/bytes-and-types.md) визначається так, що комірка, що містить 1 тип, може вмістити вдвічі більше, ніж комірка з усіма зайнятими 63 типами.

| Комірка                                  | Загальна місткість комірки з 1 використовуваним типом | Загальна місткість комірки з 63 використовуваними типами |
| ---------------------------------------- | ----------------------------------------: | ------------------------------------------: |
| <ItemLink id="item_storage_cell_1k" />   |                                     8,128 |                                       4,160 |
| <ItemLink id="item_storage_cell_4k" />   |                                    32,512 |                                      16,640 |
| <ItemLink id="item_storage_cell_16k" />  |                                   130,048 |                                      66,560 |
| <ItemLink id="item_storage_cell_64k" />  |                                   520,192 |                                     266,240 |
| <ItemLink id="item_storage_cell_256k" /> |                                 2,080,768 |                                   1,064,960 |


## Розгалуження

Комірки можна фільтрувати, щоб приймати лише певні речі, подібно до того, як фільтрується <ItemLink id="storage_bus" />. Це робиться через <ItemLink id="cell_workbench" />.

Речі можна перетягувати в слоти з JEI/REI, навіть якщо у вас насправді немає жодного з них.

## Модифікатори

Комірки зберігання підтримують такі [модифікатори](upgrade_cards.md), які можна додати через <ItemLink id="cell_workbench" />:

*   <ItemLink id="fuzzy_card" /> (недоступна для рідинних комірок) дозволяє розгалузити комірку за рівнем пошкодження та/або ігнорувати NBT предметів
*   <ItemLink id="inverter_card" /> перемикає фільтр з білого списку на чорний список
*   <ItemLink id="equal_distribution_card" /> виділяє однакову кількість байтового простору комірки кожному типу, щоб єдиний тип не мін заповнити всю комірку
*   <ItemLink id="void_card" /> знищує вставлені речі, якщо комірка заповнена (або скінчилося виділене місце для цього конкретного типу у випадку карти рівного розподілу), що корисно для запобігання переповненню сховища ресурсами з ферм. Будьте обережні з розгалужуванням!
*   <ItemLink id="energy_card" /> може бути встановлена у портативні комірки, щоб збільшити місткість їхніх акумуляторів

## Розфарбовування

Портативні предметні та рідинні комірки можна розфарбувати подібно до шкіряної броні, об'єднавши їх разом із барвниками.
(Примітка перекладача: Це дійсно так? Не схоже, що це працює)

# Корпуси

Комірки можуть бути створені з компонента зберігання та корпуса або з рецептом корпусу навколо компонента зберігання:

<Row>
  <Recipe id="network/cells/item_storage_cell_1k" />

  <Recipe id="network/cells/item_storage_cell_1k_storage" />
</Row>

Самі корпуси створюються таким чином:

<Row>
  <RecipeFor id="item_cell_housing" />

  <RecipeFor id="fluid_cell_housing" />
</Row>

# Компоненти зберігання

Компоненти зберігання є основою всіх комірок AE2, визначаючи їх місткість. Кожен рівень збільшує місткість у 4 рази та коштує в 3 рази дорожче попереднього рівня.

<Column>
  <Row>
    <RecipeFor id="cell_component_1k" />

    <RecipeFor id="cell_component_4k" />

    <RecipeFor id="cell_component_16k" />
  </Row>

  <Row>
    <RecipeFor id="cell_component_64k" />

    <RecipeFor id="cell_component_256k" />
  </Row>
</Column>

# Предметні комірки

Предметні комірки можуть вміщувати до 63 різних типів предметів і доступні у всіх стандартних місткостях.

<Column>
  <Row>
    <Recipe id="network/cells/item_storage_cell_1k_storage" />

    <Recipe id="network/cells/item_storage_cell_4k_storage" />

    <Recipe id="network/cells/item_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/item_storage_cell_64k_storage" />

    <Recipe id="network/cells/item_storage_cell_256k_storage" />
  </Row>
</Column>

## Портативні предметні комірки

Вони діють як крихітна <ItemLink id="chest" /> у кишені або як своєрідний рюкзак. Їх можна заряджати через <ItemLink id="charger" />

На відміну від стандартних комірок зберігання, ці мають меншу місткість типів (що фактично збільшує їхню мінімальну місткість предметів), а також вдвічі меншу місткість байтів.

Окрім модифікаторів, які можуть отримати всі комірки, вони також приймають [енергетичні картки](ae2:items-blocks-machines/upgrade_cards.md#енергетична-картка) для збільшення власної місткості акумулятора.

<Column>
  <Row>
    <RecipeFor id="portable_item_cell_1k" />

    <RecipeFor id="portable_item_cell_4k" />

    <RecipeFor id="portable_item_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_item_cell_64k" />

    <RecipeFor id="portable_item_cell_256k" />
  </Row>
</Column>

# Рідинні комірки

Рідинні комірки можуть утримувати до 18 (або 5?) різних типів рідин і доступні у всіх стандартних місткостях.

<Column>
  <Row>
    <Recipe id="network/cells/fluid_storage_cell_1k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_4k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_16k_storage" />
  </Row>

  <Row>
    <Recipe id="network/cells/fluid_storage_cell_64k_storage" />

    <Recipe id="network/cells/fluid_storage_cell_256k_storage" />
  </Row>
</Column>

## Портативні рідинні комірки

Вони діють як крихітна <ItemLink id="chest" /> у вашій кишені або як різновид рюкзака. Їх можна заряджати через <ItemLink id="charger" />

На відміну від стандартних комірок зберігання, ці мають меншу місткість типів (що фактично збільшує їхню мінімальну місткість рідин), а також вдвічі меншу місткість байтів.
(Примітка перекладача: Схоже, вони вже не мають такого обмеження типів)

Окрім модифікаторів, які можуть отримати всі комірки, вони також приймають [енергетичні картки](ae2:items-blocks-machines/upgrade_cards.md#енергетична-картка) для збільшення власної місткості акумулятора.

<Column>
  <Row>
    <RecipeFor id="portable_fluid_cell_1k" />

    <RecipeFor id="portable_fluid_cell_4k" />

    <RecipeFor id="portable_fluid_cell_16k" />
  </Row>

  <Row>
    <RecipeFor id="portable_fluid_cell_64k" />

    <RecipeFor id="portable_fluid_cell_256k" />
  </Row>
</Column>

# Творча комірка зберігання

<Row>
  <ItemImage id="creative_storage_cell" scale="2" />
</Row>

Творчі комірки **не забезпечують нескінченне сховище**. Натомість вони діють як нескінченні джерела та поглиначі будь-якого предмета чи рідини, на які ви їх [розгалузите](cell_workbench.md).