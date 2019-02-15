---
title: Метод IXCLRDataMethodInstance::GetRepresentativeEntryAddress
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 52b2fdaaefd16a49300641f44041b8352141385b
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828679"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="6c38a-102">Метод IXCLRDataMethodInstance::GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="6c38a-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="6c38a-103">Получает наиболее характерные адрес точки входа для компиляция в собственном коде все возможные точки входа для метода.</span><span class="sxs-lookup"><span data-stu-id="6c38a-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6c38a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c38a-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

### <a name="parameters"></a><span data-ttu-id="6c38a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c38a-105">Parameters</span></span>

<span data-ttu-id="6c38a-106">`addr` [out] Адрес типичному машинную точку входа для метода.</span><span class="sxs-lookup"><span data-stu-id="6c38a-106">`addr` [out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c38a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c38a-107">Remarks</span></span>

<span data-ttu-id="6c38a-108">Указанный метод является частью [ `IXCLRDataMethodInstance` интерфейс](ixclrdatamethodinstance-interface.md) и соответствует 19 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="6c38a-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c38a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6c38a-109">Requirements</span></span>

<span data-ttu-id="6c38a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c38a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6c38a-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="6c38a-111">**Header:** None</span></span>  
<span data-ttu-id="6c38a-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="6c38a-112">**Library:** None</span></span>  
<span data-ttu-id="6c38a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c38a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c38a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6c38a-114">See also</span></span>

- [<span data-ttu-id="6c38a-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="6c38a-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6c38a-116">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="6c38a-116">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)