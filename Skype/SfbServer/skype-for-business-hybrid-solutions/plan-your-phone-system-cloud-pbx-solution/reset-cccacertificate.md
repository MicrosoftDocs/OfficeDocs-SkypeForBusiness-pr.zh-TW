---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset CcCACertificate Cmdlet 會重新安裝憑證授權單位服務 AD 伺服器，以建立新的根 CA 憑證。
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824249"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="cea21-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="cea21-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="cea21-104">Reset CcCACertificate Cmdlet 會重新安裝憑證授權單位服務 AD 伺服器，以建立新的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="cea21-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="cea21-105">參數</span><span class="sxs-lookup"><span data-stu-id="cea21-105">Parameters</span></span>

<span data-ttu-id="cea21-106">無</span><span class="sxs-lookup"><span data-stu-id="cea21-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="cea21-107">範例</span><span class="sxs-lookup"><span data-stu-id="cea21-107">Examples</span></span>
<span data-ttu-id="cea21-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cea21-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="cea21-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="cea21-109">Example 1</span></span>

<span data-ttu-id="cea21-110">下列範例會重新安裝憑證授權單位服務的 AD Server，以建立新的根 CA 憑證：</span><span class="sxs-lookup"><span data-stu-id="cea21-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="cea21-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="cea21-111">Detailed Description</span></span>
<span data-ttu-id="cea21-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cea21-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="cea21-113">如果根 CA 憑證遭到破壞或不再安全，您必須更新根 ca 憑證，以及根 CA 所頒發的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="cea21-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="cea21-114">Reset CcCACertificate Cmdlet 會吊銷所有憑證、卸載並重新安裝憑證授權單位，然後清除所有與舊版憑證授權單位服務相關的憑證。</span><span class="sxs-lookup"><span data-stu-id="cea21-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="cea21-115">如需詳細資訊，請參閱疑難排解雲端連接器部署中的 "憑證授權單位憑證或頒發給 CMS 的內部憑證、中繼伺服器及 Edge 伺服器的到期或已遭破壞"。</span><span class="sxs-lookup"><span data-stu-id="cea21-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="cea21-116">輸入類型</span><span class="sxs-lookup"><span data-stu-id="cea21-116">Input Types</span></span>
<span data-ttu-id="cea21-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cea21-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="cea21-118">無。</span><span class="sxs-lookup"><span data-stu-id="cea21-118">None.</span></span> <span data-ttu-id="cea21-119">Reset CcCACertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="cea21-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cea21-120">傳回類型</span><span class="sxs-lookup"><span data-stu-id="cea21-120">Return Types</span></span>
<span data-ttu-id="cea21-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cea21-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="cea21-122">無。</span><span class="sxs-lookup"><span data-stu-id="cea21-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cea21-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cea21-123">See also</span></span>
<span data-ttu-id="cea21-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cea21-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="cea21-125">[更新-CcCACertificate](renew-cccacertificate.md)僅限版本1.4。2</span><span class="sxs-lookup"><span data-stu-id="cea21-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="cea21-126">[更新-CcServerCertificate](renew-ccservercertificate.md)僅限版本1.4。2</span><span class="sxs-lookup"><span data-stu-id="cea21-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="cea21-127">[更新-CcCACertificate](update-cccacertificate.md)版本2.0 及更新版本</span><span class="sxs-lookup"><span data-stu-id="cea21-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="cea21-128">[更新-CcServerCertificate](renew-ccservercertificate.md)版本2.0 及更新版本</span><span class="sxs-lookup"><span data-stu-id="cea21-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="cea21-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="cea21-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

