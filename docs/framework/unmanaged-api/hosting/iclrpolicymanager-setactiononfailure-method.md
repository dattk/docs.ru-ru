---
title: Метод ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: fb2ecc80f272a3fc9b63b20c5956e7a28f117784
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703470"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Метод ICLRPolicyManager::SetActionOnFailure
Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `failure`  
 окне Одно из значений [еклрфаилуре](eclrfailure-enumeration.md) , указывающее тип сбоя, для которого необходимо выполнить действие.  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, выполняемое в случае сбоя. Список поддерживаемых значений см. в разделе "Примечания".  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Действие политики не может быть задано для указанной операции, или для операции указано недопустимое действие политики.|  
  
## <a name="remarks"></a>Комментарии  
 По умолчанию среда CLR создает исключение, когда не удается выделить ресурс, например память. `SetActionOnFailure`позволяет узлу переопределить это поведение, указав действие политики для выполнения при сбое. В следующей таблице показаны поддерживаемые сочетания значений [еклрфаилуре](eclrfailure-enumeration.md) и [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) . (Префикс FAIL_ опущен из значений [еклрфаилуре](eclrfailure-enumeration.md) .)  
  
||нонкритикалресаурце|критикалресаурце|фаталрунтиме|орфанедлокк|StackOverflow|AccessViolationException|кодеконтракт|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||Недоступно||  
|есровексцептион|X|X||||Недоступно||  
|`eAbortThread`|X|X||||Недоступно|X|  
|`eRudeAbortThread`|X|X||||Недоступно|X|  
|`eUnloadAppDomain`|X|X||X||Недоступно|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|Недоступно|X|  
|`eExitProcess`|X|X||X|X|Недоступно|X|  
|ефастекситпроцесс|X|X||X|X|Недоступно||  
|`eRudeExitProcess`|X|X|X|X|X|Недоступно||  
|`eDisableRuntime`|X|X|X|X|X|Недоступно||  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
