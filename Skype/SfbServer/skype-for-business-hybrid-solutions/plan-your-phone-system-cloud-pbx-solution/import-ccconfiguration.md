---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799853"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="9f716-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f716-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="9f716-104">從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="9f716-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9f716-105">範例</span><span class="sxs-lookup"><span data-stu-id="9f716-105">Examples</span></span>
<span data-ttu-id="9f716-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9f716-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="9f716-107">Example 1</span></span>

<span data-ttu-id="9f716-108">下列範例會將 CloudConnector 從雲端連接器實例裝置目錄複寫到%SystemDrive%\ProgramData\CloudConnector 目錄：</span><span class="sxs-lookup"><span data-stu-id="9f716-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="9f716-109">詳細描述</span><span class="sxs-lookup"><span data-stu-id="9f716-109">Detailed Description</span></span>
<span data-ttu-id="9f716-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="9f716-111">這個 Cmdlet 會從雲端連接器裝置的裝置目錄將 CloudConnector 複製到%SystemDrive%\ProgramData\CloudConnector 目錄。</span><span class="sxs-lookup"><span data-stu-id="9f716-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="9f716-112">裝置目錄是使用 CcApplianceDirectory Cmdlet 來指定。</span><span class="sxs-lookup"><span data-stu-id="9f716-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="9f716-113">這個 Cmdlet 會覆寫%SystemDrive%\ProgramData\CloudConnector. 中任何現有的檔案</span><span class="sxs-lookup"><span data-stu-id="9f716-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="9f716-114">此命令適用于雲端連接器版本2.0.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="9f716-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9f716-115">參數</span><span class="sxs-lookup"><span data-stu-id="9f716-115">Parameters</span></span>
<span data-ttu-id="9f716-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="9f716-117">**參數**</span><span class="sxs-lookup"><span data-stu-id="9f716-117">**Parameter**</span></span>|<span data-ttu-id="9f716-118">**必要**</span><span class="sxs-lookup"><span data-stu-id="9f716-118">**Required**</span></span>|<span data-ttu-id="9f716-119">**類型**</span><span class="sxs-lookup"><span data-stu-id="9f716-119">**Type**</span></span>|<span data-ttu-id="9f716-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="9f716-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f716-121">Force</span><span class="sxs-lookup"><span data-stu-id="9f716-121">Force</span></span>  <br/> |<span data-ttu-id="9f716-122">選用</span><span class="sxs-lookup"><span data-stu-id="9f716-122">Optional</span></span>  <br/> |<span data-ttu-id="9f716-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9f716-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9f716-124">在%SystemDrive%\ProgramData\CloudConnector 中覆寫現有檔案而不發出通知。</span><span class="sxs-lookup"><span data-stu-id="9f716-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9f716-125">輸入類型</span><span class="sxs-lookup"><span data-stu-id="9f716-125">Input Types</span></span>
<span data-ttu-id="9f716-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="9f716-127">無。</span><span class="sxs-lookup"><span data-stu-id="9f716-127">None.</span></span> <span data-ttu-id="9f716-128">匯入-CcConfiguration Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="9f716-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9f716-129">傳回類型</span><span class="sxs-lookup"><span data-stu-id="9f716-129">Return Types</span></span>
<span data-ttu-id="9f716-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="9f716-131">無。</span><span class="sxs-lookup"><span data-stu-id="9f716-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f716-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9f716-132">See also</span></span>
<span data-ttu-id="9f716-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f716-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="9f716-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f716-134">Export-CcConfiguration</span></span>
  

