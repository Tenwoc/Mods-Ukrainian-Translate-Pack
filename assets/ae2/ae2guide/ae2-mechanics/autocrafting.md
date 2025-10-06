---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Autocrafting
  icon: pattern_provider
---

# Автовироблення

### Велика справа

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/autocraft_setup_greebles.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Автоматичне вироблення — одна з основних функцій AE2. Замість того, щоб вручну майструвати потрібну кількість кожного інгредієнта
і працювати, як якийсь *плебей*, ви можете попросити свою систему ME зробити це за вас. Або автоматично виробляти предмети і експортувати їх кудись.
Або автоматично зберігати певну кількість предметів на складі завдяки розумним механікам. Це також працює з 
рідинами та певними аддонами для незвичайних типів модових матеріалів, таких як гази Mekanism. Це досить круто.

Це досить складна тема, тож пристебніться і поїхали!

Установка для автовироблення складається з 3 речей:
- Надсилач запитів на вироблення
- Процесори вироблення
- <ItemLink id="pattern_provider" />.

Ось як це відбувається:

1.  Щось надсилає запит на вироблення. Це можете бути ви, коли натискаєте у терміналі на щось, що доступно до автовироблення,
    або шина експорту чи інтерфейс із карткою вироблення, коли передають визначені для них предмети.

*   (**ВАЖЛИВО:** ви можете надсилати запити за допомогою СКМ для предметів, що вже є у сховищі, проте це може конфліктувати із сортувальними модами (що також часто працюють через СКМ)),

2.  Система ME розраховує необхідні інгредієнти та попередні етапи вироблення для виконання запиту і зберігає їх у вибраному процесорі вироблення.

3.  <ItemLink id="pattern_provider" /> із відповідним [шаблоном](../items-blocks-machines/patterns.md) виштовхує інгредієнти, зазначені шаблоном у прилегле містило.
    У випадку із рецептами майстрування («шаблон майстрування») це повинен бути <ItemLink id="molecular_assembler" />.
    У випадку із рецептами не майстрування («шаблон обробки») це повинен бути інший блок, машина, чи навіть редстоуновий механізм.

4.  Результат вироблення повертається в систему якимось чином, хай то через шину імпорту, інтерфейс або повернення результату до постачальника шаблонів.
    **Зверніть увагу, що повинна відбутися подія «введення предмета в систему», ви не можете просто перенаправити результат в скриню, до якої під'єднана <ItemLink id="storage_bus" />.**

5.  Якщо цей крафт є необхідною умовою для іншого крафта в запиті, предмети зберігаються у тому ж процесорі вироблення, а потім використовуються в цьому крафті.

## Рекурсивні рецепти

<ItemImage id="minecraft:netherite_upgrade_smithing_template" scale="4" />

Єдине, з чим автовироблення *не може* впоратись — це рекурсивні рецепти. До цього відносяться рецепти дублювання на кшталт
«1 редстоуновий пил = 2 редстоунових пили» через кидання редстоуну у басейн мани Botania. Іншим прикладом є звичайні ковальські шаблони Minecraft. Однак навіть для них існує [метод виконання рецептів](../example-setups/recursive-crafting-setup.md).

# Шаблони

<ItemImage id="crafting_pattern" scale="4" />

Для створення шаблонів використовується <ItemLink id="pattern_encoding_terminal" />, який дозволяє перезаписувати пусті шаблони.

Існує кілька різних типів шаблонів для різних цілей:

*   <ItemLink id="crafting_pattern" /> зберігає рецепт верстака. Його можна вставити напряму у <ItemLink id="molecular_assembler" />, щоб він
    обробляв цей рецепт кожного разу, як отримуватиме інгредієнти, проте його основне використання відкривається, коли поряд з ним розміщено <ItemLink id="pattern_provider" />.
    У цьому випадку постачальники шаблонів мають особливу поведінку і надсилають відповідний шаблон разом з інгредієнтами до прилеглих збирачів.
    Оскільки збирачі автоматично вивантажують результати майстрування до сусідніх містил, для автоматизації шаблонів майстрування достатньо мати збирач на постачальнику шаблонів.

***

*   <ItemLink id="smithing_table_pattern" /> дуже схожий на шаблон майстрування, але зберігає рецепти ковальського стола. Він також автоматизується
    постачальником шаблоні та молекулярним збирачем, і функціонує так само. Насправді шаблони майстрування, кування та тесання можуть
    використовуватися в єдиній конструкції.

***

*   <ItemLink id="stonecutting_pattern" /> дуже схожий на шаблон майстрування, але зберігає рецепти каменеріза. Він також автоматизується
    постачальником шаблоні та молекулярним збирачем, і функціонує так само. Насправді шаблони майстрування, кування та тесання можуть
    використовуватися в єдиній конструкції.

***

*   <ITEMLINK id="processing_pattern" /> — це те, звідки береться велика гнучкість в автовироблення. Ці шаблони є найбільш узагальненим типом,
    просто кажучи, «якщо постачальник шаблонів переніс ці інгредієнти кудись, система ME отримає результати в найближчому або віддаленому 
    майбутньому». Саме так ви будете автовиробляти майже з будь-якою модифікованою машиною, піччю тощо. Оскільки вони є настільки загальними у 
    використанні і не зважають на те, що відбувається між переміщенням інгредієнтів і отриманням результату, ви можете робити дійсно цікаві речі, 
    наприклад, вводити інгредієнти в цілий складний виробничий ланцюг фабрики, який буде сортувати речі, приймати інші інгредієнти з ферм, що 
    виробляють їх нескінченно, друкувати весь сценарій «Бі Муві» — система ME не зважає на це, поки отримує результат, що вказаний у 
    шаблоні. Насправді йому навіть байдуже, чи пов'язані інгредієнти якимось чином з результатом. Ви можете вказати йому «1 вишнева дошка = 1 зірка Незеру»
    і ваша ферма Візерів вбиватиме Візера після отримання вишневої дошки.

Кілька постачальників шаблонів з однаковими шаблонами здатні працювати паралельно. Крім того, ви можете встановити шаблон,
наприклад, 8 кругляків = 8 каменів замість 1 кругляк = 1 камінь, і постачальник шаблонів вставлятиме до вашої установки витоплення
одразу 8 кругляків у кожний момент опрацювання замість 1.

## Найпримітивніша форма "шаблону"

Насправді існує ще більш «загальна» форма «шаблону», ніж шаблон обробки. <ItemLink id="level_emitter" /> з карткою вироблення можна 
налаштувати так, щоб він випромінював сигнал редстоуну для вироблення чогось. Цей «шаблон» не визначає і навіть не враховує 
інгредієнти. Він лише говорить: «Якщо цей випромінювач рівня випромінює редстоуновий сигнал, система ME отримає цей предмет у 
найближчому або віддаленому майбутньому». Зазвичай це використовується для активації та деактивації нескінченних ферм, які не 
потребують вхідних інгредієнтів, або для активації системи, яка обробляє рекурсивні рецепти (які стандартне автомайстрування не може 
зрозуміти), як, наприклад, «1 кругляк = 2 кругляки», якщо у вас є машина, яка дублює кругляк.

# Процесори вироблення

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/crafting_cpus.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Процесори вироблення управляють запитами/завданнями на виготовлення. Вони зберігають Вони зберігають проміжні інгредієнти під час виконання багатоетапних завдань 
і впливають на розмір завдань та, певною мірою, на швидкість їх виконання. Вони багатоблочні та повинні бути цільними паралелепіпедами 
з щонайменше 1 сховищем для виготовлення.

Процесори вироблення складаються з:

*   (Необхідно) [Сховища для вироблення](../items-blocks-machines/crafting_cpu_multiblock.md), доступні в усіх стандартних розмірах комірок (1К, 4К, 16К, 64К, 256К). Вони зберігають інгредієнти та
    проміжні інгредієнти, що потрібні у завданні вироблення, тому для обробки завдань з виготовлення, що вимагають більше інгредієнтів, процесору потрібні
    більші або додаткові сховища.
*   (Необов'язково) <ItemLink id="crafting_accelerator" />змушує систему частіше відправляти партії інгредієнтів від постачальників шаблонів.
    Це дозволяє, наприклад, постачальнику шаблонів, оточеному 6 молекулярними складальниками, надсилати інгредієнти (і, таким чином, використовувати) всі 6 одночасно, а не тільки один.
*   (Необов'язково) <ItemLink id="crafting_monitor" /> відображає завдання, яке в цей момент обробляє процесор. <ItemLink id="color_applicator" /> може забарвити іх.
*   (Необов'язково) <ItemLink id="crafting_unit" /> використовується для заповнення простору, щоб зробити процесор прямокутним паралелепіпедом.

Кожен процесор обробляє 1 запит або завдання, тому якщо ви хочете одночасно запросити обчислювальний процесор і 256 гладких каменів, вам знадобиться дві процесорних конструкції.

Їх можна налаштувати для обробки запитів від гравців, автоматизації (експортні шини та інтерфейси) або обох.

# Постачальники шаблонів

<Row>
<BlockImage id="pattern_provider" scale="4" />

<BlockImage id="pattern_provider" p:push_direction="up" scale="4" />

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/blocks/cable_pattern_provider.snbt" />
</GameScene>
</Row>

<ItemLink id="pattern_provider" />s are the primary way in which your autocrafting system interacts with the world. They push the ingredients in
their [patterns](../items-blocks-machines/patterns.md) to adjacent inventories, and items can be inserted into them in order to insert them into the network. Often
a channel can be saved by piping the output of a machine back into a nearby pattern provider (often the one that pushed the ingredients)
instead of using an <ItemLink id="import_bus" /> to pull the output of the machine into the network.

Of note, since they push the ingredients directly from the [crafting storage](../items-blocks-machines/crafting_cpu_multiblock.md#crafting-storage) in a crafting CPU, they
never actually contain the ingredients in their inventory, so you cannot pipe out from them. You have to have the provider push
to another inventory (like a barrel) then pipe from that.

Also of note, the provider has to push ALL of the ingredients at once, it can't push half-batches. This is useful
to exploit.

Pattern providers have a special interaction with interfaces on [subnets](../ae2-mechanics/subnetworks.md): if the interface is unmodified (nothing in the request slots)
the provider will skip the interface entirely and push directly to that subnet's [storage](../ae2-mechanics/import-export-storage.md),
skipping the interface and not filling it with recipe batches, and more importantly, not inserting the next batch until there's space in storage.

Multiple pattern providers with identical patterns are supported and work in parallel.

Pattern providers will attempt to round-robin their batches to all of their faces, thus using all attached machines in parallel.

## Variants

Pattern Providers come in 3 different variants: normal, directional, and flat. This affects which specific sides they push
ingredients to, receive items from, and provide a network connection to.

*   Normal pattern providers push ingredients to all sides, receive inputs from all sides, and, like most AE2 machines, act
    like a cable providing network connection to all sides.

*   Directional pattern providers are made by using a <ItemLink id="certus_quartz_wrench" /> on a normal pattern provider to change its
    direction. They only push ingredients to the selected side, receive inputs from all sides, and specifically don't provide a network
    connection on the selected side. This allows them to push to AE2 machines without connecting networks, if you want to make a subnetwork.

*   Flat pattern providers are a [cable subpart](../ae2-mechanics/cable-subparts.md), and so multiple can be placed on the same cable, allowing for compact setups.
    They act similar to the selected side on a directional pattern provider, providing patterns, receiving inputs, and not
    providing a network connection on their face.

Pattern providers can be swapped between normal and flat in a crafting grid.

## Settings

Pattern providers have a variety of modes:

*   **Blocking Mode** stops the provider from pushing a new batch of ingredients if there are already
    ingredients in the machine.
*   **Lock Crafting** can lock the provider under various redstone conditions, or until the result of the
    previous craft is inserted into that specific pattern provider.
*   The provider can be shown or hidden on <ItemLink id="pattern_access_terminal" />s.

## Priority

Priorities can be set by clicking the wrench in the top-right of the GUI. In the case of several [patterns](../items-blocks-machines/patterns.md)
for the same item, patterns in providers with higher priority will be used over patterns in providers with lower priority,
unless the network does not have the ingredients for the higher priority pattern.

# Molecular Assemblers

<BlockImage id="molecular_assembler" scale="4" />

The <ItemLink id="molecular_assembler" /> takes items input into it and carries out the operation defined by an adjacent <ItemLink id="pattern_provider" />,
or the inserted <ItemLink id="crafting_pattern" />, <ItemLink id="smithing_table_pattern" />, or <ItemLink id="stonecutting_pattern" />,
then pushes the result to adjacent inventories.

Their main use is next to a <ItemLink id="pattern_provider" />. Pattern providers have special behavior in this case,
and will send information about the relevant pattern along with the ingredients to adjacent assemblers. Since assemblers auto-eject the results of
crafts to adjacent inventories (and thus into the return slots of the pattern provider), an assembler on a pattern provider
is all that is needed to automate crafting patterns.

<GameScene zoom="4" background="transparent">
<ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>
