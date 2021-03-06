---
title: Структура MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 33b3044c7b5237e586fdb993a16b6144c271782c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007719"
---
# <a name="mdainfo-structure"></a>Структура MDAInfo
Предоставляет сведения о `Event_MDAFired` событии, которое запускает создание помощника по отладке управляемого кода (MDA).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`lpMDACaption`|Заголовок текущего MDA. Заголовок описывает тип сбоя, вызвавшего `Event_MDAFired` событие.|  
|`lpMDAMessage`|Выходное сообщение, предоставленное текущим MDA.|  
  
## <a name="remarks"></a>Примечания  
 Управляемые помощники по отладке (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для выполнения таких задач, как определение недопустимых условий в подсистеме выполнения среды выполнения или дамп дополнительных сведений о состоянии подсистемы. MDA создают сообщения XML о событиях, которые в противном случае сложны для перехвата. Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.  
  
 При срабатывании события, запускающего создание MDA, среда выполнения выполняет следующие действия:  
  
- Если узел не зарегистрировал экземпляр [иактиононклревент](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) , вызвав [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) , чтобы получать уведомления о `Event_MDAFired` событии, среда выполнения переходит по умолчанию, а не размещенное поведение.  
  
- Если узел зарегистрировал обработчик для этого события, среда выполнения проверяет, присоединен ли отладчик к процессу. Если это так, среда выполнения разбивается на отладчик. Когда отладчик продолжит выполнение, он вызывает узел. Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на `MDAInfo` экземпляр в качестве `data` параметра.  
  
 Узел может активировать MDA и получать уведомления при активации MDA. Это дает узлу возможность переопределить поведение по умолчанию и прервать управляемый поток, вызвавший событие, чтобы предотвратить повреждение состояния процесса. Дополнительные сведения об использовании MDA см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Структуры размещения](hosting-structures.md)
- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
