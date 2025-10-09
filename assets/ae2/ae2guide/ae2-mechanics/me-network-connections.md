---
navigation:
  parent: ae2-mechanics/ae2-mechanics-index.md
  title: Мережування
  icon: fluix_glass_cable
---

# Мережування

## Що означає «Мережа»?

«Мережа» — це група [пристроїв](../ae2-mechanics/devices.md), з'єднаних блоками, які можуть передавати [канали](../ae2-mechanics/channels.md), такі як [кабелі](../items-blocks-machines/cables.md) або блокоподібні машини та [пристрої](../ae2-mechanics/devices.md) (<ItemLink id="charger" />, <ItemLink id="interface" />, <ItemLink id="drive" /> тощо). Технічно один кабель вже є мережею, її найменшою одиницею.

## Додаткова інформація про розміщування пристроїв

Для [пристроїв](../ae2-mechanics/devices.md), які мають певну мережеву функцію (наприклад, <ItemLink id="interface" />, що передає та отримує речі з [мережевого сховища](../ae2-mechanics/import-export-storage.md), <ItemLink id="level_emitter" />, що зчитує вміст мережевого сховища, <ItemLink id="drive" />, що є мережевим сховищем тощо) фізичне розташування пристрою не має значення.

Повторюємо, **фізичне розташування пристрою не має значення**. Важливо лише те, що пристрій підключений до мережі (і, звичайно, до якої саме мережі).

## Мережеві з'єднання

Простий спосіб визначити, що приєднано до мережі — це використати <ItemLink id="network_tool" />. Він покаже всі компоненти в мережі, тож якщо ви бачите те, чого не повинні бачити, або не бачите те, що повинні бачити, у вас є проблема.

Наприклад, це 2 окремі мережі:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Мережа 1
  </BoxAnnotation>

<BoxAnnotation color="#5CA7CD" min="2 0 0" max="3 2 2">
        Мережа 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Це також 2 окремі мережі, оскільки <ItemLink id="quartz_fiber" /> ділиться [енергією](../ae2-mechanics/energy.md) без надання мережевого з'єднання:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/2_networks_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1 2 2">
        Мережа 1
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="1.3 0 0" max="3 2 2">
        Мережа 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Однак це лише 1 мережа, а не 2 окремі. [Квантовий міст](../items-blocks-machines/quantum_bridge.md) діє як бездротовий [щільний кабель](../items-blocks-machines/cables.md#dense-cable), тому обидва кінці знаходяться в одній мережі:

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="7 3 3">
        Єдина мережа
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Це також лише 1 мережа, оскільки колір [кабелю](../items-blocks-machines/cables.md) не має нічого спільного з мережевими з'єднаннями, окрім того, що кабелі різних кольорів не з'єднуються між собою. При цьому всі кольори з'єднуються з флюїксовими кабелями (незабарвленими):

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/actually_1_network_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Єдина мережа
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## З'єднання в контексті підмереж

[Підмережі](../ae2-mechanics/subnetworks.md) використовують мережеві з'єднання (а саме **відсутність** з'єднання) для обмеження доступу [пристроїв](../ae2-mechanics/devices.md) до інших пристроїв.

Насправді підмережа — це окрема мережа.

Наприклад, візьмемо [автоматичний удачливий руйнівник руди](../example-setups/ore-fortuner.md). Тут є 3 окремі мережі, кожна з яких виконує певну функцію в цій конфігурації:

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/ore_fortuner.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 2" max="3 1 3">
        Мережа 1, що діє як підмережа труб, обмежує доступ імпортної шини, щоб вона «зберігала» блоки руди через площини формування.
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="0 0 0" max="3 1 1">
        Мережа 2, діє як інша підмережа труби, обмежує доступ площин анігіляції, щоб вони зберігали шматки руди в бочці, а не в вашій основній мережі. Це також означає, що вони не використовують жодних каналів в основній мережі.
  </BoxAnnotation>

  <BoxAnnotation color="#82CD5C" min="2 0 1" max="4 1 2">
        Мережа 3, основна мережа, на якій знаходиться все ваше сховище та крафти. Вона існує лише для постачання енергії і, зокрема, *не* підключена до 2 підмереж.
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## З'єднання в контексті P2P

Один з варіантів [P2P-тунелю](../items-blocks-machines/p2p_tunnels.md) переміщує [канали](channels.md) замість предметів, рідин або редстоунових сигналів, і це з якоїсь причини плутає людей. Мережа, до якої підключений тунель, не має нічого спільного з мережею, яку тунель передає. Вони *можуть* бути однією мережею, але це не обов'язково, і зазвичай не так:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_channels_network_connection.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1.98 2 1">
        Мережа 1, мережа, що передається (зазвичай ваша основна мережа)
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="2.02 0 0" max="3.98 1 1">
        Мережа 2, мережа, що працює з ME P2P тунелями (зазвичай *не* ваша основна мережа)
  </BoxAnnotation>

  <BoxAnnotation color="#915dcd" min="4.02 0 0" max="6 1 1">
        Мережа 1, мережа, що передається (зазвичай ваша основна мережа)
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Менш інтуїтивні з'єднання

У цьому випадку це лише єдина мережа, оскільки <ItemLink id="pattern_provider" /> є блокоподібним пристроєм, він діє як кабель, та <ItemLink id="inscriber" /> виконує подібну функцію. Таким чином, мережеве з'єднання проходить через постачальника та штампувальника:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_1.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="4 2 2">
        Єдина мережа
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Щоб запобігти цьому (корисно для багатьох налаштувань автовироблення, що включають [підмережі](../ae2-mechanics/subnetworks.md)), ви можете клацнути ПКМ по постачальнику, використовуючи <ItemLink id="certus_quartz_wrench" />, щоб зробити його спрямованим, і в цьому випадку він не буде пропускати канали через лицьовий бік.

<Row gap="40">
<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_network_connection_2.snbt" />

  <BoxAnnotation color="#915dcd" min="0 0 0" max="1.98 2 2">
        Мережа 1
  </BoxAnnotation>

  <BoxAnnotation color="#5CA7CD" min="2.02 0 0" max="4 2 2">
        Мережа 2
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/pattern_provider_directional_connection.snbt" />

  <BoxAnnotation color="#ee3333" min="1 .3 .3" max="1.3 .7 .7">
        Зверніть увагу, що кабель не підключається
  </BoxAnnotation>

  <IsometricCamera yaw="255" pitch="30" />
</GameScene>
</Row>

Інші частини, які не забезпечують спрямовані мережеві з'єднання, є в основному [кабельними](../ae2-mechanics/cable-subparts.md) [пристроями](../ae2-mechanics/devices.md), як <ItemLink id="import_bus" />, <ItemLink id="storage_bus" />, та <ItemLink id="cable_interface" />.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/subpart_no_connection.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>