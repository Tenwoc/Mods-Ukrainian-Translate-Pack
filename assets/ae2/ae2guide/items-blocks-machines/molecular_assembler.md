---
navigation:
  parent: items-blocks-machines/items-blocks-machines-index.md
  title: Молекулярний збирач
  icon: molecular_assembler
  position: 310
categories:
- machines
item_ids:
- ae2:molecular_assembler
---

# Молекулярний збирач

<BlockImage id="molecular_assembler" scale="8" />

Молекулярний збирач приймає вхідні предмети та виконує операції, йому які може визначати <ItemLink id="pattern_provider" /> або вставлені напряму <ItemLink id="crafting_pattern" />, <ItemLink id="smithing_table_pattern" /> та <ItemLink id="stonecutting_pattern" />, а потім передає результат до прилеглих містил.

Цей збирач має шаблон майстрування, який визначає рецепт «1 дубова колода = 4 дубові дошки». Коли дубові колоди подаються через верхню лійку, збирач створює та викидає дубові дошки в нижню лійку.

<GameScene zoom="6" background="transparent">
  <ImportStructure src="../assets/assemblies/standalone_assembler.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Основне використання молекулярного збирача

Однак їх основне використання — поруч із <a href="pattern_provider.md">постачальником шаблонів</a>. Постачальники шаблонів мають особливу поведінку в цьому випадку і надсилають інформацію про відповідний шаблон разом зі складниками до усіх прилеглих збирачів. Оскільки збирачі автоматично виштовхують результати майстрування до прилеглих містил (а отже, і до слотів повернення постачальника шаблонів), для автоматизації шаблонів майстрування достатньо лише розмістити збирач на постачальнику шаблонів.

<GameScene zoom="4" background="transparent">
  <ImportStructure src="../assets/assemblies/assembler_tower.snbt" />
  <IsometricCamera yaw="195" pitch="30" />
</GameScene>

## Модифікатори

Молекулярний збирач підтримує такі [модифікатори](upgrade_cards.md):

*   <ItemLink id="speed_card" />

## Рецепт

<RecipeFor id="molecular_assembler" />

## Примітка

Optifine порушує функцію «перенесення до прилеглих містил», тому більшість установок майстрування зі збирачами не працюватимуть.