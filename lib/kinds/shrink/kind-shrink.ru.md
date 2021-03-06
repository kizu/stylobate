---
---

## Схлопывание

Тип схлопывания полезен если нужно от какого-то блока с контентом «отъедать» ширину другими блоками, расположенными слева/справа.

По сути это всего лишь враппер над поведением флоатов, включающий в себя клерфикс и дополнительные правки для инлайнового поведения.

Основным типом — `shrink` — отмечается блок, который нужно схлопывать:

    kind: shrink

Если для текста внутри этого блока нужно отображать многоточие при обрезании, достаточно добавить тип `ellipsis`:

    kind: shrink, ellipsis

Если схлопывающийся блок хочется сделать инлайновым, надо добавить параметр `inline`:

    kind: shrink inline

Если вы делаете блок инлайновым или вам просто нужно его заклирить, нужно обернуть этот блок в `shrink-wrap`:

    kind: shrink-wrap

или

    kind: shrink-wrap inline

Теперь нужно присвоить подтипы для блоков, которые, собственно, будут отъедать место от основного блока. Это подтипы `shrink-left` и `shrink-right`.

Важный момент: в DOM эти блоки должны идти **до** блока с `kind: shrink`, иначе магия не сработает.

    kind: shrink-left

    kind: shrink-right
