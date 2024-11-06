# Библиотека *rules*

```lua
rules.create(
    -- имя правила
    name: str,
    -- значение по-умолчанию
    default: bool,
    -- функция-обработчик изменения значения
    [опционально] handler: function
) -> int
```

Создаёт правило. Если указан обработчик, возвращает id для возможности удаления.

> [!NOTE]
> Созданием правила считается вызов rules.create с назначением значения по-умолчанию.
> Не созданные правила могут быть использованы, но сброс через rules.reset приведёт
> к установке значения nil.

```lua
rules.listen(
    -- имя правила
    name: str,
    -- функция-обработчик изменения значения
    handler: function
) -> int
```

Добавляет обработчик изменения значения правила. 
Возвращает id для возможности удаления.
Также позволяет подписаться на правило до его создания.

```lua
rules.unlisten(name: str, id: int)
```

Удаляет обработчик правила по id, если он существует.

```lua
rules.get(name: str) -> bool | nil
```

Возвращает значение правила или nil, если оно ещё не было создано.

```lua
rules.set(name: str, value: bool)
```

Устанавливает значение правила, вызывая обработчики. Может использоваться и
до создания правила.

```lua
rules.reset(name: str)
```

Сбрасывает значение правила к значению по-умолчанию.


## Стандартные правила


| Имя                  | Описание                                                        | По-умолчанию |
| -------------------- | --------------------------------------------------------------- | ------------ |
| cheat-commands       | Разрешить команды, имена которых есть в массиве console.chears. | true         |
| allow-content-access | Разрешить панель доступа к контенту.                            | true         |
| allow-flight         | Разрешить полёт                                                 | true         |
| allow-noclip         | Разрешить включение noclip.                                     | true         |
| allow-attack         | Разрешить атаковать сущности.                                   | true         |
| allow-destroy        | Разрешить разрушение блоков.                                    | true         |
| allow-cheat-movement | Разрешить специальные клавиши быстрого перемещения.             | true         |
| allow-debug-cheats   | Разрешить нечестные элементы управления на дебаг-панели.        | true         |