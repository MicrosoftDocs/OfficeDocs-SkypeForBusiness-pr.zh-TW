---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 當商務用 Skype 雲端連接器版本接近到期或已到期時，更新-CcServerCertificate Cmdlet 會重新計算憑證。
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003113"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="52aa8-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="52aa8-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="52aa8-104">當商務用 Skype 雲端連接器版本接近到期或已到期時，更新-CcServerCertificate Cmdlet 會重新計算憑證。</span><span class="sxs-lookup"><span data-stu-id="52aa8-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="52aa8-105">範例</span><span class="sxs-lookup"><span data-stu-id="52aa8-105">Examples</span></span>
<span data-ttu-id="52aa8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="52aa8-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="52aa8-107">Example 1</span></span>

<span data-ttu-id="52aa8-108">下列範例會在憑證接近到期或已到期時，續約中央管理商店、中繼伺服器和 Edge 伺服器的憑證：</span><span class="sxs-lookup"><span data-stu-id="52aa8-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="52aa8-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="52aa8-109">Example 2</span></span>

<span data-ttu-id="52aa8-110">下個範例會在伺服器和 Edge 伺服器接近到期或過期時，續約的憑證：</span><span class="sxs-lookup"><span data-stu-id="52aa8-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="52aa8-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="52aa8-111">Detailed Description</span></span>
<span data-ttu-id="52aa8-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-112"></span></span>

<span data-ttu-id="52aa8-113">向中央管理商店、中繼伺服器和 Edge 伺服器頒發的雲端連接器內部憑證，在來自憑證授權單位服務的兩年後有效。</span><span class="sxs-lookup"><span data-stu-id="52aa8-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="52aa8-114">如果證書接近到期或已過期，請執行 CcServerCertificate Cmdlet 來更新證書。</span><span class="sxs-lookup"><span data-stu-id="52aa8-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="52aa8-115">這個命令會取代雲端連接器2.0 和更新版本中的 CcServerCertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="52aa8-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="52aa8-116">參數</span><span class="sxs-lookup"><span data-stu-id="52aa8-116">Parameters</span></span>
<span data-ttu-id="52aa8-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-117"></span></span>

|<span data-ttu-id="52aa8-118">**參數**</span><span class="sxs-lookup"><span data-stu-id="52aa8-118">**Parameter**</span></span>|<span data-ttu-id="52aa8-119">**必要**</span><span class="sxs-lookup"><span data-stu-id="52aa8-119">**Required**</span></span>|<span data-ttu-id="52aa8-120">**類型**</span><span class="sxs-lookup"><span data-stu-id="52aa8-120">**Type**</span></span>|<span data-ttu-id="52aa8-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="52aa8-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52aa8-122">角色</span><span class="sxs-lookup"><span data-stu-id="52aa8-122">Roles</span></span>  <br/> |<span data-ttu-id="52aa8-123">選用</span><span class="sxs-lookup"><span data-stu-id="52aa8-123">Optional</span></span>  <br/> |<span data-ttu-id="52aa8-124">System.object</span><span class="sxs-lookup"><span data-stu-id="52aa8-124">System.Array</span></span>  <br/> | <span data-ttu-id="52aa8-125">雲端連接器伺服器角色的陣列。</span><span class="sxs-lookup"><span data-stu-id="52aa8-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="52aa8-126">輸入類型</span><span class="sxs-lookup"><span data-stu-id="52aa8-126">Input Types</span></span>
<span data-ttu-id="52aa8-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-127"></span></span>

<span data-ttu-id="52aa8-128">無。</span><span class="sxs-lookup"><span data-stu-id="52aa8-128">None.</span></span> <span data-ttu-id="52aa8-129">CcServerCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="52aa8-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="52aa8-130">傳回類型</span><span class="sxs-lookup"><span data-stu-id="52aa8-130">Return Types</span></span>
<span data-ttu-id="52aa8-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-131"></span></span>

<span data-ttu-id="52aa8-132">無</span><span class="sxs-lookup"><span data-stu-id="52aa8-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52aa8-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="52aa8-133">See also</span></span>
<span data-ttu-id="52aa8-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52aa8-134"></span></span>

[<span data-ttu-id="52aa8-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="52aa8-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="52aa8-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="52aa8-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="52aa8-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="52aa8-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

