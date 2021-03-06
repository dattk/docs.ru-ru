---
title: Вызов функции DLL
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 14589544e05f6c59f4f58f7723fef40e75af9823
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123720"
---
# <a name="calling-a-dll-function"></a>Вызов функции DLL
Хотя вызов неуправляемых функций DLL почти идентичен вызову другого управляемого кода, все же существуют отличия, которые поначалу могут вызвать некоторые сложности в освоении функций DLL. В этом разделе представлены статьи, касающиеся некоторых особенностей вызовов.  
  
 Структуры, возвращаемые из вызовов неуправляемого кода, должны быть типами данных, имеющими одинаковые представления в управляемом и неуправляемом коде. Такие типы называются *непреобразуемыми типами*, так как они не требуют преобразования (см. раздел [Непреобразуемые и преобразуемые типы](blittable-and-non-blittable-types.md)). Чтобы вызвать функцию с преобразуемой структурой в качестве ее возвращаемого типа, можно определить непреобразуемый вспомогательный тип того же размера, что и преобразуемый тип, и преобразовать данные после возвращения функции.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Передача структур](passing-structures.md)  
 Описываются вопросы передачи структур данных с предопределенной компоновкой.  
  
 [Функции обратного вызова](callback-functions.md)  
 Основные сведения о функциях обратного вызова.  
  
 [Практическое руководство. Реализация функций обратного вызова](how-to-implement-callback-functions.md)  
 Описывается реализация функций обратного вызова в управляемом коде.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование неуправляемых функций DLL](consuming-unmanaged-dll-functions.md)  
 Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.  
  
 [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md)  
 Описывается способ объявления параметров метода и передачи аргументов в функции, экспортируемые неуправляемыми библиотеками.
