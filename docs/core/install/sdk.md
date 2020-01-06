---
title: Установка пакета SDK для .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для разработки приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999065"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="75423-104">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="75423-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="75423-105">В этой статье вы узнаете, как установить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75423-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="75423-106">Пакет SDK для .NET Core используется для создания приложений и библиотек .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75423-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="75423-107">Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="75423-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="75423-108">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="75423-108">Install with an installer</span></span>

<span data-ttu-id="75423-109">В Windows есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="75423-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="75423-110">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="75423-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="75423-111">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="75423-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="75423-112">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="75423-112">Install with an installer</span></span>

<span data-ttu-id="75423-113">В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="75423-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="75423-114">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="75423-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="75423-115">Установка с помощью диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="75423-115">Install with a package manager</span></span>

<span data-ttu-id="75423-116">Вы можете установить пакет SDK для .NET Core с помощью множества стандартных диспетчеров пакетов Linux.</span><span class="sxs-lookup"><span data-stu-id="75423-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="75423-117">Дополнительные сведения см. в статье [Диспетчер пакетов Linux — установка .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="75423-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="75423-118">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="75423-118">Download and manually install</span></span>

<span data-ttu-id="75423-119">Чтобы извлечь пакет SDK и сделать команды доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75423-119">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="75423-120">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="75423-120">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="75423-121">Приведенные выше команды сделают команды пакета SDK для .NET доступными только для сеанса терминала, в котором производился запуск.</span><span class="sxs-lookup"><span data-stu-id="75423-121">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="75423-122">Вы можете изменить профиль оболочки, чтобы добавить команды окончательно.</span><span class="sxs-lookup"><span data-stu-id="75423-122">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="75423-123">Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль.</span><span class="sxs-lookup"><span data-stu-id="75423-123">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="75423-124">Например:</span><span class="sxs-lookup"><span data-stu-id="75423-124">For example:</span></span>
>
> - <span data-ttu-id="75423-125">**Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="75423-125">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="75423-126">**Оболочка Korn**: *~/.kshrc* или *.profile*</span><span class="sxs-lookup"><span data-stu-id="75423-126">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="75423-127">**Оболочка Z**: *~/.zshrc* или *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="75423-127">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="75423-128">Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`.</span><span class="sxs-lookup"><span data-stu-id="75423-128">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="75423-129">Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="75423-129">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="75423-130">Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.</span><span class="sxs-lookup"><span data-stu-id="75423-130">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="75423-131">Установка с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75423-131">Install with Visual Studio</span></span>

<span data-ttu-id="75423-132">Если вы используете Visual Studio для разработки приложений .NET Core, в следующей таблице указана минимальная требуемая версия Visual Studio на основе целевой версии пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75423-132">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="75423-133">Версия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="75423-133">.NET Core SDK version</span></span> | <span data-ttu-id="75423-134">Версия Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75423-134">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="75423-135">3.1</span><span class="sxs-lookup"><span data-stu-id="75423-135">3.1</span></span>                   | <span data-ttu-id="75423-136">Visual Studio 2019 версии 16.4 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="75423-136">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="75423-137">3.0</span><span class="sxs-lookup"><span data-stu-id="75423-137">3.0</span></span>                   | <span data-ttu-id="75423-138">Visual Studio 2019 версии 16.3 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="75423-138">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="75423-139">2.2</span><span class="sxs-lookup"><span data-stu-id="75423-139">2.2</span></span>                   | <span data-ttu-id="75423-140">Visual Studio 2017 версии 15.9 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="75423-140">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="75423-141">2.1</span><span class="sxs-lookup"><span data-stu-id="75423-141">2.1</span></span>                   | <span data-ttu-id="75423-142">Visual Studio 2017 версии 15.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="75423-142">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="75423-143">Если среда Visual Studio уже установлена, вы можете проверить ее версию, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="75423-143">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="75423-144">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75423-144">Open Visual Studio.</span></span>
01. <span data-ttu-id="75423-145">Выберите **Справка** > **О Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="75423-145">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="75423-146">Считайте номер версии из диалогового окна **О программе**.</span><span class="sxs-lookup"><span data-stu-id="75423-146">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="75423-147">Visual Studio может установить последнюю пакета SDK для .NET Core и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75423-147">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="75423-148">[Скачайте Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="75423-148">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="75423-149">Выбор рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="75423-149">Select a workload</span></span>

<span data-ttu-id="75423-150">При установке или изменении Visual Studio выберите одну из следующих рабочих нагрузок в зависимости от типа создаваемого приложения:</span><span class="sxs-lookup"><span data-stu-id="75423-150">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="75423-151">рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;</span><span class="sxs-lookup"><span data-stu-id="75423-151">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="75423-152">рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;</span><span class="sxs-lookup"><span data-stu-id="75423-152">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="75423-153">рабочая нагрузка **Разработка для Azure** в разделе **Веб-разработка и облако**;</span><span class="sxs-lookup"><span data-stu-id="75423-153">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="75423-154">рабочая нагрузка **Разработка классических приложений .NET** в разделе **Классические и мобильные**.</span><span class="sxs-lookup"><span data-stu-id="75423-154">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="75423-155">[![Windows Visual Studio 2019 с рабочей нагрузкой .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="75423-155">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="75423-156">Установка с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="75423-156">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="75423-157">Visual Studio для Mac устанавливает пакет SDK для .NET Core, если выбрана рабочая нагрузка **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="75423-157">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="75423-158">Чтобы приступить к разработке в .NET Core на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="75423-158">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="75423-159">В последнем выпуске .NET Core 3.1 необходимо использовать предварительную версию Visual Studio для Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="75423-159">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="75423-160">[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET Core в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="75423-160">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="75423-161">Установка вместе с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="75423-161">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="75423-162">Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере.</span><span class="sxs-lookup"><span data-stu-id="75423-162">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="75423-163">Visual Studio Code доступен для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="75423-163">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="75423-164">Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.</span><span class="sxs-lookup"><span data-stu-id="75423-164">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="75423-165">[Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="75423-165">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="75423-166">[Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="75423-166">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="75423-167">[Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="75423-167">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="75423-168">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="75423-168">Install with PowerShell automation</span></span>

<span data-ttu-id="75423-169">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="75423-169">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="75423-170">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="75423-170">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="75423-171">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="75423-171">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="75423-172">Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.</span><span class="sxs-lookup"><span data-stu-id="75423-172">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="75423-173">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="75423-173">Install with bash automation</span></span>

<span data-ttu-id="75423-174">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="75423-174">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="75423-175">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="75423-175">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="75423-176">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="75423-176">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="75423-177">Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.</span><span class="sxs-lookup"><span data-stu-id="75423-177">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="75423-178">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="75423-178">All .NET Core downloads</span></span>

<span data-ttu-id="75423-179">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="75423-179">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="75423-180">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="75423-180">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="75423-181">Скачиваемые файлы для .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="75423-181">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="75423-182">Скачиваемые файлы для .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="75423-182">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="75423-183">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="75423-183">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="75423-184">Docker</span><span class="sxs-lookup"><span data-stu-id="75423-184">Docker</span></span>

<span data-ttu-id="75423-185">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="75423-185">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="75423-186">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="75423-186">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="75423-187">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="75423-187">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="75423-188">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="75423-188">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="75423-189">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="75423-189">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="75423-190">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="75423-190">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="75423-191">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="75423-191">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="75423-192">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="75423-192">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="75423-193">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="75423-193">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="75423-194">[Учебник. Hello World на C#](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="75423-194">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="75423-195">[Учебник. Hello World на Visual Basic](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="75423-195">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="75423-196">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="75423-196">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="75423-197">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="75423-197">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="75423-198">[Учебник. Начало работы с macOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="75423-198">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="75423-199">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="75423-199">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="75423-200">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="75423-200">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="75423-201">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="75423-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="75423-202">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="75423-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end