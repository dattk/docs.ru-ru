---
title: Использование бессерверных функций
description: Использование бессерверных и функций Azure в собственных облачных приложениях
ms.date: 05/13/2020
ms.openlocfilehash: 53a0fdd29630b2a4368f3aa37ddfc5f93df10a24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613867"
---
# <a name="leveraging-serverless-functions"></a>Использование бессерверных функций

В спектре от управления физическими компьютерами до использования облачных возможностей бессерверные функции находятся в крайнем конце. Единственной обязанностью является ваш код, и вы платите только за время выполнения кода. Функции Azure предоставляют возможность создания бессерверных функций в собственных облачных приложениях.

## <a name="what-is-serverless"></a>Что значит "без сервера"?

Бессерверные технологии — это относительно новая модель службы облачных вычислений. Это не означает, что серверы являются необязательными. код по-прежнему работает на сервере где-то еще. Различие состоит в том, что группа приложений больше не связана с управлением серверной инфраструктурой. Вместо этого ответственность за это несет поставщик облачных вычислений. Команда разработчиков повышает производительность за счет предоставления бизнес-решений клиентам, а не коммуникации.

Бессерверные вычисления используют контейнеры, активируемые событиями без отслеживания состояния, для размещения служб. Они могут масштабироваться и в для удовлетворения спроса по мере необходимости. Бессерверные платформы, такие как функции Azure, тесно интегрируются с другими службами Azure, такими как очереди, события и хранилище.

## <a name="what-challenges-are-solved-by-serverless"></a>Какие проблемы решаются независимо от сервера?

Бессерверные платформы изменяют множество ресурсоемких и дорогостоящих проблем:

- Приобретение компьютеров и лицензий на программное обеспечение
- Корпус, обеспечение безопасности, Настройка и обслуживание компьютеров и их сети, мощности и требований к/C
- Установка исправлений и обновление операционных систем и программного обеспечения
- Настройка веб-серверов или служб компьютеров для размещения программного обеспечения приложения
- Настройка программного обеспечения приложения на платформе

Многие компании распределяют большие бюджеты для поддержки проблем с инфраструктурой оборудования. Переход в облако поможет снизить затраты. Перемещение приложений на сервер может помочь устранить их.

## <a name="what-is-the-difference-between-a-microservice-and-a-serverless-function"></a>В чем разница между микрослужбой и бессерверной функцией?

Обычно микрослужба включает бизнес-возможности, такие как покупательская корзина для веб-сайта электронной коммерции. Она предоставляет несколько операций, которые позволяют пользователю управлять своими покупками. Однако функция является небольшим простым блоком кода, который выполняет однозначную операцию в ответ на событие.
Микрослужбы обычно создаются для реагирования на запросы, часто из интерфейса. Запросы могут быть на базе HTTP gRPC или на основе запросов. Бессерверные службы реагируют на события. Ее архитектура, управляемая событиями, идеально подходит для обработки кратковременных фоновых задач.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>Какие сценарии подходят для бессерверных задач?

Бессерверные программы предоставляют отдельные кратковременные функции, которые вызываются в ответ на триггер. Это делает их идеальным решением для обработки фоновых задач.

Приложению может потребоваться отправить сообщение электронной почты в качестве шага в рабочем процессе. Вместо отправки уведомления в рамках запроса микрослужбы поместите сведения о сообщении в очередь. Функция Azure может вывести сообщение из очереди и асинхронно отправить сообщение. Это может повысить производительность и масштабируемость микрослужбы. Можно реализовать [Выравнивание нагрузки на основе очередей](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) , чтобы избежать узких мест, связанных с отправкой сообщений электронной почты. Кроме того, эту автономную службу можно повторно использовать в качестве служебной программы во многих разных приложениях.

Асинхронный обмен сообщениями из очередей и разделов является распространенным шаблоном для активации бессерверных функций. Однако функции Azure могут инициироваться другими событиями, например изменениями в хранилище BLOB-объектов Azure. Служба, поддерживающая передачу изображений, может иметь функцию Azure, отвечающую за оптимизацию размера образа. Функция может быть активирована непосредственно путем вставки в хранилище BLOB-объектов Azure, что усложняет работу операций микрослужбы.

Многие службы имеют длительно работающие процессы в рамках рабочих процессов. Часто эти задачи выполняются как часть взаимодействия пользователя с приложением. Эти задачи могут заставить пользователя ожидать, негативно влияя на их работу. Бессерверные вычисления предоставляют отличный способ перемещения более медленных задач за пределы цикла взаимодействия с пользователем. Эти задачи можно масштабировать по запросу, не требуя масштабирования всего приложения.

## <a name="when-should-you-avoid-serverless"></a>Когда следует избегать бессерверных проблем?

Бессерверные решения подготавливаются и масштабируются по запросу. При вызове нового экземпляра холодный запуск является распространенной проблемой. Холодный запуск — это период времени, требуемый для инициализации этого экземпляра. Обычно эта задержка может составлять несколько секунд, но она может быть длиннее в зависимости от различных факторов. После подготовки один экземпляр сохраняется в активном состоянии до тех пор, пока он получает периодические запросы. Но если служба вызывается реже, Azure может удалить ее из памяти и требовать холодного запуска при повторном вызове. Холодный запуск также требуется, когда функция масштабируется до нового экземпляра.

На рис. 3-10 показан шаблон холодного запуска. Обратите внимание на дополнительные шаги, необходимые для холодного приложения.

![Холодный и горячий запуск ](./media/cold-start-warm-start.png)
 **рис. 3-10**. Холодный запуск и горячий запуск.

Чтобы избежать холодного запуска, вы можете переключиться с [плана потребления на выделенный план](https://azure.microsoft.com/blog/understanding-serverless-cold-start/). Вы также можете настроить один или несколько [предварительно подготовленных экземпляров](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) с помощью обновления плана Premium. В таких случаях, когда необходимо добавить другой экземпляр, он уже готов к работе. Эти параметры могут помочь устранить проблемы холодного запуска, связанные с бессерверными вычислениями.

Поставщики облачных служб выставляют счета за бессерверные ресурсы в зависимости от времени выполнения вычислений и потребленной памяти. Длительные операции или рабочие нагрузки с высоким потреблением памяти не всегда являются лучшими кандидатами для бессерверных. Бессерверные функции применяют небольшие фрагменты работы, которые могут быть быстро завершены. Большинству бессерверных платформ требуется, чтобы отдельные функции были выполнены в течение нескольких минут. По умолчанию для функций Azure устанавливается длительность ожидания в 5 минут, что может быть настроено до 10 минут. План функций Azure Premium может также устранить эту ошибку, а время ожидания по умолчанию — 30 минут с неограниченным большим ограничением, которое можно настроить. Время вычислений не является календарным временем. Более сложные функции, использующие [Azure устойчивые функции Framework](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview?tabs=csharp) , могут приостановить выполнение в течение нескольких дней. Выставление счетов основано на фактическом времени выполнения, когда функция выходит из спящего режима и продолжает обработку.

Наконец, использование функций Azure для задач приложения усложняет сложность. Разумно сначала спроектировать приложение с помощью модульной, слабо связанной архитектуры. Затем выясните, есть ли у сервера преимущества, которые будут предлагаться, чтобы выровнять дополнительную сложность.

>[!div class="step-by-step"]
>[Назад](leverage-containers-orchestrators.md)
>[Вперед](combine-containers-serverless-approaches.md)
