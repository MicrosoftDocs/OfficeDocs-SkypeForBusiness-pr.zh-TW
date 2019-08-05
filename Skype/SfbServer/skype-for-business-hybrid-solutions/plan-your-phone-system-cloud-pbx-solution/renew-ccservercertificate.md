---
title: 更新-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 當 CcServerCertificate Cmdlet 接近到期或已到期時, 會更新商務用 Skype 雲端連接器版本的憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190672"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="4ba25-104">更新-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4ba25-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="4ba25-105">當 CcServerCertificate Cmdlet 接近到期或已到期時, 會更新商務用 Skype 雲端連接器版本的憑證。</span><span class="sxs-lookup"><span data-stu-id="4ba25-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="4ba25-106">此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。</span><span class="sxs-lookup"><span data-stu-id="4ba25-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="4ba25-107">範例</span><span class="sxs-lookup"><span data-stu-id="4ba25-107">Examples</span></span>
<span data-ttu-id="4ba25-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="4ba25-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="4ba25-109">Example 1</span></span>

<span data-ttu-id="4ba25-110">下列範例會在憑證接近到期或已到期時, 續約中央管理商店、中繼伺服器和 Edge 伺服器的憑證:</span><span class="sxs-lookup"><span data-stu-id="4ba25-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="4ba25-111">範例 2</span><span class="sxs-lookup"><span data-stu-id="4ba25-111">Example 2</span></span>

<span data-ttu-id="4ba25-112">下個範例會在伺服器和 Edge 伺服器接近到期或過期時, 續約的憑證:</span><span class="sxs-lookup"><span data-stu-id="4ba25-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="4ba25-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="4ba25-113">Detailed Description</span></span>
<span data-ttu-id="4ba25-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-114"></span></span>

<span data-ttu-id="4ba25-115">向中央管理商店、中繼伺服器和 Edge 伺服器頒發的雲端連接器內部憑證, 在來自憑證授權單位服務的兩年後有效。</span><span class="sxs-lookup"><span data-stu-id="4ba25-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="4ba25-116">如果證書接近到期或已過期, 請執行 CcServerCertificate Cmdlet 來更新憑證。</span><span class="sxs-lookup"><span data-stu-id="4ba25-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="4ba25-117">參數</span><span class="sxs-lookup"><span data-stu-id="4ba25-117">Parameters</span></span>
<span data-ttu-id="4ba25-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-118"></span></span>

|<span data-ttu-id="4ba25-119">**參數**</span><span class="sxs-lookup"><span data-stu-id="4ba25-119">**Parameter**</span></span>|<span data-ttu-id="4ba25-120">**必要**</span><span class="sxs-lookup"><span data-stu-id="4ba25-120">**Required**</span></span>|<span data-ttu-id="4ba25-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="4ba25-121">**Type**</span></span>|<span data-ttu-id="4ba25-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="4ba25-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ba25-123">角色</span><span class="sxs-lookup"><span data-stu-id="4ba25-123">Roles</span></span>  <br/> |<span data-ttu-id="4ba25-124">選用</span><span class="sxs-lookup"><span data-stu-id="4ba25-124">Optional</span></span>  <br/> |<span data-ttu-id="4ba25-125">System.object</span><span class="sxs-lookup"><span data-stu-id="4ba25-125">System.Array</span></span>  <br/> | <span data-ttu-id="4ba25-126">雲端連接器伺服器角色的陣列。</span><span class="sxs-lookup"><span data-stu-id="4ba25-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4ba25-127">輸入類型</span><span class="sxs-lookup"><span data-stu-id="4ba25-127">Input Types</span></span>
<span data-ttu-id="4ba25-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-128"></span></span>

<span data-ttu-id="4ba25-129">無。</span><span class="sxs-lookup"><span data-stu-id="4ba25-129">None.</span></span> <span data-ttu-id="4ba25-130">CcServerCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="4ba25-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4ba25-131">傳回類型</span><span class="sxs-lookup"><span data-stu-id="4ba25-131">Return Types</span></span>
<span data-ttu-id="4ba25-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-132"></span></span>

<span data-ttu-id="4ba25-133">無</span><span class="sxs-lookup"><span data-stu-id="4ba25-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ba25-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ba25-134">See also</span></span>
<span data-ttu-id="4ba25-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4ba25-135"></span></span>

[<span data-ttu-id="4ba25-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="4ba25-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="4ba25-137">更新-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4ba25-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="4ba25-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="4ba25-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

