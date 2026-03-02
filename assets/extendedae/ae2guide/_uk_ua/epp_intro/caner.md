---
navigation:
  parent: epp_intro/epp_intro-index.md
  title: ME Герметизатор
  icon: extendedae:caner
categories:
  - extended devices
item_ids:
  - extendedae:caner
---

# ME Герметизатор

<BlockImage id="extendedae:caner" scale="8"></BlockImage>

ME Герметизатор – це машина, яка «консервує» речі, включаючи рідини, гази Mekanism, ману Botania та навіть енергію!

Перший слот призначений для речовини до наповнення, а другий – для контейнера до цієї речовини.

Для роботи потрібна енергія, і кожна операція коштує 80 AE.

![GUI](../pic/caner_gui.png)

Усталено він наповнює лише рідини, але зі встановленням аддонів він буде здатний наповнювати й інші речовини.

### Підтримувані аддони:

- Applied Flux
- Applied Mekanistics
- Applied Botanics Addon

## Автовироблення із МЕ Герметизатором

Тільки верхня та нижня сторони можуть приймати енергію та підключатися до мережі.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/caner_example.snbt"></ImportStructure>
</GameScene>

Проста устава для герметизатора. ME Герметизатор автоматично вилучить заповнений предмет, коли <ItemLink id="ae2:pattern_provider" /> передасть йому складники.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../structure/caner_auto.snbt"></ImportStructure>
</GameScene>

Шаблон повинен містити лише речі до наповнення та контейнер, який потрібно наповнити. Ось кілька прикладів:

Наповнення відра водою:

![P1](../pic/fill_water.png)

Підзарядка планшета енергії (з аддоном Applied Flux):

![P1](../pic/fill_energy.png)

## Спорожнення

ME Герметизатор також може зливати речі з контейнерів в режимі спорожнювання — для цього вам потрібно у шаблоні поміняти місцями складники та результат.
