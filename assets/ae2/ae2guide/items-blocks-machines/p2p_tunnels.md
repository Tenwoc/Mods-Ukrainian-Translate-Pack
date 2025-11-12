---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: P2P Тунелі
  icon: me_p2p_tunnel
  position: 210
categories:
- devices
item_ids:
- ae2:me_p2p_tunnel
- ae2:redstone_p2p_tunnel
- ae2:item_p2p_tunnel
- ae2:fluid_p2p_tunnel
- ae2:fe_p2p_tunnel
- ae2:light_p2p_tunnel
---

# Тунелі Точка-До-Точки

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

P2P-тунелі – це спосіб переміщення таких речей, як предмети, рідини, редстоунові сигнали, енергія, світло та [канали](../ae2-mechanics/channels.md) мережею без їхньої безпосередньої взаємодії з мережею. Існує багато варіантів P2P-тунелів, але кожен з них транспортує лише свій специфічний тип речей. Вони по суті діють як портали, які безпосередньо з'єднують дві грані блоків на відстані. Вони не є двонаправленими, мають визначені входи та виходи.

![Портал](../assets/assemblies/p2p_portal.png)

Наприклад, лійка, що стоїть навпроти предметного P2P, діятиме так, ніби вона безпосередньо підключена до бочки, і передавати у неї предмети.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_hopper_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Відповідно, дві бочки поруч одна з одною не передаватимуть предмети між собою.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_barrel_barrel.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Існують також інші варіанти, такі як редстоуновий P2P.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_redstone.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Та МЕ P2P, який переміщує канали.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_channels.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Типи P2P-тунелів та їхнє налаштування

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_tunnels.snbt" />
  <IsometricCamera yaw="180" pitch="90" />
</GameScene>

Існує багато типів P2P-тунелів. Тільки тунель МЕ P2P можна створити безпосередньо, інші створюються клацанням ПКМ по тунелях P2P певними предметами:
- МЕ P2P тунелі вибираються клацанням ПКМ будь-яким [кабелем](../items-blocks-machines/cables.md).
- Редстоунові P2P тунелі вибираються клацанням ПКМ різними редстоуновими компонентами.
- Предметні P2P тунелі вибираються клацанням ПКМ скринею або лійкою.
- Рідкі P2P тунелі вибираються клацанням ПКМ відром або пляшкою.
- Енергетичні P2P тунелі вибираються клацанням ПКМ майже будь-яким енергомістким предметом.
- Світлові P2P тунелі вибираються клацанням ПКМ смолоскипом або світлокаменем.

Деякі типи тунелів мають особливості. Наприклад, канали МЕ P2P тунелів не можуть вкладатися в інші МЕ P2P тунелі, а енергетичні P2P тунелі опосередковано споживають 2,5% FE, що протікає через них, збільшуючи споживання [енергії](../ae2-mechanics/energy.md) draw.

## Найпоширеніша форма використання P2P

Найпоширенішим випадком використання P2P тунелів є використання МЕ P2P тунелю для зменшення щільності транспортування [каналів](../ae2-mechanics/channels.md). Замість пучка щільного кабелю, для передачі багатьох каналів можна використовувати один щільний кабель.

У цьому прикладі 8 входів МЕ P2P приймають 256 каналів (8*32) з контролера основної мережі, а 8 виходів МЕ P2P виводять їх кудись ще. Зверніть увагу, як кожен вхід або вихід тунелю P2P приймає 1 канал. Таким чином, ми можемо прокласти багато каналів через тонкий кабель. А оскільки наші P2P-тунелі знаходяться у виділеній [підмережі](../ae2-mechanics/subnetworks.md), ми навіть не використовуємо жодних каналів з основної мережі для цього! Також зверніть увагу, що хоча P2P-тунелі можна розмістити безпосередньо біля контролера, між ними можна розмістити [щільний розумний кабель](../items-blocks-machines/cables.md#розумний-кабель) для легшої візуалізації каналів.

<GameScene zoom="4" interactive={true}>
  <ImportStructure src="../assets/assemblies/p2p_compact_channels.snbt" />

  <BoxAnnotation color="#dddddd" min="1.3 1.3 6.3" max="2 2.7 6.7">
        Кварцове волокно розподіляє енергію між основною мережею та підмережею P2P.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="4.1 0 5.7" max="5 2.3 6.4">
        Ви можете або розмістити вхід тунелю безпосередньо на контролері, або під'єднати до нього кабель.
  </BoxAnnotation>

  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

Для іншого прикладу (включно з його використанням з [квантових мостів](quantum_bridge.md)) дивіться цю діаграму MS Paint, над якою я дуже старався:

![P2P and quantum bridges](../assets/diagrams/p2p_quantum_network.png)

## Вкладення

Ви не можете використовувати це для надсилання нескінченної кількості каналів через один кабель. Канал для МЕ P2P тунелю не проходитиме через інший тунель МЕ P2P, тому ви не можете рекурсивно вкладати їх. Однак спостерігайте, як зовнішній шар МЕ P2P тунелів на червоних кабелях не працює. Зверніть увагу, що це стосується лише МЕ P2P тунелів, інші типи P2P тунелів можуть проходити через МЕ P2P тунель, як видно з редстоуновим P2P тунелем, який працює нормально.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_nesting.snbt" />
  <IsometricCamera yaw="225" pitch="30" />
</GameScene>

## Зв'язування

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/p2p_linking_frequency.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Кінці P2P тунелю можна з'єднати, використовуючи <ItemLink id="memory_card" />. Частота буде відображатися як масив кольорів 2x2 на задній стороні тунелю.
- Клацніть ПКМ крадькома, щоб створити нову частоту зв'язку P2P.
- Клацніть ПКМ, щоб вставити налаштування, карти модифікаторів або частоту зв'язку.

Тунель, на якому ви клацнете ПКМ крадькома, буде входом, а тунель, на якому ви клацнете ПКМ, буде виходом. Ви можете мати кілька виходів, але з МЕ P2P тунелями канали, що проходять через вхід, будуть розділені між виходами, тому ви не зможете дублювати канали.

## Рецепт

<RecipeFor id="me_p2p_tunnel" />