---
title: Практическое руководство. установку сборки в глобальный кэш сборок
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 64878a795a7c5b790c8991064e32b82505685c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155567"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Практическое руководство. установку сборки в глобальный кэш сборок

В глобальном кэше сборок сохраняются сборки, которые могут использоваться несколькими приложениями. Установите сборку в [глобальный кэш сборок](gac.md) с одним из следующих компонентов:

- [Установщик Windows](#windows-installer)
- [Средство глобального кэша сборок](#global-assembly-cache-tool)

> [!IMPORTANT]
> В глобальный кэш сборок можно установить только сборки со строгими именами. Дополнительные сведения о создании сборки со строгим именем см. в разделе [Практическое руководство. Подписание сборки со строгим именем](../../standard/assembly/sign-strong-name.md).

## <a name="windows-installer"></a>Установщик Windows

[Установщик Windows](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache) — средство установки Windows, которое рекомендуется использовать для добавления сборок в GAC. Установщик Windows предоставляет возможность подсчета ссылок на сборки в GAC и другие дополнительные возможности. Создать пакет установщика для установщика Windows можно с помощью [расширения Wix Toolset для Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Средство глобального кэша сборок

[Служебную программу глобального кэша сборок .NET (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) можно использовать для добавления сборок в глобальный кэш сборок и для просмотра содержимого указанного кэша.

   > [!NOTE]
   > *Gacutil.exe* предназначен только для разработки. Не используйте его для установки рабочих сборок в глобальный кэш сборок.

Синтаксис для использования *gacutil.exe* для установки сборки в глобальном кэше сборок выглядит следующим образом:

```cmd
gacutil -i <assembly name>
```

В этой команде *\<имя сборки>* представляет собой имя сборки, устанавливаемой в глобальный кэш сборок.

Если *gacutil.exe* не находится в системном пути, используйте [командную строку разработчика для VS *\<версия>* ](../tools/developer-command-prompt-for-vs.md).

В следующем примере выполняется установка сборки с именем файла *hello.dll* в глобальный кэш сборок.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> В предыдущих версиях .NET Framework расширение оболочки Windows *Shfusion.dll* позволяло устанавливать сборки, перетаскивая их в проводнике. Начиная с версии .NET Framework 4 расширение оболочки *Shfusion.dll* является устаревшим.

## <a name="see-also"></a>См. также

- [Работа со сборками и глобальным кэшем сборок](working-with-assemblies-and-the-gac.md)
- [Практическое руководство. Удаление сборки из глобального кэша сборок](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (программа глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md)
- [Практическое руководство. Подписание сборки строгим именем](../../standard/assembly/sign-strong-name.md)
