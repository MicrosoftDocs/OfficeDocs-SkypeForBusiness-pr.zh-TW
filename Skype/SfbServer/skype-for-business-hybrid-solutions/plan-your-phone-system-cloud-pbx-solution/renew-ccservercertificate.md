---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 當 CcServerCertificate Cmdlet 接近到期或已到期時，會更新商務用 Skype 雲端連接器版本的憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824259"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="f94fe-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f94fe-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="f94fe-105">當 CcServerCertificate Cmdlet 接近到期或已到期時，會更新商務用 Skype 雲端連接器版本的憑證。</span><span class="sxs-lookup"><span data-stu-id="f94fe-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="f94fe-106">此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。</span><span class="sxs-lookup"><span data-stu-id="f94fe-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="f94fe-107">範例</span><span class="sxs-lookup"><span data-stu-id="f94fe-107">Examples</span></span>
<span data-ttu-id="f94fe-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f94fe-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="f94fe-109">Example 1</span></span>

<span data-ttu-id="f94fe-110">下列範例會在憑證接近到期或已到期時，續約中央管理商店、中繼伺服器和 Edge 伺服器的憑證：</span><span class="sxs-lookup"><span data-stu-id="f94fe-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f94fe-111">範例 2</span><span class="sxs-lookup"><span data-stu-id="f94fe-111">Example 2</span></span>

<span data-ttu-id="f94fe-112">下個範例會在伺服器和 Edge 伺服器接近到期或過期時，續約的憑證：</span><span class="sxs-lookup"><span data-stu-id="f94fe-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="f94fe-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="f94fe-113">Detailed Description</span></span>
<span data-ttu-id="f94fe-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f94fe-115">向中央管理商店、中繼伺服器和 Edge 伺服器頒發的雲端連接器內部憑證，在來自憑證授權單位服務的兩年後有效。</span><span class="sxs-lookup"><span data-stu-id="f94fe-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="f94fe-116">如果證書接近到期或已過期，請執行 CcServerCertificate Cmdlet 來更新憑證。</span><span class="sxs-lookup"><span data-stu-id="f94fe-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="f94fe-117">參數</span><span class="sxs-lookup"><span data-stu-id="f94fe-117">Parameters</span></span>
<span data-ttu-id="f94fe-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f94fe-119">**參數**</span><span class="sxs-lookup"><span data-stu-id="f94fe-119">**Parameter**</span></span>|<span data-ttu-id="f94fe-120">**必要**</span><span class="sxs-lookup"><span data-stu-id="f94fe-120">**Required**</span></span>|<span data-ttu-id="f94fe-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="f94fe-121">**Type**</span></span>|<span data-ttu-id="f94fe-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="f94fe-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f94fe-123">角色</span><span class="sxs-lookup"><span data-stu-id="f94fe-123">Roles</span></span>  <br/> |<span data-ttu-id="f94fe-124">選用</span><span class="sxs-lookup"><span data-stu-id="f94fe-124">Optional</span></span>  <br/> |<span data-ttu-id="f94fe-125">System.object</span><span class="sxs-lookup"><span data-stu-id="f94fe-125">System.Array</span></span>  <br/> | <span data-ttu-id="f94fe-126">雲端連接器伺服器角色的陣列。</span><span class="sxs-lookup"><span data-stu-id="f94fe-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f94fe-127">輸入類型</span><span class="sxs-lookup"><span data-stu-id="f94fe-127">Input Types</span></span>
<span data-ttu-id="f94fe-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f94fe-129">無。</span><span class="sxs-lookup"><span data-stu-id="f94fe-129">None.</span></span> <span data-ttu-id="f94fe-130">CcServerCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="f94fe-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f94fe-131">傳回類型</span><span class="sxs-lookup"><span data-stu-id="f94fe-131">Return Types</span></span>
<span data-ttu-id="f94fe-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f94fe-133">無</span><span class="sxs-lookup"><span data-stu-id="f94fe-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f94fe-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f94fe-134">See also</span></span>
<span data-ttu-id="f94fe-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f94fe-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f94fe-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f94fe-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f94fe-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f94fe-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f94fe-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f94fe-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

