---
title: Учебник. Установка и использование локальных средств .NET Core
description: Узнайте, как устанавливать и использовать средство .NET в качестве локального.
ms.date: 02/12/2020
ms.openlocfilehash: 6de620772cec1e9d1b1f57380b72c0163d68337c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543818"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a><span data-ttu-id="a1513-103">Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1513-103">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>

<span data-ttu-id="a1513-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="a1513-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="a1513-105">В этом учебнике вы узнаете, как установить и использовать локальное средство.</span><span class="sxs-lookup"><span data-stu-id="a1513-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="a1513-106">Вы используете инструмент, созданный в [первом учебнике этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="a1513-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1513-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a1513-107">Prerequisites</span></span>

* <span data-ttu-id="a1513-108">Выполните действия из [первого руководства этой серии](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="a1513-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="a1513-109">Установите среду выполнения .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="a1513-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="a1513-110">В данном учебнике вы установите и используете средство, нацеленное на .NET Core 2.1, поэтому вам необходимо установить эту среду выполнения на ваш компьютер.</span><span class="sxs-lookup"><span data-stu-id="a1513-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="a1513-111">Чтобы установить среду выполнения 2.1, перейдите на [страницу загрузки .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) и найдите ссылку на установку среды выполнения в колонке **Run apps — Runtime** (Запуск приложений — среда выполнения).</span><span class="sxs-lookup"><span data-stu-id="a1513-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="a1513-112">Создание файла манифеста</span><span class="sxs-lookup"><span data-stu-id="a1513-112">Create a manifest file</span></span>

<span data-ttu-id="a1513-113">Чтобы установить средство только для локального доступа (для текущего каталога и подкаталогов), его необходимо добавить в файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="a1513-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span> 

<span data-ttu-id="a1513-114">Из папки *botsay-\<name>* перейдите на один уровень вверх к папке *репозиторий*:</span><span class="sxs-lookup"><span data-stu-id="a1513-114">From the *botsay-\<name>* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="a1513-115">Создайте файл манифеста, выполнив команду [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="a1513-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="a1513-116">Выходные данные свидетельствуют об успешном создании файла.</span><span class="sxs-lookup"><span data-stu-id="a1513-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="a1513-117">Файл *.config/dotnet-tools.json* пока не имеет в себе никаких средств:</span><span class="sxs-lookup"><span data-stu-id="a1513-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="a1513-118">Средства, перечисленные в файле манифеста, доступны для текущего каталога и подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="a1513-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="a1513-119">Текущим является каталог, содержащий каталог *.config* с файлом манифеста.</span><span class="sxs-lookup"><span data-stu-id="a1513-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="a1513-120">При использовании команды CLI, которая относится к локальному средству, пакет SDK ищет файл манифеста в текущем каталоге и родительских каталогах.</span><span class="sxs-lookup"><span data-stu-id="a1513-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="a1513-121">Если он находит файл манифеста, но файл не включает указанное средство, поиск продолжается по родительским каталогам.</span><span class="sxs-lookup"><span data-stu-id="a1513-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="a1513-122">Поиск заканчивается после нахождения указанного средства или файла манифеста с `isRoot` установленным на `true`.</span><span class="sxs-lookup"><span data-stu-id="a1513-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="a1513-123">Установка botsay в качестве локального средства</span><span class="sxs-lookup"><span data-stu-id="a1513-123">Install botsay as a local tool</span></span>

<span data-ttu-id="a1513-124">Установите средство из пакета, который вы создали в первом учебнике:</span><span class="sxs-lookup"><span data-stu-id="a1513-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./botsay-<name>/nupkg botsay-<name>
```

<span data-ttu-id="a1513-125">Эта команда добавляет средство в файл манифеста, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="a1513-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="a1513-126">Вывод команды показывает, в каком файле манифеста находится только что установленное средство:</span><span class="sxs-lookup"><span data-stu-id="a1513-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="a1513-127">Файл *.config/dotnet-tools.json* теперь содержит одно средство:</span><span class="sxs-lookup"><span data-stu-id="a1513-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay-<name>": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="a1513-128">Работа со средством</span><span class="sxs-lookup"><span data-stu-id="a1513-128">Use the tool</span></span>

<span data-ttu-id="a1513-129">Запустите средство, выполнив команду `dotnet tool run` из папки *репозиторий*:</span><span class="sxs-lookup"><span data-stu-id="a1513-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="a1513-130">Восстановление локального инструмента, установленного другими пользователями</span><span class="sxs-lookup"><span data-stu-id="a1513-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="a1513-131">Обычно вы устанавливаете локальное средство в корневой каталог репозитория.</span><span class="sxs-lookup"><span data-stu-id="a1513-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="a1513-132">После записи файла манифеста в репозиторий после изменения, другие разработчики получают последний файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="a1513-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="a1513-133">Чтобы установить все средства, перечисленные в файле манифеста, они могут запустить всего лишь одну команду `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="a1513-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="a1513-134">Откройте файл *.config/dotnet-tools.json* и замените его содержимое на следующий JSON:</span><span class="sxs-lookup"><span data-stu-id="a1513-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "botsay-<name>": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="a1513-135">Замените `<name>` именем, использованным для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="a1513-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="a1513-136">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="a1513-136">Save your changes.</span></span>

   <span data-ttu-id="a1513-137">Внесение этого изменения аналогично получению последней версии из репозитория после установления пакета `dotnetsay` для каталога проекта другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="a1513-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span> 

1. <span data-ttu-id="a1513-138">Выполните команду `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="a1513-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="a1513-139">После выполнения команды должен появиться результат, подобный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="a1513-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'botsay-<name>' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="a1513-140">Убедитесь, что средства доступны:</span><span class="sxs-lookup"><span data-stu-id="a1513-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="a1513-141">Выходные данные представляют собой список пакетов и команд, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a1513-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   -------------------------------------------------------------------------------------------
   botsay-<name>   1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="a1513-142">Протестируйте средства:</span><span class="sxs-lookup"><span data-stu-id="a1513-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="a1513-143">Обновление локального средства</span><span class="sxs-lookup"><span data-stu-id="a1513-143">Update a local tool</span></span>

<span data-ttu-id="a1513-144">Установленная версия локального средства `dotnetsay` — 2.1.3.</span><span class="sxs-lookup"><span data-stu-id="a1513-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="a1513-145">Последней является версия 2.1.4.</span><span class="sxs-lookup"><span data-stu-id="a1513-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="a1513-146">Используйте команду [dotnet tool update](dotnet-tool-update.md), чтобы обновить средство до последней версии.</span><span class="sxs-lookup"><span data-stu-id="a1513-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="a1513-147">В выходных данных указывается новый номер версии:</span><span class="sxs-lookup"><span data-stu-id="a1513-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="a1513-148">Команда update находит первый файл манифеста, содержащий идентификатор пакета, и обновляет его.</span><span class="sxs-lookup"><span data-stu-id="a1513-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="a1513-149">Если такой идентификатор пакета отсутствует в любом файле манифеста, находящегося в области поиска, пакет SDK добавляет новую запись в ближайший файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="a1513-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="a1513-150">Область поиска поднимается вверх по родительским каталогам, пока не будет найден файл манифеста с `isRoot = true`.</span><span class="sxs-lookup"><span data-stu-id="a1513-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="a1513-151">Удаление локального средства</span><span class="sxs-lookup"><span data-stu-id="a1513-151">Remove local tools</span></span>

<span data-ttu-id="a1513-152">Удалите установленные средства, выполнив команду [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="a1513-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall botsay-<name>
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="a1513-153">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a1513-153">Troubleshoot</span></span>

<span data-ttu-id="a1513-154">Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a1513-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1513-155">См. также</span><span class="sxs-lookup"><span data-stu-id="a1513-155">See also</span></span>

<span data-ttu-id="a1513-156">Дополнительные сведения см. в статье [Обзор глобальных средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1513-156">For more information, see [.NET Core tools](global-tools.md)</span></span>