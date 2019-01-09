---
title: Método SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3f2180d9a1893e651f174fff6d0f073df651e712
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152568"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="3c1dc-102">Método SqlStreamChars.Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="3c1dc-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="3c1dc-103">Cuando se invalida en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="3c1dc-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3c1dc-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="3c1dc-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="3c1dc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c1dc-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="3c1dc-108">Es `true` para liberar tanto recursos administrados como no administrados; es `false` para liberar únicamente recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c1dc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c1dc-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3c1dc-110">El `SqlStreamChars.Dispose` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3c1dc-111">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c1dc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c1dc-112">Requirements</span></span>

<span data-ttu-id="3c1dc-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3c1dc-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3c1dc-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="3c1dc-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3c1dc-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="3c1dc-115">**.NET Framework versions:** Available since 2.0.</span></span>