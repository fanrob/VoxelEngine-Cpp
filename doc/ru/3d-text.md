# 3D Текст

2D текст отображаемый в 3D пространстве.

Вид 3D текста, как и [частицы](particles.md), настраивается через таблицу, все поля которой опциональны.

| Поле            | Описание                                                | По-умолчанию      |
| --------------- | ------------------------------------------------------- | ----------------- |
| display         | Формат отображения                                      | static_billboard  |
| color           | Цвет текста                                             | {1, 1, 1, 1}      |
| scale           | Масштаб                                                 | 1                 |
| renderDistance  | Дистанция отрисовки текста                              | 32                |
| xray_opacity    | Коэффициент видимости через препятствия (просвечивание) | 0                 |
| perspective     | Коэффициент перспективы                                 | 1                 |

Доступные форматы отображения:

| Формат            | Описание                                                          |
| ----------------- | ----------------------------------------------------------------- |
| static_billboard  | Простой 3D текст в мире с ручным управлением размером и вращением |
| y_free_billboard  | Свободно вращающийся по оси Y текст, направляющийся на камеру     |
| xy_free_billboard | Свободно вращающийся текст, направляющийся на камеру              |
| projected         | Проецируемый текст (отображается в экранной системе координат)    |

## Библиотека *gfx.text3d*

```lua
gfx.text3d.show(
    -- позиция текста
    position: vec3,
    -- отображаемый текст
    text: str,
    -- таблица настроек отображение текста
    preset: table,
    -- дополнительная таблица настроек отображения текста
    [опционально] extension: table
) -> int
```

Создаёт 3D текст, возвращая его id.

```lua
gfx.text3d.hide(id: int)
```

Удаляет 3D текст.

```lua
gfx.text3d.get_text(id: int) -> str
gfx.text3d.set_text(id: int, text: str)
```

Геттер и сеттер текста.

```lua
gfx.text3d.get_pos(id: int) -> vec3
gfx.text3d.set_pos(id: int, pos: vec3)
```

Геттер и сеттер позиции текста.

```lua
gfx.text3d.get_axis_x(id: int) -> vec3
gfx.text3d.set_axis_x(id: int, pos: vec3)
```

Геттер и сеттер вектора X.

```lua
gfx.text3d.get_axis_y(id: int) -> vec3
gfx.text3d.set_axis_y(id: int, pos: vec3)
```

Геттер и сеттер вектора Y.

```lua
gfx.text3d.set_rotation(id: int, rotation: mat4)
```

Устанавливает вращение текста (Устанавливает повернутые вектора X,Y).

```lua
gfx.text3d.update_settings(id: int, preset: table)
```

Обновляет настройки отображения текста.