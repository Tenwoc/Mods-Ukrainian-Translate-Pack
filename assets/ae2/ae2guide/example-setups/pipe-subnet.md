---
navigation:
  parent: example-setups/example-setups-index.md
  title: Трубні преметні/рідинні підмережі
  icon: storage_bus
---

# Предметна/рідинна «трубна» мережа

Простий метод переміщення предметів та/або рідин трубами за допомогою AE2 [пристроїв](../ae2-mechanics/devices.md), корисний для, ну, будь-чого, для чого ви використовуєте предметну або рідинну трубу. Це включає повернення результатів вироблення у <ItemLink id="pattern_provider" />.

Загалом існує два різних методи досягнення цього:

## Шина імпорту -> Шина зберігання

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Шина імпорту: Можна відфільтрувати.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Шина зберігання: Можна відфільтрувати. Ця (та інші шини зберігання, які ви хочете використовувати як місце призначення) має бути єдиним сховищем у мережі.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Джерело
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Місце призначення
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="import_bus" /> (1) у вихідному містилі імпортує предмети або рідину та намагається зберегти їх у [мережевому сховищі](../ae2-mechanics/import-export-storage.md). Оскільки єдиним сховищем у мережі є <ItemLink id="storage_bus" /> (2) (саме тому це підмережа, а не ваша основна мережа), предмети або рідина розміщуються в цільовому містилі, таким чином переміщуючись. Енергія постачається через <ItemLink id="quartz_fiber" />. Як шину імпорту, так і шину зберігання можна фільтрувати, але система передасть усе, до чого вона може отримати доступ, якщо не застосовано жодних фільтрів. Ця система також працює з кількома шинами імпорту та кількома шинами зберігання.

## Шина зберігання -> Шина експорту

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        (1) Шина зберігання: Можна відфільтрувати. Ця (та інші шини зберігання, які ви хочете використовувати як джерело) має бути єдиним сховищем у мережі.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        (2) Шина експорту: Повинна бути відфільтрована.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#00ff00">
        Джерело
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#00ff00">
        Місце призначення
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="export_bus" /> в цільовому містилі намагається витягнути відфільтровані предмети з [мережевого сховища](../ae2-mechanics/import-export-storage.md). Оскільки єдиним сховищем у мережі є <ItemLink id="storage_bus" /> (саме тому це підмережа, а не ваша основна мережа), предмети або рідина витягуються з вихідного містила, таким чином передаються. Енергія постачається через <ItemLink id="quartz_fiber" />. Шини експорту обов'язково повинні бути відфільтрованими. Ця схема також працює з кількома шинами зберігання та кількома шинами експорту.

## Схема, яка не працює (Шина імпорту -> Шина експорту)

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_export_pipe.snbt" />

<BoxAnnotation color="#dd3333" min="3.7 0 0" max="4 1 1">
        Шина імпорту: Оскільки мережа не має сховища, їй нікуди імпортувати.
  </BoxAnnotation>

<BoxAnnotation color="#dd3333" min="1 0 0" max="1.3 1 1">
        (2) Шина експорту: Оскільки мережа не має сховища, їй нікуди експортувати.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 0.5" color="#ff0000">
        Джерело
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 0.5" color="#ff0000">
        Місце призначення
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

Схема лише з шиною імпорту та експорту не працюватиме. Шина імпорту спробує витягнути предмети або рідину з вихідного містила та зберегти їх у мережевому сховищі. Шина експорту спробує витягнути предмети або рідину з мережевого сховища та помістити їх у цільове містило. Однак, оскільки ця мережа **не має сховища**, шина імпорту не може імпортувати, а шина експорту не може експортувати, тому нічого не відбудеться.

## Введення та виведення через 1 грань

Припустимо, у вас є машина, яка може отримувати складники та виводити результати через 1 грань. (Наприклад <ItemLink id="charger" />) Ви можете як вводити складники, так і виводити результат, комбінуючи методи 2 трубної підмережі:

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/import_storage_export_pipe.snbt" />

<BoxAnnotation color="#dddddd" min="4 1 1" max="5 1.3 2">
        (1) Шина імпорту: Можна відфільтрувати.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 1 1" max="3 1.3 2">
        (2) Шина зберігання: Можна відфільтрувати. Ця (та інші шини сховища, на які ви хочете вставляти та витягувати предмети) має бути єдиним сховищем у мережі.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="2 0 1" max="3 1 2">
        (3) Річ, в яку ви хочете вводити та звідки витягувати: У цьому випадку зарядний пристрій.
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 1" max="1 1.3 2">
        (4) Шина експорту: Повинна бути відфільтрована.
  </BoxAnnotation>

<DiamondAnnotation pos="4.5 0.5 1.5" color="#00ff00">
        Джерело
    </DiamondAnnotation>

<DiamondAnnotation pos="0.5 0.5 1.5" color="#00ff00">
        Місце призначення
    </DiamondAnnotation>

  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Інтерфейси

Виявляється, що окрім шин імпорту та експорту, існують [пристрої](../ae2-mechanics/devices.md) які теж здатні воодити предмети в [мережеве сховище](../ae2-mechanics/import-export-storage.md) та виводити їх з нього! Тут важливим є <ItemLink id="interface" />. Якщо вставлено предмет, інтерфейс, не налаштований на запасання, завантажить його в мережеве сховище, що ми можемо використовувати аналогічно до каналу «шина імпорту -> шина зберігання». Встановлення інтерфейсу на запасання певного предмета призведе до його вилучення з мережевого сховища, подібно до каналу «шина зберігання -> шина експорту». Інтерфейси можна налаштувати на запасання одних предметів, та залишити для забирання інших, що дозволить вам дистанційно завантажувати та витягувати їх через шини зберігання, якщо ви з якоїсь причини хочете це зробити.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/interface_pipes.snbt" />

<BoxAnnotation color="#dddddd" min="3.7 0 0" max="4 1 1">
        Інтерфейс
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 1">
        Шина зберігання
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="3.7 0 2" max="4 1 3">
        Шина зберігання
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 1 2" max="1 1.3 3">
        Інтерфейс
  </BoxAnnotation>

<IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Один до багатьох та багато до одного (і багато до багатьох)

Звичайно, вам не потрібно використовувати виключно одну <ItemLink id="import_bus" />, <ItemLink id="export_bus" /> чи <ItemLink id="storage_bus" />

<GameScene zoom="3" background="transparent">
<ImportStructure src="../assets/assemblies/many_to_many_pipe.snbt" />

<IsometricCamera yaw="185" pitch="30" />
</GameScene>

## Постачання складників у декілька місць

З усього цього ми можемо вивести метод для надсилання складників з однієї грані <ItemLink id="pattern_provider" /> до багатьох різних місць, наприклад, масиву машин або кількох різних граней однієї машини.

Нам не потрібна труба «імпорт -> сховище» або «сховище -> експорт», оскільки <ItemLink id="pattern_provider" /> насправді ніколи не містить складників. Натомість постачальники _виводять_ складники до прилеглих містил напряму з мережевого сховища, тому нам потрібно буферне містило, яке також може імпортувати предмети.

Це звучить як... <ItemLink id="interface" />! Переконайтеся, що постачальник знаходиться в спрямованому режимі спрямованої або у вигляді кабельного компонента та/або інтерфейс знаходиться у вигляді кабельного компонента, щоб вони не утворювали мережеве з'єднання.

<GameScene zoom="6" background="transparent">
<ImportStructure src="../assets/assemblies/provider_interface_storage.snbt" />

<BoxAnnotation color="#dddddd" min="2.7 0 1" max="3 1 2">
        Інтерфейс (має бути пласким, а не блокоподібним)
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="1 0 0" max="1.3 1 4">
        Шини зберігання
  </BoxAnnotation>

<BoxAnnotation color="#dddddd" min="0 0 0" max="1 1 4">
        Місця, куди ви хочете надавати шаблони (кілька машин або кілька граней однієї машини)
  </BoxAnnotation>

<IsometricCamera yaw="185" pitch="30" />
</GameScene>
