---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424709"
---
### <a name="install-the-global-tool"></a>Установка глобального средства

Ресурсы пакета следует установить в защищенном расположении с помощью параметра `--tool-path`. Это позволяет изолировать среду пользователя с ограниченным доступом от среды с повышенными правами.

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

`/usr/local/share/dotnet-tools` создается с разрешением `drwxr-xr-x`. Если каталог уже существует, используйте команду `ls -l`, чтобы убедиться в том, что у пользователя с ограниченным доступом нет разрешения на изменение каталога. Если такое разрешение есть, запретите доступ с помощью команды `sudo chmod o-w -R /usr/share/dotnet-tools`.

### <a name="run-the-global-tool"></a>Запуск глобального средства

**Способ 1**. Используйте полный путь с sudo:

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

**Способ 2**. Добавьте символьную ссылку на средство (одна на средство):

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

Запустите средство с помощью команды:

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Удаление глобального средства

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Если вы добавили символьную ссылку, ее также нужно удалить:

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```