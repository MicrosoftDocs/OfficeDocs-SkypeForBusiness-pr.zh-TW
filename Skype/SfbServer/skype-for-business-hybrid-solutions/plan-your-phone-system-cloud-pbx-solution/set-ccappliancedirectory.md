---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824219"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="ec3b0-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ec3b0-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="ec3b0-105">CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。</span><span class="sxs-lookup"><span data-stu-id="ec3b0-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="ec3b0-106">所有部署檔案都儲存在這個目錄中。</span><span class="sxs-lookup"><span data-stu-id="ec3b0-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ec3b0-107">範例</span><span class="sxs-lookup"><span data-stu-id="ec3b0-107">Examples</span></span>
<span data-ttu-id="ec3b0-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ec3b0-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ec3b0-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="ec3b0-109">Example 1</span></span>

<span data-ttu-id="ec3b0-110">下列範例會將主機伺服器上的工作目錄設定為 c:\cloudconnector\applianceroot：</span><span class="sxs-lookup"><span data-stu-id="ec3b0-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="ec3b0-111">參數</span><span class="sxs-lookup"><span data-stu-id="ec3b0-111">Parameters</span></span>
<span data-ttu-id="ec3b0-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ec3b0-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="ec3b0-113">**參數**</span><span class="sxs-lookup"><span data-stu-id="ec3b0-113">**Parameter**</span></span>|<span data-ttu-id="ec3b0-114">**必要**</span><span class="sxs-lookup"><span data-stu-id="ec3b0-114">**Required**</span></span>|<span data-ttu-id="ec3b0-115">**類型**</span><span class="sxs-lookup"><span data-stu-id="ec3b0-115">**Type**</span></span>|<span data-ttu-id="ec3b0-116">**說明**</span><span class="sxs-lookup"><span data-stu-id="ec3b0-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ec3b0-117">路徑</span><span class="sxs-lookup"><span data-stu-id="ec3b0-117">Path</span></span> <br/> | <span data-ttu-id="ec3b0-118">必要</span><span class="sxs-lookup"><span data-stu-id="ec3b0-118">Required</span></span> <br/> |<span data-ttu-id="ec3b0-119">System.String</span><span class="sxs-lookup"><span data-stu-id="ec3b0-119">System.String</span></span>  <br/> | <span data-ttu-id="ec3b0-120">指定儲存所有部署檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="ec3b0-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ec3b0-121">輸入類型</span><span class="sxs-lookup"><span data-stu-id="ec3b0-121">Input Types</span></span>
<span data-ttu-id="ec3b0-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec3b0-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ec3b0-123">無。</span><span class="sxs-lookup"><span data-stu-id="ec3b0-123">None.</span></span> <span data-ttu-id="ec3b0-124">CcApplianceDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="ec3b0-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ec3b0-125">傳回類型</span><span class="sxs-lookup"><span data-stu-id="ec3b0-125">Return Types</span></span>
<span data-ttu-id="ec3b0-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec3b0-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ec3b0-127">無</span><span class="sxs-lookup"><span data-stu-id="ec3b0-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec3b0-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ec3b0-128">See also</span></span>
<span data-ttu-id="ec3b0-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec3b0-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ec3b0-130">無</span><span class="sxs-lookup"><span data-stu-id="ec3b0-130">None</span></span>
  

