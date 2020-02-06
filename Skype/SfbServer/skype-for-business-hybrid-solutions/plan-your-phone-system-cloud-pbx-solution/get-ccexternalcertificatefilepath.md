---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype 雲端連接器版本部署的外部憑證檔路徑。 使用者準備這個證書。
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799903"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="13bfc-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="13bfc-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="13bfc-105">CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype 雲端連接器版本部署的外部憑證檔路徑。</span><span class="sxs-lookup"><span data-stu-id="13bfc-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="13bfc-106">使用者準備這個證書。</span><span class="sxs-lookup"><span data-stu-id="13bfc-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="13bfc-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="13bfc-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="13bfc-108">範例</span><span class="sxs-lookup"><span data-stu-id="13bfc-108">Examples</span></span>
<span data-ttu-id="13bfc-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="13bfc-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="13bfc-110">Example 1</span></span>

<span data-ttu-id="13bfc-111">下列範例顯示 Edge 伺服器的憑證路徑：</span><span class="sxs-lookup"><span data-stu-id="13bfc-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="13bfc-112">範例 2</span><span class="sxs-lookup"><span data-stu-id="13bfc-112">Example 2</span></span>

<span data-ttu-id="13bfc-113">下列範例顯示為中繼伺服器所設定的憑證：</span><span class="sxs-lookup"><span data-stu-id="13bfc-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="13bfc-114">詳細描述</span><span class="sxs-lookup"><span data-stu-id="13bfc-114">Detailed Description</span></span>
<span data-ttu-id="13bfc-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="13bfc-116">在部署期間或在修改拓撲時，您必須指定 Edge 伺服器憑證的路徑，也可以為中繼伺服器指定路徑。</span><span class="sxs-lookup"><span data-stu-id="13bfc-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="13bfc-117">如果要在閘道與中繼伺服器之間使用 TLS，則需要進行中繼伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="13bfc-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="13bfc-118">若要變更路徑，請使用 CcExternalCertificateFilePath Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="13bfc-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="13bfc-119">參數</span><span class="sxs-lookup"><span data-stu-id="13bfc-119">Parameters</span></span>
<span data-ttu-id="13bfc-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="13bfc-121">**參數**</span><span class="sxs-lookup"><span data-stu-id="13bfc-121">**Parameter**</span></span>|<span data-ttu-id="13bfc-122">**必要**</span><span class="sxs-lookup"><span data-stu-id="13bfc-122">**Required**</span></span>|<span data-ttu-id="13bfc-123">**類型**</span><span class="sxs-lookup"><span data-stu-id="13bfc-123">**Type**</span></span>|<span data-ttu-id="13bfc-124">**說明**</span><span class="sxs-lookup"><span data-stu-id="13bfc-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13bfc-125">目標</span><span class="sxs-lookup"><span data-stu-id="13bfc-125">Target</span></span>  <br/> |<span data-ttu-id="13bfc-126">選用</span><span class="sxs-lookup"><span data-stu-id="13bfc-126">Optional</span></span>  <br/> | <span data-ttu-id="13bfc-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="13bfc-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="13bfc-128">所要求的檔路徑類型。</span><span class="sxs-lookup"><span data-stu-id="13bfc-128">Type of file path requested.</span></span> <span data-ttu-id="13bfc-129">類型包括：</span><span class="sxs-lookup"><span data-stu-id="13bfc-129">Types include:</span></span>  <br/> <span data-ttu-id="13bfc-130">EdgeServer （預設值）</span><span class="sxs-lookup"><span data-stu-id="13bfc-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="13bfc-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="13bfc-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="13bfc-132">輸入類型</span><span class="sxs-lookup"><span data-stu-id="13bfc-132">Input Types</span></span>
<span data-ttu-id="13bfc-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="13bfc-134">CcExternalCertificateFilePath Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="13bfc-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="13bfc-135">傳回類型</span><span class="sxs-lookup"><span data-stu-id="13bfc-135">Return Types</span></span>
<span data-ttu-id="13bfc-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="13bfc-137">命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="13bfc-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13bfc-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13bfc-138">See also</span></span>
<span data-ttu-id="13bfc-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13bfc-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="13bfc-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="13bfc-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

