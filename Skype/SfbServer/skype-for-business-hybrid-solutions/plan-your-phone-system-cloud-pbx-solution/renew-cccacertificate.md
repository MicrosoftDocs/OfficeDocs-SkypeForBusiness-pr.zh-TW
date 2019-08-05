---
title: 更新-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype 雲端連接器版本根 CA 憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcCACertificate。
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190678"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="9a2e4-104">更新-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9a2e4-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="9a2e4-105">CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype 雲端連接器版本根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="9a2e4-106">此命令已在雲端連接器2.0 和更新版本中變更為 CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="9a2e4-107">參數</span><span class="sxs-lookup"><span data-stu-id="9a2e4-107">Parameters</span></span>

<span data-ttu-id="9a2e4-108">無</span><span class="sxs-lookup"><span data-stu-id="9a2e4-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9a2e4-109">範例</span><span class="sxs-lookup"><span data-stu-id="9a2e4-109">Examples</span></span>
<span data-ttu-id="9a2e4-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9a2e4-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="9a2e4-111">範例 1</span><span class="sxs-lookup"><span data-stu-id="9a2e4-111">Example 1</span></span>

<span data-ttu-id="9a2e4-112">下列範例會續約根 CA 憑證:</span><span class="sxs-lookup"><span data-stu-id="9a2e4-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="9a2e4-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="9a2e4-113">Detailed Description</span></span>
<span data-ttu-id="9a2e4-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9a2e4-114"></span></span>

<span data-ttu-id="9a2e4-115">雲端連接器根 CA 憑證的有效期是從已安裝憑證授權單位服務的日期起五年後才能生效。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="9a2e4-116">如果根憑證接近到期或已到期, 請執行 CcCACertificate Cmdlet 來更新憑證。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="9a2e4-117">更新根憑證之後, AD Server、管理中心儲存區和 Edge 伺服器將會自動頒發新的憑證。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="9a2e4-118">如果同一個 PSTN 網站中有多個裝置, 請在相同 PSTN 網站的所有裝置中執行 CcCACertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="9a2e4-119">最後一個步驟是執行 Export CcRootCertificate, 將根憑證匯出到第一個裝置中的本機檔案, 然後將匯出的憑證複製並安裝到 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9a2e4-120">輸入類型</span><span class="sxs-lookup"><span data-stu-id="9a2e4-120">Input Types</span></span>
<span data-ttu-id="9a2e4-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a2e4-121"></span></span>

<span data-ttu-id="9a2e4-122">無。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-122">None.</span></span> <span data-ttu-id="9a2e4-123">CcCACertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="9a2e4-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9a2e4-124">傳回類型</span><span class="sxs-lookup"><span data-stu-id="9a2e4-124">Return Types</span></span>
<span data-ttu-id="9a2e4-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a2e4-125"></span></span>

<span data-ttu-id="9a2e4-126">無</span><span class="sxs-lookup"><span data-stu-id="9a2e4-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a2e4-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9a2e4-127">See also</span></span>
<span data-ttu-id="9a2e4-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a2e4-128"></span></span>

[<span data-ttu-id="9a2e4-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9a2e4-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="9a2e4-130">更新-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9a2e4-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="9a2e4-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="9a2e4-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

