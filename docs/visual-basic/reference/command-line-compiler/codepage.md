---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: a38fb4be9347b3372b4a459fce2e96b9e38c3a51
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343548"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`id`|Обязательный. Компилятор использует кодовую страницу, указанную `id`, для интерпретации кодировки исходных файлов.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы скомпилировать исходный код, сохраненный в определенной кодировке, можно с помощью параметра `-codepage` указать, какую кодовую страницу следует использовать. Параметр `-codepage` применяется ко всем файлам исходного кода, включенным в компиляцию. Дополнительные сведения см. в статье [Кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с использованием текущей кодовой страницы ANSI, Юникода или UTF-8 с сигнатурой. Visual Studio по умолчанию сохраняет все файлы исходного кода с использованием текущей кодовой страницы ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка**. Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с использованием другой кодовой страницы.  
  
> [!NOTE]
> Параметр `-codepage` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
