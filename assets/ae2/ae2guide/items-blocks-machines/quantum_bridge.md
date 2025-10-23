---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Квантовий міст
  icon: quantum_ring
  position: 110
categories:
- network infrastructure
item_ids:
- ae2:quantum_link
- ae2:quantum_ring
---

# Квантовий мережевий міст

![Сформований квантовий мережевий міст](../assets/diagrams/quantum_bridge_demonstration.png)

Квантові мережеві мости можуть розширювати [мережу](../ae2-mechanics/me-network-connections.md) на нескінченні відстані й навіть між вимірами. Вони можуть передавати загалом 32 канали (незалежно від того, як кабелі підключені до кожної грані), в сутності діючи як бездротовий [щільний кабель](cables.md#щільний-кабель).

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_1.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/quantum_bridge_internal_structure_2.snbt" />

  <BoxAnnotation color="#33dd33" min="1 1 1" max="6 2 3">
        Уявний кабель між двома кінцевими точками
  </BoxAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Зверніть увагу, що **обидві сторони мають перебувати у завантажених чанках**, тому необхідно використовувати <ItemLink id="spatial_anchor" /> або інший завантажувач чанків, якщо 2 сторони знаходяться далеко одна від одної.

# Квантове кільце

<BlockImage id="quantum_ring" scale="8" />

Вісім таких блоків, розміщених навколо камери квантового зв'язку створять квантовий мережевий міст. Тільки 4 блоки квантового кільця, що прилягають до камери квантового зв'язку прийматимуть мережеві з'єднання, 4 кутові блоки не можуть підключатися до кабелів.

## Рецепт

<RecipeFor id="quantum_ring" />

# Камера квантового зв'язку

<BlockImage id="quantum_link" scale="8" />

Цей блок, оточений квантовим кільцем, створить квантовий мережевий міст. Цей блок не підключається до жодних кабелів і реєструється лише як частина мережі, коли створено повний міст.

В інвентар цього блоку вміщується лише одна <ItemLink id="quantum_entangled_singularity" />. Цей слот також доступний для автоматизації.

## Рецепт

<RecipeFor id="quantum_link" />
