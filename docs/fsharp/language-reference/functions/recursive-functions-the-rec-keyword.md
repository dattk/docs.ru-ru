---
title: 'Рекурсивные функции: Ключевое слово REC'
description: Узнайте, как F# ключевое слово "REC" используется с ключевым словом let для определения рекурсивной функции.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630649"
---
# <a name="recursive-functions-the-rec-keyword"></a>Рекурсивные функции: Ключевое слово REC

Ключевое слово используется вместе `let` с ключевым словом для определения рекурсивной функции. `rec`

## <a name="syntax"></a>Синтаксис

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Примечания

Рекурсивные функции, которые вызывают сами себя, определяются явным образом на F# языке. Это делает определяемый идентификатор доступным в области действия функции.

В следующем коде показана рекурсивная функция, которая выполняет вычисление *n*-<sup>го</sup> числа Фибоначчи.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> На практике код, подобный приведенному выше, — непроизводительна памяти и процессорного времени, так как он включает перерасчет ранее вычисленных значений.

Методы неявно являются рекурсивными в пределах типа; нет необходимости добавлять `rec` ключевое слово. Привязки let в классах не являются неявно рекурсивными.

## <a name="mutually-recursive-functions"></a>Взаимные рекурсивные функции

Иногда функции являются *взаимно рекурсивными*, то есть вызывают форму круга, где одна функция вызывает другую, которая, в свою очередь, вызывает первую, с любым числом вызовов между. Необходимо определить такие функции вместе в одной `let` привязке, `and` используя ключевое слово, чтобы связать их вместе.

В следующем примере показаны две взаимно рекурсивные функции.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>См. также

- [Функции](index.md)
