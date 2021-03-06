---
title: Метод IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445224"
---
# <a name="imetadataimport2getversionstring-method"></a>Метод IMetaDataImport2::GetVersionString
Возвращает номер версии среды выполнения, которая использовалась для построения сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzBuf`  
 заполняет Массив для хранения строки, указывающей версию.  
  
 `ccBufSize`  
 окне Размер массива `pwzBuf` в расширенных символах.  
  
 `pccBufSize`  
 заполняет Число расширенных символов, включая знак завершения null, возвращенный в массиве `pwzBuf`.  
  
## <a name="remarks"></a>Примечания  
 Метод `GetVersionString` получает встроенную версию текущей области метаданных. Если область не была сохранена, она не будет иметь встроенной версии и будет возвращена пустая строка.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
