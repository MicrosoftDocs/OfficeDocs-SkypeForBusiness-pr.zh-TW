---
title: 更新-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: CcCACertificate Cmdlet 會更新接近到期或已過期的商務用 Skype 雲端連接器版本根 CA 憑證。
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190579"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="fea9f-103">更新-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="fea9f-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="fea9f-104">CcCACertificate Cmdlet 會更新接近到期或已過期的商務用 Skype 雲端連接器版本根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="fea9f-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="fea9f-105">參數</span><span class="sxs-lookup"><span data-stu-id="fea9f-105">Parameters</span></span>

<span data-ttu-id="fea9f-106">無。</span><span class="sxs-lookup"><span data-stu-id="fea9f-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="fea9f-107">範例</span><span class="sxs-lookup"><span data-stu-id="fea9f-107">Examples</span></span>
<span data-ttu-id="fea9f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fea9f-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="fea9f-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="fea9f-109">Example 1</span></span>

<span data-ttu-id="fea9f-110">下列範例會續約根 CA 憑證:</span><span class="sxs-lookup"><span data-stu-id="fea9f-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="fea9f-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="fea9f-111">Detailed Description</span></span>
<span data-ttu-id="fea9f-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fea9f-112"></span></span>

<span data-ttu-id="fea9f-113">雲端連接器根 CA 憑證的有效期是從已安裝憑證授權單位服務的日期起五年後才能生效。</span><span class="sxs-lookup"><span data-stu-id="fea9f-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="fea9f-114">如果根憑證接近到期或已過期, 請執行 CcCACertificate Cmdlet 來更新證書。</span><span class="sxs-lookup"><span data-stu-id="fea9f-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="fea9f-115">更新根憑證之後, AD Server、管理中心儲存區和 Edge 伺服器將會自動頒發新的憑證。</span><span class="sxs-lookup"><span data-stu-id="fea9f-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="fea9f-116">如果同一個 PSTN 網站中有多個裝置, 請在相同 PSTN 網站的所有裝置中執行 CcCACertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fea9f-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="fea9f-117">最後一個步驟是執行 Export CcRootCertificate, 將根憑證匯出到第一個裝置中的本機檔案, 然後將匯出的憑證複製並安裝到 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="fea9f-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="fea9f-118">這個命令會取代雲端連接器2.0 和更新版本中的 CcCACertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fea9f-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="fea9f-119">輸入類型</span><span class="sxs-lookup"><span data-stu-id="fea9f-119">Input Types</span></span>
<span data-ttu-id="fea9f-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fea9f-120"></span></span>

<span data-ttu-id="fea9f-121">無。</span><span class="sxs-lookup"><span data-stu-id="fea9f-121">None.</span></span> <span data-ttu-id="fea9f-122">CcCACertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="fea9f-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fea9f-123">傳回類型</span><span class="sxs-lookup"><span data-stu-id="fea9f-123">Return Types</span></span>
<span data-ttu-id="fea9f-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fea9f-124"></span></span>

<span data-ttu-id="fea9f-125">無。</span><span class="sxs-lookup"><span data-stu-id="fea9f-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fea9f-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fea9f-126">See also</span></span>
<span data-ttu-id="fea9f-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fea9f-127"></span></span>

[<span data-ttu-id="fea9f-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="fea9f-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="fea9f-129">更新-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="fea9f-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="fea9f-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="fea9f-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

