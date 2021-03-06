---
title: Приложения SOA
description: Имейте в виду, что контейнеры могут быть удобным вариантом развертывания для приложений SOA.
ms.date: 02/15/2019
ms.openlocfilehash: f8619cb50a7d90b911db9ff2c8ef37c3c5fde210
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738390"
---
# <a name="service-oriented-applications"></a>Сервисноориентированные приложения

Термин "сервисноориентированная архитектура" (SOA) перегружен значениями и для разных людей означает разные понятия. Однако общий момент заключается в том, что термин SOA подразумевает структурирование архитектуры приложения путем разделения ее на несколько служб (чаще всего HTTP-службы), которые можно классифицировать различными способами, например как подсистемы или уровни.

Сейчас эти службы можно развернуть как контейнеры Docker, которые помогают решать проблемы развертывания, так как в образ контейнера включены все зависимости. Однако, если при развертывании вы используете отдельные экземпляры, то при необходимости масштабирования приложений SOA вы столкнетесь с проблемами. Эту проблему можно решить с помощью программного обеспечения кластеризации Docker или оркестратора. Мы рассмотрим оркестраторы более подробно в следующем разделе, при изучении подходов на основе микрослужб.

Контейнеры Docker являются полезным (но необязательным) элементом как для традиционных архитектур, ориентированных на службы, так и более сложных архитектур с микрослужбами.

В целом решения кластеризации на базе контейнеров удобны как для традиционной архитектуры SOA, так и для более сложной архитектуры микрослужб, где каждая микрослужба имеет свою модель данных. А благодаря нескольким базам данных также есть возможность масштабировать уровень данных вместо работы с монолитными базами данных, совместно используемыми службами SOA. Однако обсуждение разделения данных касается исключительно архитектуры и проектирования.

>[!div class="step-by-step"]
>[Назад](state-and-data-in-docker-applications.md)
>[Вперед](orchestrate-high-scalability-availability.md)
