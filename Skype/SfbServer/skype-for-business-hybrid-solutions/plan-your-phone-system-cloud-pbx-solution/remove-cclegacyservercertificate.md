---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824279"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="1fa99-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="1fa99-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="1fa99-104">CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="1fa99-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="1fa99-105">範例</span><span class="sxs-lookup"><span data-stu-id="1fa99-105">Examples</span></span>
<span data-ttu-id="1fa99-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa99-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1fa99-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="1fa99-107">Example 1</span></span>

<span data-ttu-id="1fa99-108">下列範例會在您續約憑證之後，移除針對中央管理商店、中繼伺服器和 Edge 伺服器所頒發的舊版證書：</span><span class="sxs-lookup"><span data-stu-id="1fa99-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="1fa99-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="1fa99-109">Example 2</span></span>

<span data-ttu-id="1fa99-110">下一個範例會在您續約憑證之後，移除為中繼伺服器和 Edge 伺服器頒發的憑證：</span><span class="sxs-lookup"><span data-stu-id="1fa99-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="1fa99-111">參數</span><span class="sxs-lookup"><span data-stu-id="1fa99-111">Parameters</span></span>
<span data-ttu-id="1fa99-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa99-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="1fa99-113">**參數**</span><span class="sxs-lookup"><span data-stu-id="1fa99-113">**Parameter**</span></span>|<span data-ttu-id="1fa99-114">**必要**</span><span class="sxs-lookup"><span data-stu-id="1fa99-114">**Required**</span></span>|<span data-ttu-id="1fa99-115">**類型**</span><span class="sxs-lookup"><span data-stu-id="1fa99-115">**Type**</span></span>|<span data-ttu-id="1fa99-116">**說明**</span><span class="sxs-lookup"><span data-stu-id="1fa99-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1fa99-117">角色</span><span class="sxs-lookup"><span data-stu-id="1fa99-117">Roles</span></span> <br/> |<span data-ttu-id="1fa99-118">選用</span><span class="sxs-lookup"><span data-stu-id="1fa99-118">Optional</span></span>  <br/> |<span data-ttu-id="1fa99-119">System.object</span><span class="sxs-lookup"><span data-stu-id="1fa99-119">System.Array</span></span>  <br/> | <span data-ttu-id="1fa99-120">雲端連接器伺服器角色的陣列。</span><span class="sxs-lookup"><span data-stu-id="1fa99-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1fa99-121">輸入類型</span><span class="sxs-lookup"><span data-stu-id="1fa99-121">Input Types</span></span>
<span data-ttu-id="1fa99-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa99-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1fa99-123">無。</span><span class="sxs-lookup"><span data-stu-id="1fa99-123">None.</span></span> <span data-ttu-id="1fa99-124">CcLegacyServerCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="1fa99-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1fa99-125">傳回類型</span><span class="sxs-lookup"><span data-stu-id="1fa99-125">Return Types</span></span>
<span data-ttu-id="1fa99-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa99-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1fa99-127">無</span><span class="sxs-lookup"><span data-stu-id="1fa99-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fa99-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1fa99-128">See also</span></span>
<span data-ttu-id="1fa99-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa99-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1fa99-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="1fa99-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="1fa99-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="1fa99-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="1fa99-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="1fa99-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="1fa99-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="1fa99-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

