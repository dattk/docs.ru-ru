---
title: Начало работы с C# и Visual Studio Code
description: Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506914"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Начало работы с C# и Visual Studio Code

.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS. Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.

## <a name="prerequisites"></a>Предварительные требования

1. Установите [Visual Studio Code](https://code.visualstudio.com/).
2. Установите [пакета SDK для .NET Core](https://dotnet.microsoft.com/download).
3. Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) для Visual Studio Code. См. дополнительные сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).

## <a name="hello-world"></a>Hello World

Начните с создания простой программы Hello World для .NET Core:

1. Откройте проект.

    - Откройте Visual Studio Code.
    - В главном меню выберите **Файл** > **Открыть папку**.
    - Создайте папку с именем *HelloWorld* и щелкните **Выбрать папку**. Имя папки по умолчанию преобразуется в имя проекта и имя пространства имен. Вы добавите код позже в этом учебнике. Предполагается, что пространство имен проекта — `HelloWorld`.

1. Инициализируйте проект C#.

    - Откройте в Visual Studio Code терминал, выбрав **Просмотр** > **Терминал** в главном меню.
    - В окне терминала введите `dotnet new console`.

      Эта команда создает в выбранной папке файл *Program.cs* с уже готовой простой программой Hello World, а также файл проекта C# с именем *HelloWorld.csproj*.

      ![Команда dotnet new](media/with-visual-studio-code/dotnet-new-command.png)

1. Запустите программу Hello World.

    - В окне терминала введите `dotnet run`.

      ![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a>Отладка

1. Откройте файл *Program.cs*, щелкнув его. Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).

    ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code предлагает добавить недостающие ресурсы для сборки и отладки приложения. Выберите ответ **Да**.

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

1. Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.

    ![Откройте вкладку "Отладка" в Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. Найдите зеленую стрелку в верхней части панели. Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант **Запуск .NET Core (консоль)** .

    ![Выбор .NET Core в Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. Добавьте в проект точку останова, щелкнув **поле редактора** (пустое пространство слева от номеров строк) в строке 9, или переместите курсор текста в строку 9 в редакторе и нажмите клавишу <kbd>F9</kbd>.

    ![Установка точки останова](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. Чтобы начать отладку, нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку. Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.
    - Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.

1. Выберите синюю стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.

    ![Запуск и отладка в Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="add-a-class"></a>Добавление класса

1. Чтобы добавить новый класс, щелкните правой кнопкой мыши в обозревателе VS Code под *Program.cs* и выберите **Новый файл**. Так вы добавите новый файл в папку, открытую в VSCode.
1. Назовите файл *MyClass.cs*. Необходимо сохранить его с расширением `.cs`, чтобы он распознавался как файл С#.
1. Добавьте приведенный ниже код для создания класса.

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. Вызовите новый класс из метода `Main`, заменив код в *Program.cs* следующим кодом:

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. Сохраните изменения.

1. Запустите программу еще раз.

    ```dotnetcli
    dotnet run
    ```

    Должно отобразиться новое сообщение с добавленной строкой.

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>часто задаваемые вопросы

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Мне не хватает ресурсов для выполнения сборки и отладки C# в Visual Studio Code. Отладчик выдает сообщение: "Конфигурация отсутствует".

Ресурсы для сборки и отладки можно создать с помощью расширения Visual Studio Code C#. Visual Studio Code предложит создать эти ресурсы при первом открытии проекта C#. Если вы не создали ресурсы, вы все равно сможете выполнить эту команду. Для этого откройте палитру команд (**Вид > Палитра команд**) и введите ">.NET: Generate Assets for Build and Debug" (.NET: создать ресурсы для сборки и отладки). После этого будут созданы необходимые файлы конфигурации *.vscode*, *launch.json* и *tasks.json*.

## <a name="see-also"></a>См. также

- [Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)
- [Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)
