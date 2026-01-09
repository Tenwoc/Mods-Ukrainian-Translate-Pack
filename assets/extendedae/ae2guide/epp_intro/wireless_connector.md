---
navigation:
    parent: epp_intro/epp_intro-index.md
    title: ME Бездротовий сполучник
    icon: extendedae:wireless_connect
categories:
- extended devices
item_ids:
- extendedae:wireless_connect
- extendedae:wireless_tool
---

# ME Бездротовий сполучник

<Row gap="20">
<BlockImage id="extendedae:wireless_connect" scale="6"></BlockImage>
<ItemImage id="extendedae:wireless_tool" scale="6"></ItemImage>
</Row>

ME Бездротовий сполучник може поєднувати між собою дві мережі, як це робить <ItemLink id="ae2:quantum_link" />, але має обмежену дистанцію та не може проходити крізь виміри. ME Бездротовий сполучник підтримує лише зв'язки від-один-до-одного, для від-кількох-до-кількох сполучень вам потрібно використовувати <ItemLink id="extendedae:wireless_hub" />.

## Зв'язування бездротових сполучників

Застосуйте МЕ Набір створення бездротового зв'язку на двох сполучниках, щоб зв'язати їх.

Застосуйте пристрій крадькома, щоб очистити його прив'язки.

Після вдалого сполучення ME Бездротовий сполучник змінить свою текстуру.

Незв'язані бездротові сполучники

<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_off.snbt"></ImportStructure>
</GameScene>

Сполучені бездротові сполучники

<GameScene zoom="5" background="transparent">
  <ImportStructure src="../structure/wireless_connector_on.snbt"></ImportStructure>
</GameScene>

## Колір

Бездротові сполучники можна фарбувати так само як кабелі, і з'єднувати лише кабелі/роз'єми одного кольору.

Вам потрібен <ItemLink id="ae2:color_applicator" />, щоб пофарбувати сполучник.

Таким чином ви можете розподіляти свої бездротові роз'єми ось так:

<GameScene zoom="3" background="transparent" interactive={true}>
  <ImportStructure src="../structure/wireless_connector_setup.snbt"></ImportStructure>
</GameScene>

## Споживання енергії

МЕ Бездротові сполучники споживають більше енергії, коли знаходяться далі один від одного. Крива залежності вартості від відстані нелінійна, тому вартість енергії може бути дуже високою, якщо вони знаходяться занадто далеко один від одного.

<ItemLink id="ae2:energy_card" /> може допомогти зекономити споживання енергії, кожна карта може зменшити витрати на 10%.

