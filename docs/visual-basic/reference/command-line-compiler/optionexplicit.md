---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266733"
---
# <a name="-optionexplicit"></a>-optionexplicit
Заставляет компилятор сообщать об ошибках, если переменные не объявляются до их использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный элемент. Чтобы сделать явное объявление переменных обязательным, укажите `-optionexplicit+`. Параметр `-optionexplicit+` используется по умолчанию и аналогичен параметру `-optionexplicit`. Используйте параметр `-optionexplicit-`, чтобы разрешить неявное объявление переменных.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), этот оператор переопределяет параметр компилятора командной строки `-optionexplicit`.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Как задать параметр -optionexplicit в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в поле **Option Explicit**.  
  
## <a name="example"></a>Пример  
 Следующий код компилируется, когда используется параметр `-optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
