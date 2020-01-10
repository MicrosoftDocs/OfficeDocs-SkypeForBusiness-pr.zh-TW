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
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003283"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="50286-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="50286-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="50286-104">CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="50286-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="50286-105">範例</span><span class="sxs-lookup"><span data-stu-id="50286-105">Examples</span></span>
<span data-ttu-id="50286-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50286-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="50286-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="50286-107">Example 1</span></span>

<span data-ttu-id="50286-108">下列範例會在您續約憑證之後，移除針對中央管理商店、中繼伺服器和 Edge 伺服器所頒發的舊版證書：</span><span class="sxs-lookup"><span data-stu-id="50286-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="50286-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="50286-109">Example 2</span></span>

<span data-ttu-id="50286-110">下一個範例會在您續約憑證之後，移除為中繼伺服器和 Edge 伺服器頒發的憑證：</span><span class="sxs-lookup"><span data-stu-id="50286-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="50286-111">參數</span><span class="sxs-lookup"><span data-stu-id="50286-111">Parameters</span></span>
<span data-ttu-id="50286-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50286-112"></span></span>

|<span data-ttu-id="50286-113">**參數**</span><span class="sxs-lookup"><span data-stu-id="50286-113">**Parameter**</span></span>|<span data-ttu-id="50286-114">**必要**</span><span class="sxs-lookup"><span data-stu-id="50286-114">**Required**</span></span>|<span data-ttu-id="50286-115">**類型**</span><span class="sxs-lookup"><span data-stu-id="50286-115">**Type**</span></span>|<span data-ttu-id="50286-116">**描述**</span><span class="sxs-lookup"><span data-stu-id="50286-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="50286-117">角色</span><span class="sxs-lookup"><span data-stu-id="50286-117">Roles</span></span> <br/> |<span data-ttu-id="50286-118">選用</span><span class="sxs-lookup"><span data-stu-id="50286-118">Optional</span></span>  <br/> |<span data-ttu-id="50286-119">System.object</span><span class="sxs-lookup"><span data-stu-id="50286-119">System.Array</span></span>  <br/> | <span data-ttu-id="50286-120">雲端連接器伺服器角色的陣列。</span><span class="sxs-lookup"><span data-stu-id="50286-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="50286-121">輸入類型</span><span class="sxs-lookup"><span data-stu-id="50286-121">Input Types</span></span>
<span data-ttu-id="50286-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50286-122"></span></span>

<span data-ttu-id="50286-123">無。</span><span class="sxs-lookup"><span data-stu-id="50286-123">None.</span></span> <span data-ttu-id="50286-124">CcLegacyServerCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="50286-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50286-125">傳回類型</span><span class="sxs-lookup"><span data-stu-id="50286-125">Return Types</span></span>
<span data-ttu-id="50286-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50286-126"></span></span>

<span data-ttu-id="50286-127">無</span><span class="sxs-lookup"><span data-stu-id="50286-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50286-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="50286-128">See also</span></span>
<span data-ttu-id="50286-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50286-129"></span></span>

[<span data-ttu-id="50286-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="50286-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="50286-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="50286-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="50286-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="50286-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="50286-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="50286-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

