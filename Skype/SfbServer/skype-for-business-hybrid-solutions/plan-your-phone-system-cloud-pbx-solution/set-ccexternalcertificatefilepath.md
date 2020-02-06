---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: CcExternalCertificateFilePath Cmdlet 會指定要儲存中繼伺服器或 Edge 伺服器憑證的路徑。
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824197"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="c575e-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="c575e-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="c575e-104">CcExternalCertificateFilePath Cmdlet 會指定要儲存中繼伺服器或 Edge 伺服器憑證的路徑。</span><span class="sxs-lookup"><span data-stu-id="c575e-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="c575e-105">此憑證在部署期間或新增商務用 Skype 雲端連接器版本的新裝置時是必要的。</span><span class="sxs-lookup"><span data-stu-id="c575e-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="c575e-106">此命令也可讓您在部署後匯入轉送伺服器的新憑證。</span><span class="sxs-lookup"><span data-stu-id="c575e-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="c575e-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="c575e-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c575e-108">範例</span><span class="sxs-lookup"><span data-stu-id="c575e-108">Examples</span></span>
<span data-ttu-id="c575e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c575e-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="c575e-110">Example 1</span></span>

<span data-ttu-id="c575e-111">下列範例會設定 Edge 伺服器的憑證路徑：</span><span class="sxs-lookup"><span data-stu-id="c575e-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="c575e-112">範例 2</span><span class="sxs-lookup"><span data-stu-id="c575e-112">Example 2</span></span>

<span data-ttu-id="c575e-113">下一個範例會設定中繼伺服器的憑證路徑：</span><span class="sxs-lookup"><span data-stu-id="c575e-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="c575e-114">範例 3</span><span class="sxs-lookup"><span data-stu-id="c575e-114">Example 3</span></span>

<span data-ttu-id="c575e-115">下一個範例會更新中繼伺服器的憑證：</span><span class="sxs-lookup"><span data-stu-id="c575e-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="c575e-116">詳細描述</span><span class="sxs-lookup"><span data-stu-id="c575e-116">Detailed Description</span></span>
<span data-ttu-id="c575e-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c575e-118">在部署期間，或在修改拓朴時，您必須指定 Edge 伺服器憑證的路徑，以及中繼伺服器憑證（選用）。</span><span class="sxs-lookup"><span data-stu-id="c575e-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="c575e-119">如果要在閘道與中繼伺服器之間使用 TLS，則需要進行中繼伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="c575e-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="c575e-120">當您部署雲端連接器裝置並想要部署 TLS 時，只能指定將在中繼伺服器上部署之憑證的路徑。</span><span class="sxs-lookup"><span data-stu-id="c575e-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="c575e-121">不過，如果您想要在已部署的裝置上更新轉送憑證，您必須指定路徑和-匯入參數。</span><span class="sxs-lookup"><span data-stu-id="c575e-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="c575e-122">若要查看路徑，請使用 CCExternalCertificateFilePath Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c575e-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c575e-123">參數</span><span class="sxs-lookup"><span data-stu-id="c575e-123">Parameters</span></span>
<span data-ttu-id="c575e-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c575e-125">**參數**</span><span class="sxs-lookup"><span data-stu-id="c575e-125">**Parameter**</span></span>|<span data-ttu-id="c575e-126">**必要**</span><span class="sxs-lookup"><span data-stu-id="c575e-126">**Required**</span></span>|<span data-ttu-id="c575e-127">**類型**</span><span class="sxs-lookup"><span data-stu-id="c575e-127">**Type**</span></span>|<span data-ttu-id="c575e-128">**說明**</span><span class="sxs-lookup"><span data-stu-id="c575e-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c575e-129">目標</span><span class="sxs-lookup"><span data-stu-id="c575e-129">Target</span></span> <br/> | <span data-ttu-id="c575e-130">必要</span><span class="sxs-lookup"><span data-stu-id="c575e-130">Required</span></span> <br/> |<span data-ttu-id="c575e-131">System.String</span><span class="sxs-lookup"><span data-stu-id="c575e-131">System.String</span></span>  <br/> |<span data-ttu-id="c575e-132">所要求的檔路徑類型。</span><span class="sxs-lookup"><span data-stu-id="c575e-132">Type of file path requested.</span></span> <span data-ttu-id="c575e-133">類型包括：</span><span class="sxs-lookup"><span data-stu-id="c575e-133">Types include:</span></span>  <br/> <span data-ttu-id="c575e-134">EdgeServer （預設值）</span><span class="sxs-lookup"><span data-stu-id="c575e-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="c575e-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c575e-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="c575e-136">Import</span><span class="sxs-lookup"><span data-stu-id="c575e-136">Import</span></span>  <br/> |<span data-ttu-id="c575e-137">選用</span><span class="sxs-lookup"><span data-stu-id="c575e-137">Optional</span></span>  <br/> |<span data-ttu-id="c575e-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c575e-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c575e-139">指示必須將憑證匯入到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="c575e-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="c575e-140">如果您是第一次部署裝置，則不需要此參數。</span><span class="sxs-lookup"><span data-stu-id="c575e-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="c575e-141">如果您想要變更已部署版本中的現有憑證，必須輸入參數。</span><span class="sxs-lookup"><span data-stu-id="c575e-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c575e-142">輸入類型</span><span class="sxs-lookup"><span data-stu-id="c575e-142">Input Types</span></span>
<span data-ttu-id="c575e-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c575e-144">CcExternalCertificateFilePath Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="c575e-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c575e-145">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c575e-145">Return Types</span></span>
<span data-ttu-id="c575e-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c575e-147">無</span><span class="sxs-lookup"><span data-stu-id="c575e-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c575e-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c575e-148">See also</span></span>
<span data-ttu-id="c575e-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c575e-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c575e-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="c575e-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

