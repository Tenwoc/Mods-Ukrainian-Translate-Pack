---
navigation:
  title: МЕ Бездротовий комунікатор
  parent: aeadditions.md
item_ids:
  - ae2additions:me_wireless_transceiver
---

# МЕ Бездротовий комунікатор

## Для чого це?

Цей блок дозволяє вам розширити вашу мережу на будь-яку відстань без кабелів, але не за межі виміру. Комунікатори можуть передавати до 32 каналів. Чим далі ви розміщуєте їх один від одного, тим вище їхнє енергоспоживання.

На відміну від квантового мосту, комунікатор працює за іменованими каналами. Після того як комунікатор прив'язано до каналу як передавач, ви можете приєднатися до цього каналу через будь-який інший комунікатор у тому ж вимірі.

Якщо ви хочете розширити мережу за межі виміру, вам слід використовувати квантовий міст.

![](assets/wirelesstransceiver/transceiver_diagram.png)

# Базова устава

<GameScene zoom="4" interactive={true}>
    <ImportStructure src="assets/wirelesstransceiver/basic_setup.snbt" />
    <BoxAnnotation color="#dddddd" min="6 0 7" max="7 1 6">
        Цей комунікатор налаштовано як передавач:

        ![](assets/wirelesstransceiver/basic_setup_broadcaster.png)
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="10 0 7" max="11 1 6">
        Цей комунікатор налаштовано як отримувач:

        ![](assets/wirelesstransceiver/basic_setup_subscriber.png)
    </BoxAnnotation>
    <BoxAnnotation color="#dddddd" min="10.1 1.1 6.1" max="10.9 1.9 6">
        Цей термінал тепер підключено до контролера, за умови, що живлення подається, і максимальна кількість каналів не зайнята.
    </BoxAnnotation>

</GameScene>

# Рецепт

<RecipeFor id="me_wireless_transceiver"/>
