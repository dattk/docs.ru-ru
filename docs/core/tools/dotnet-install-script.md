---
title: Скрипты dotnet-install
description: Сведения о скриптах dotnet-install, которые служат для установки пакета SDK для .NET Core и общей среды выполнения
ms.date: 04/30/2020
ms.openlocfilehash: 9f5cef9cfcca1d8b344021efe803c063a7393f8e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802723"
---
# <a name="dotnet-install-scripts-reference"></a>Справка по скриптам dotnet-install

## <a name="name"></a>name

`dotnet-install.ps1` | `dotnet-install.sh` — скрипт, используемый для установки общей среды выполнения и пакета SDK для .NET Core.

## <a name="synopsis"></a>Краткий обзор

Windows:

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

dotnet-install.ps1 -Help
```

Linux или MacOS:

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a>Описание

Скрипты `dotnet-install` используются для установки пакета SDK для .NET Core без прав администратора. Этот пакет включает общую среду выполнения и .NET Core CLI.

Мы рекомендуем использовать стабильную версию скриптов.

- Bash (Linux или macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1>

Их основное назначение — помощь в сценариях автоматизации и при установках без прав администратора. Имеются два скрипта: один для PowerShell (работает в Windows), а второй — bash-скрипт, который работает в Linux и macOS. Оба скрипта выполняют одни и те же функции. Так как bash-скрипт также считывает параметры PowerShell, их можно использовать с этим скриптом в системах Linux и macOS.

Скрипты установки скачивают файл ZIP или TAR из места сборки CLI, а затем осуществляют установку в расположении по умолчанию или расположении, заданном параметром `-InstallDir|--install-dir`. По умолчанию скрипты установки скачивают и устанавливают пакет SDK. Если вы хотите получить только общую среду выполнения, укажите аргумент `-Runtime|--runtime`.

По умолчанию скрипт добавляет место установки в переменную $PATH для текущего сеанса. Переопределите это поведение по умолчанию, указав аргумент `-NoPath|--no-path`.

Перед запуском скрипта установите все необходимые [зависимости](../install/dependencies.md).

Вы можете установить конкретную версию с помощью аргумента `-Version|--version`. Версию следует указывать в виде трехкомпонентного номера (например, `2.1.0`). Если она не указана, используется версия `latest`.

Скрипты установки не обновляют реестр в Windows. Они просто скачивают двоичные ZIP-файлы и копируют их в папку. Чтобы значения разделов реестра обновлялись, используйте установщики .NET Core.

## <a name="options"></a>Параметры

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Архитектура устанавливаемых двоичных файлов .NET Core. Допустимые значения: `<auto>`, `amd64`, `x64`, `x86`, `arm64` и `arm`. Значение по умолчанию — `<auto>`, представляющее текущую используемую архитектуру ОС.

- **`-AzureFeed|--azure-feed`**

  Указывает URL-адрес для веб-канала Azure этого установщика. Изменять это значение не рекомендуется. Значение по умолчанию — `https://dotnetcli.azureedge.net/dotnet`.

- **`-Channel|--channel <CHANNEL>`**

  Указывает исходный канал для установки. Допустимые значения:

  - `Current` — самый последний выпуск.
  - `LTS` — канал долгосрочной поддержки (самый последний поддерживаемый выпуск).
  - Версия из двух частей в формате X.Y, который представляет конкретный выпуск (например, `2.1` или `3.0`).
  - Имя ветви, например `release/3.1.1xx` или `master` (для ночных выпусков). Используйте этот параметр для установки версии из канала предварительной версии. Используйте имя канала, указанное в разделе [Установщики и двоичные файлы](https://github.com/dotnet/core-sdk#installers-and-binaries).

  Значение по умолчанию — `LTS`. Дополнительные сведения о каналах поддержки .NET см. на странице о [политике поддержки .NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- **`-DryRun|--dry-run`**

  Если задано, скрипт не будет выполнять установку. Вместо этого отобразится командная строка для согласованной установки запрошенной в настоящее время версии .NET Core CLI. Например, если указать версию `latest`, он отображает ссылку для определенной версии, чтобы эту команду можно было детерминировано использовать в скрипте сборки. Кроме того, он отображает расположение двоичного файла, если вы хотите выполнить скачивание или установку самостоятельно.

- **`-FeedCredential|--feed-credential`**

  Используется в качестве строки запроса для добавления в веб-канал Azure. Позволяет изменять URL-адрес для использования учетных записей хранилища BLOB-объектов, не являющихся общедоступными.

- **`-Help|--help`**

  Выводит справку для скрипта.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Указывает путь установки. Если такого пути нет, создается каталог. Значение по умолчанию — *%LocalAppData%\Microsoft\dotnet* в Windows и */usr/share/dotnet* в Linux и macOS. Двоичные файлы помещаются непосредственно в этот каталог.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Указывает путь к файлу [global.json](global-json.md), который будет использоваться для определения версии пакета SDK. В файле *global.json* должно быть значение для `sdk:version`.

- **`-NoCdn|--no-cdn`**

  Отключает загрузку из [сети доставки содержимого Microsoft Azure (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) и напрямую использует некэшированный веб-канал.

- **`-NoPath|--no-path`**

  Если значение задано, папка установки не экспортируется в путь текущего сеанса. По умолчанию скрипт изменит значение PATH, благодаря чему .NET Core CLI становится доступным сразу после установки.

- **`-ProxyAddress`**

  Если значение задано, установщик использует прокси-сервер для выполнения веб-запросов. (Допустимо только для Windows.)

- **`ProxyUseDefaultCredentials`**

  Если задано, установщик использует учетные данные текущего пользователя при использовании адреса прокси-сервера. (Допустимо только для Windows.)

- **`-Runtime|--runtime <RUNTIME>`**

  Устанавливается только общая среда выполнения, а не весь пакет SDK. Допустимые значения:

  - `dotnet` — общая среда выполнения `Microsoft.NETCore.App`.
  - `aspnetcore` — общая среда выполнения `Microsoft.AspNetCore.App`.
  - `windowsdesktop` — общая среда выполнения `Microsoft.WindowsDesktop.App`.

- **`--runtime-id <RID>`**

  Указывает [идентификатор среды выполнения](../rid-catalog.md), для которого устанавливаются средства. Используйте значение `linux-x64` для переносимых файлов Linux. (Допустимо только для Linux и macOS.)

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Этот параметр является устаревшим и может быть удален в будущей версии скрипта. Вместо этого рекомендуется использовать параметр `-Runtime|--runtime`.

  Устанавливаются только двоичные файлы общей среды выполнения; в противном случае устанавливается весь пакет SDK. Этот параметр эквивалентен указанию `-Runtime|--runtime dotnet`.

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Пропускает установку файлов без версии, таких как *dotnet.exe*, если они уже существуют.

- **`-UncachedFeed|--uncached-feed`**

  Позволяет изменять URL-адрес некэшированного веб-канала, используемого этим установщиком. Изменять это значение не рекомендуется.

- **`-Verbose|--verbose`**

  Отображает сведения о диагностике.

- **`-Version|--version <VERSION>`**

  Представляет определенную версию сборки. Допустимые значения:

  - `latest` — последняя сборка в канале (используется с параметром `-Channel`).
  - `coherent` — последняя согласованная сборка в канале. Использует последние сочетания стабильных пакетов. (Используется с параметрами `-Channel` имени ветви.)
  - Версия из трех частей в формате X.Y.Z, который представляет определенную версию сборки. Заменяет параметр `-Channel`. Например, `2.0.0-preview2-006120`.

  Если не указано, `-Version` по умолчанию принимает значение `latest`.

## <a name="examples"></a>Примеры

- Установка последней версии с долгосрочной поддержкой (LTS) в расположение по умолчанию:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- Установка последней версии из канала версии 3.1 в указанное расположение

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- Установка общей среды выполнения версии 3.0.0

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  Mac OS и Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- Получите и установите скрипт версии 2.1.2 за корпоративным прокси-сервером (только для Windows):

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- Получите скрипт и установите однострочные примеры для интерфейса командной строки .NET Core:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  Mac OS и Linux:

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>См. также

- [Выпуски .NET Core](https://github.com/dotnet/core/releases)
- [Архив загрузки пакета SDK и среды выполнения .NET Core](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
