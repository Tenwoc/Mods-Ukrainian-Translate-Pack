---
navigation:
  parent: example-setups/example-setups-index.md
  title: Проста ферма істинного кварцу
  icon: certus_quartz_crystal
  position: 110
---

# Проста ферма істинного кварцу

Як згадувалося у розділі [Вирощування істинного кварцу](../ae2-mechanics/certus-growth.md), автоматизація збору <ItemLink id="certus_quartz_crystal" /> включає <ItemLink id="annihilation_plane" /> та <ItemLink id="storage_bus" />. <ItemLink id="growth_accelerator" />s використовуються для значного прискорення росту родючого істинного кварцу, а потім площини руйнують дозрілу <ItemLink id="quartz_cluster" />. Вони фільтруються, використовуючи підозріло щасливу властивість, що незрілі зародки істинного кварцу скидають <ItemLink id="certus_quartz_dust" /> замість того, щоб скидати нічого.

Ця ферма працює повністю автоматично з <ItemLink id="flawless_budding_quartz" />, але у випадку з надщербленим, пошкодженим та дефектним джерелами кварцу, вам доведеться замінювати родючий блок вручну. Або автоматично, як це описано в розділах [Напівавтоматичної ферми істинного кварцу](semiauto-certus-farm.md) та [Вдосконаленої ферми істинного кварцу](advanced-certus-farm.md).

Дивіться [Вирощування істинного кварцу](../ae2-mechanics/certus-growth.md) для отримання орієнтовної швидкості ферми.

<GameScene zoom="6" interactive={true}>
  <ImportStructure src="../assets/assemblies/simple_certus_farm.snbt" />

  <BoxAnnotation color="#dddddd" min="3.7 1 1" max="4 2 2">
        (1) Площина руйнування: Не має інтерфейсу для налаштування, але може бути зачарована Удачею.
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 1" max="3.3 2 2">
        (2) Шина зберігання №1: Відфільтрована на істинний кварц.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

  <BoxAnnotation color="#dddddd" min="3 1 .7" max="2 2 1">
        (3) Шина зберігання №2: Відфільтрована на істинний кварц. Має пріоритет, встановлений вище, ніж у основного сховища.
        <ItemImage id="certus_quartz_crystal" scale="2" />
  </BoxAnnotation>

<DiamondAnnotation pos="1 0.5 0.5" color="#00ff00">
        До основної мережі
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Конфігурації

- <ItemLink id="annihilation_plane" /> (1) не має інтерфейсу та не може бути налаштована, але може бути зачарована Удачею.
- Перша <ItemLink id="storage_bus" /> (2) відфільтрована на <ItemLink id="certus_quartz_crystal" />.
- The second <ItemLink id="storage_bus" /> (3) відфільтрована на <ItemLink id="certus_quartz_crystal" />, та її [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ) встановлено вище, ніж у основного сховища.

## Як це працює

1. <ItemLink id="annihilation_plane" /> намагається зламати те, що знаходиться перед нею, але може зламати лише <ItemLink id="quartz_cluster" /> оскільки єдиним сховищем у підмережі є <ItemLink id="storage_bus" />, відфільтрована на <ItemLink id="certus_quartz_crystal" />.
2. Перша <ItemLink id="storage_bus" /> зберігає істинний кварц у діжці.
3. Друга <ItemLink id="storage_bus" /> надає основній мережі доступ до всіх кристалів діжці. Їй встановлено високий [пріоритет](../ae2-mechanics/import-export-storage.md#пріоритет-сховищ), щоб кристали кварцу Certus переважно поверталися назад у діжку, а не у ваше основне сховище.
