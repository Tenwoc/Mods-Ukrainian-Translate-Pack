---
navigation:
  title: "Великий акумулятор"
  icon: "yet_another_industrialization:large_storage_unit"
  position: 1
  parent: yet_another_industrialization:utilities.md
item_ids:
  - yet_another_industrialization:large_storage_unit
  - yet_another_industrialization:large_storage_unit_input_hatch
  - yet_another_industrialization:large_storage_unit_output_hatch
---

# Великий резервуар

###### _Це та сама Жадібність, про яку говорять у Біблії, знаєш?_

<GameScene zoom="3" interactive={true} fullWidth={true}>
    <MultiblockShape controller="yet_another_industrialization:large_storage_unit" />
</GameScene>

Великі акумулятори здатні зберігати у вісім разів більше, ніж акумулятори їхньої напруги. Це дуже багато!

На відміну від інших електричних машин, великі акумулятори можуть вводити/виводити енергію на своїй напрузі та нижчих. Наприклад, на HV вони можуть працювати з іншими машинами на своїй напрузі, та на додаток із MV та LV. Трансформатори не потрібні.

<Recipe id="yet_another_industrialization:craft/large_storage_unit" />

<Recipe id="yet_another_industrialization:materials/battery_alloy/craft/machine_casing" />

Введення/виведення енергії відбувається через спеціальні роз'єми:

<Recipe id="yet_another_industrialization:craft/large_storage_unit_input_hatch" />

<Recipe id="yet_another_industrialization:craft/large_storage_unit_output_hatch" />
