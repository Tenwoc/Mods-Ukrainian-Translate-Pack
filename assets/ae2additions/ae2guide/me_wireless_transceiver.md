---
navigation:
    title: МЕ Бездротовий передавач
    parent: aeadditions.md
item_ids:
  - ae2additions:me_wireless_transceiver
---
# МЕ Бездротовий передавач

## Для чого це?

Цей блок дозволяє вам бездротово розширити вашу мережу на будь-яку відстань, але не за межі вимірів. Передавачі можуть передавати загалом 32 канали. Чим далі ви розміщуєте їх один від одного, тим вище їхнє енергоспоживання.

Що відрізняє його від квантового мосту, так це те, що ви можете прив'язати передавачі до іменованого каналу. Після того як передавач прив'язаний до каналу як роздавач, ви можете приєднатися до цього каналу на через будь-який передавач, який вам потрібен, у тому ж вимірі.

Якщо ви хочете розширити мережу за межі виміру, вам слід використовувати квантовий міст.

![](assets/wirelesstransceiver/transceiver_diagram.png)

# Базова установка

<GameScene zoom="4" interactive={true}>
    <ImportStructure src="assets/wirelesstransceiver/basic_setup.snbt" />
    <BoxAnnotation color="#dddddd" min="6 0 7" max="7 1 6">
        Цей передавач налаштовано як передавач:

        ![](assets/wirelesstransceiver/basic_setup_broadcaster.png)
    </BoxAnnotation>

    <BoxAnnotation color="#dddddd" min="10 0 7" max="11 1 6">
        Цей передавач налаштовано як отримувач:

        ![](assets/wirelesstransceiver/basic_setup_subscriber.png)
    </BoxAnnotation>
    <BoxAnnotation color="#dddddd" min="10.1 1.1 6.1" max="10.9 1.9 6">
        Цей термінал тепер підключено до контролера, за умови, що живлення подається, і максимальна кількість каналів не зайнята.
    </BoxAnnotation>
</GameScene>


# Рецепт
<RecipeFor id="me_wireless_transceiver"/>