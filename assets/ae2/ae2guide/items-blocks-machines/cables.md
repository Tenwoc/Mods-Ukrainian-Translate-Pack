---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Кабелі
  icon: fluix_glass_cable
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:white_glass_cable
- ae2:orange_glass_cable
- ae2:magenta_glass_cable
- ae2:light_blue_glass_cable
- ae2:yellow_glass_cable
- ae2:lime_glass_cable
- ae2:pink_glass_cable
- ae2:gray_glass_cable
- ae2:light_gray_glass_cable
- ae2:cyan_glass_cable
- ae2:purple_glass_cable
- ae2:blue_glass_cable
- ae2:brown_glass_cable
- ae2:green_glass_cable
- ae2:red_glass_cable
- ae2:black_glass_cable
- ae2:fluix_glass_cable
- ae2:white_covered_cable
- ae2:orange_covered_cable
- ae2:magenta_covered_cable
- ae2:light_blue_covered_cable
- ae2:yellow_covered_cable
- ae2:lime_covered_cable
- ae2:pink_covered_cable
- ae2:gray_covered_cable
- ae2:light_gray_covered_cable
- ae2:cyan_covered_cable
- ae2:purple_covered_cable
- ae2:blue_covered_cable
- ae2:brown_covered_cable
- ae2:green_covered_cable
- ae2:red_covered_cable
- ae2:black_covered_cable
- ae2:fluix_covered_cable
- ae2:white_covered_dense_cable
- ae2:orange_covered_dense_cable
- ae2:magenta_covered_dense_cable
- ae2:light_blue_covered_dense_cable
- ae2:yellow_covered_dense_cable
- ae2:lime_covered_dense_cable
- ae2:pink_covered_dense_cable
- ae2:gray_covered_dense_cable
- ae2:light_gray_covered_dense_cable
- ae2:cyan_covered_dense_cable
- ae2:purple_covered_dense_cable
- ae2:blue_covered_dense_cable
- ae2:brown_covered_dense_cable
- ae2:green_covered_dense_cable
- ae2:red_covered_dense_cable
- ae2:black_covered_dense_cable
- ae2:fluix_covered_dense_cable
- ae2:white_smart_cable
- ae2:orange_smart_cable
- ae2:magenta_smart_cable
- ae2:light_blue_smart_cable
- ae2:yellow_smart_cable
- ae2:lime_smart_cable
- ae2:pink_smart_cable
- ae2:gray_smart_cable
- ae2:light_gray_smart_cable
- ae2:cyan_smart_cable
- ae2:purple_smart_cable
- ae2:blue_smart_cable
- ae2:brown_smart_cable
- ae2:green_smart_cable
- ae2:red_smart_cable
- ae2:black_smart_cable
- ae2:fluix_smart_cable
- ae2:white_smart_dense_cable
- ae2:orange_smart_dense_cable
- ae2:magenta_smart_dense_cable
- ae2:light_blue_smart_dense_cable
- ae2:yellow_smart_dense_cable
- ae2:lime_smart_dense_cable
- ae2:pink_smart_dense_cable
- ae2:gray_smart_dense_cable
- ae2:light_gray_smart_dense_cable
- ae2:cyan_smart_dense_cable
- ae2:purple_smart_dense_cable
- ae2:blue_smart_dense_cable
- ae2:brown_smart_dense_cable
- ae2:green_smart_dense_cable
- ae2:red_smart_dense_cable
- ae2:black_smart_dense_cable
- ae2:fluix_smart_dense_cable
---

# Кабелі

<GameScene zoom="3" background="transparent">
  <ImportStructure src="../assets/assemblies/cables.snbt" />
  <IsometricCamera yaw="180" pitch="30" />
</GameScene>

Хоча МЕ мережі також створюються суміжними МЕ-сумісними машинами, кабелі є основним способом розширення МЕ мережі на більші площі.

Можна використовувати кабелі різних кольорів, щоб суміжні кабелі не були з'єднані один з одним, що дозволяє ефективніше розподіляти [канали](../ae2-mechanics/channels.md). Вони також впливають на колір підключених до них компонентів, і таким чином ви зможете всюди мати не тільки фіолетові компоненти. Флюїксові кабелі можуть з'єднуватися з усіма іншими забарвленими кабелями.

Зверніть увагу, **КОЛЬОРИ КАБЕЛІВ НІЯК НЕ ВПЛИВАЮТЬ НА КАНАЛИ**

## Важливе зауваження

**Якщо ви новачок в AE2 і не знайомі з каналами, використовуйте розумний кабель та щільний розумний кабель, де це можливо. Це покаже, як канали прокладаються вашою мережею, що зробить їхню поведінку більш зрозумілою.**

## Ще одне зауваження

**Це не труби для предметів, рідин, енергії, чи щось інше.** Вони не мають внутрішнього інвентарю, постачальники шаблонів та машини не передають предмети в них напряму; все, що вони роблять, це з'єднують [пристрої](../ae2-mechanics/devices.md) AE2 разом у мережу.

## Скляний кабель

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/fluix_glass_cable.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="fluix_glass_cable" /> — це найпростіший кабель, який можна створити. Він передає енергію та до 8 [каналів](../ae2-mechanics/channels.md). Він йде у 17 різних кольорах, усталено використовується флюїксовий, і його можна пофарбувати, використовуючи будь-який з 16 барвників.

Щоб створити кольорові кабелі, оточіть барвник будь-якого типу 8 кабелями одного типу (колір кабелів не має значення, але вони повинні бути одного типу: скляний, розумний тощо). Ви також можете пофарбувати кабелі будь-яким сумісним з Forge фарбувальником у світі.

Ви можете поєднати кабель будь-якого кольору з відром води, щоб видалити барвник.

Ви можете покрити кабель вовною, щоб створити <ItemLink id="fluix_covered_cable" />, а також <ItemLink id="fluix_smart_cable" /> щоб краще зрозуміти, що відбувається з вашими [каналами](../ae2-mechanics/channels.md).

<RecipeFor id="fluix_glass_cable" />

<RecipeFor id="blue_glass_cable" />

## Огорнений кабель

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Варіант огорненого кабелю не має жодних ігрових переваг порівняно з його флюїксовим аналогом. Однак його можна використовувати як альтернативний естетичний вибір, якщо ви віддаєте перевагу огорненому вигляду.

Може бути забарвлений так само як <ItemLink id="fluix_glass_cable" />. <ItemLink id="fluix_covered_cable" /> можна скласти чотири рази, щоб отримати <ItemLink id="fluix_covered_dense_cable" />.

<Recipe id="network/cables/covered_fluix" />

<RecipeFor id="blue_covered_cable" />

## Щільний кабель

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_covered_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Цей кабель має більшу пропускну спроможність й може передавати 32 канали, на відміну від стандартного кабелю, який може передавати лише 8. Однак він не підтримує шини, тому для цього спочатку потрібно перейти від щільного до меншого кабелю (наприклад використовуючи <ItemLink id="fluix_glass_cable" /> або <ItemLink id="fluix_smart_cable" />), перш ніж використовувати шини або панелі.

Щільні кабелі дещо змінюють поведінку каналів на «найкоротший шлях»: канали пройдуть найкоротший шлях до щільного кабелю, а потім найкоротший шлях через цей щільний кабель до контролера.

<Recipe id="network/cables/dense_covered_fluix" />

<RecipeFor id="blue_covered_dense_cable" />

## Розумний кабель

<Row>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/fluix_smart_dense_cable.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>
</Row>

Хоча цей кабель дещо схожий на <ItemLink id="fluix_covered_cable" /> за зовнішнім виглядом, він забезпечує діагностичну функцію, візуалізуючи використання каналів на кабелях. Канали виглядають як підсвічені кольорові лінії, що проходять вздовж чорної смуги на кабелях, даючи вам розуміння того, як канали використовуються у вашій мережі. Для звичайних розумних кабелів перші чотири канали відображаються як лінії, що відповідають кольору кабелю, наступні чотири відображаються як білі лінії. Для щільного розумного кабелю кожна смуга представляє 4 канали.

У мережах, які мають <ItemLink id="controller" />, лінії на кабелях показують точний шлях, яким проходять канали.

Розумні кабелі в автономних мережах натомість показуватимуть кількість каналів, що використовуються в мережі, а не кількість каналів, що проходять через цей конкретний кабель.

Їх також можна забарвити так само як <ItemLink id="fluix_glass_cable" />.

<Recipe id="network/cables/smart_fluix" />

<Recipe id="network/cables/dense_smart_fluix" />

<RecipeFor id="blue_smart_cable" />
