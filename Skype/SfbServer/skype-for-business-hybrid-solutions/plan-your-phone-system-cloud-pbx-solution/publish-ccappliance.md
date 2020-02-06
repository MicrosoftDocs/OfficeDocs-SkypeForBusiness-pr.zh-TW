---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: CcAppliance Cmdlet 會從線上租使用者配置取得高可用性資訊，並將它發佈到主機伺服器上的商務用 Skype 雲端連接器 Edition 裝置。
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824309"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="d323e-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d323e-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="d323e-104">CcAppliance Cmdlet 會從線上租使用者配置取得高可用性資訊，並將它發佈到主機伺服器上的商務用 Skype 雲端連接器 Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="d323e-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="d323e-105">參數</span><span class="sxs-lookup"><span data-stu-id="d323e-105">Parameters</span></span>

<span data-ttu-id="d323e-106">無</span><span class="sxs-lookup"><span data-stu-id="d323e-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d323e-107">範例</span><span class="sxs-lookup"><span data-stu-id="d323e-107">Examples</span></span>
<span data-ttu-id="d323e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d323e-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d323e-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="d323e-109">Example 1</span></span>

<span data-ttu-id="d323e-110">下列範例會從線上租使用者配置中取得高可用性資訊，並將它發佈到主機伺服器上的雲端連接器裝置：</span><span class="sxs-lookup"><span data-stu-id="d323e-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="d323e-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="d323e-111">Detailed Description</span></span>
<span data-ttu-id="d323e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d323e-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d323e-113">高可用性資訊包含 PSTN 網站的中繼伺服器 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d323e-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="d323e-114">新的 DNS A 記錄會新增至在中繼伺服器 IP 位址的 AD 伺服器中。</span><span class="sxs-lookup"><span data-stu-id="d323e-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="d323e-115">新的拓撲專案會更新到中繼伺服器 Fqdn 和 IP 位址的中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="d323e-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="d323e-116">輸入類型</span><span class="sxs-lookup"><span data-stu-id="d323e-116">Input Types</span></span>
<span data-ttu-id="d323e-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d323e-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d323e-118">無。</span><span class="sxs-lookup"><span data-stu-id="d323e-118">None.</span></span> <span data-ttu-id="d323e-119">CcAppliance Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="d323e-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d323e-120">傳回類型</span><span class="sxs-lookup"><span data-stu-id="d323e-120">Return Types</span></span>
<span data-ttu-id="d323e-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d323e-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d323e-122">無</span><span class="sxs-lookup"><span data-stu-id="d323e-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d323e-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d323e-123">See also</span></span>
<span data-ttu-id="d323e-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d323e-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d323e-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d323e-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d323e-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d323e-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d323e-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d323e-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d323e-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d323e-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

