---
title: Интерфейс IHostIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 90675d9be71342efa903767abbf63102b40a2c35
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804678"
---
# <a name="ihostiocompletionmanager-interface"></a>Интерфейс IHostIoCompletionManager
Предоставляет методы, позволяющие среде CLR взаимодействовать с портами завершения ввода-вывода, предоставляемыми узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Bind](ihostiocompletionmanager-bind-method.md)|Привязывает маркер к порту завершения ввода-вывода.|  
|[Метод CloseIoCompletionPort](ihostiocompletionmanager-closeiocompletionport-method.md)|Закрывает порт, созданный с помощью предыдущего вызова метода `CreateIoCompletionPort` .|  
|[Метод CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)|Запрашивает создание узлом нового порта завершения ввода-вывода.|  
|[Метод GetAvailableThreads](ihostiocompletionmanager-getavailablethreads-method.md)|Возвращает число потоков завершения ввода-вывода, которые в настоящий момент не обрабатывают запросы.|  
|[Метод GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)|Возвращает размер любых пользовательских данных, которые узел намеревается добавить к запросам ввода-вывода.|  
|[Метод GetMaxThreads](ihostiocompletionmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, которое узел может выделить для обслуживания запросов ввода-вывода.|  
|[Метод GetMinThreads](ihostiocompletionmanager-getminthreads-method.md)|Возвращает минимальное число потоков, предоставляемых узлом для обслуживания запросов ввода-вывода.|  
|[Метод InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md)|Предоставляет узлу возможность инициализировать любые пользовательские данные о запросе ввода-вывода.|  
|[Метод SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Предоставляет узлу указатель интерфейса на экземпляр [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) , РЕАЛИЗУЕМый средой CLR.|  
|[Метод SetMaxThreads](ihostiocompletionmanager-setmaxthreads-method.md)|Задает максимальное число потоков, которое узел запрашивает для обслуживания запросов ввода-вывода.|  
|[Метод SetMinThreads](ihostiocompletionmanager-setminthreads-method.md)|Задает минимальное число потоков, которое узел должен выделить при завершении ввода-вывода.|  
  
## <a name="remarks"></a>Замечания  
 `IHostIoCompletionManager`соответствует `ICLRIoCompletionManager` интерфейсу, реализованному средой CLR. Среда CLR вызывает методы `IHostIoCompletionManager` для привязки дескрипторов к портам, предоставляемым узлом, и узел вызывает методы `ICLRIoCompletionManager` для сообщения о завершении запросов ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы размещения](hosting-interfaces.md)
