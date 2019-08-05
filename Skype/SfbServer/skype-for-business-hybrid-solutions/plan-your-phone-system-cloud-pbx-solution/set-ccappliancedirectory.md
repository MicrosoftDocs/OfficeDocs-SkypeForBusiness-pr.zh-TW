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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190648"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="99f52-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="99f52-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="99f52-105">CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。</span><span class="sxs-lookup"><span data-stu-id="99f52-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="99f52-106">所有部署檔案都儲存在這個目錄中。</span><span class="sxs-lookup"><span data-stu-id="99f52-106">All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="99f52-107">範例</span><span class="sxs-lookup"><span data-stu-id="99f52-107">Examples</span></span>
<span data-ttu-id="99f52-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99f52-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="99f52-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="99f52-109">Example 1</span></span>

<span data-ttu-id="99f52-110">下列範例會將主機伺服器上的工作目錄設定為 c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="99f52-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="99f52-111">參數</span><span class="sxs-lookup"><span data-stu-id="99f52-111">Parameters</span></span>
<span data-ttu-id="99f52-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99f52-112"></span></span>

|<span data-ttu-id="99f52-113">**參數**</span><span class="sxs-lookup"><span data-stu-id="99f52-113">**Parameter**</span></span>|<span data-ttu-id="99f52-114">**必要**</span><span class="sxs-lookup"><span data-stu-id="99f52-114">**Required**</span></span>|<span data-ttu-id="99f52-115">**類型**</span><span class="sxs-lookup"><span data-stu-id="99f52-115">**Type**</span></span>|<span data-ttu-id="99f52-116">**說明**</span><span class="sxs-lookup"><span data-stu-id="99f52-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="99f52-117">路徑</span><span class="sxs-lookup"><span data-stu-id="99f52-117">Path</span></span> <br/> | <span data-ttu-id="99f52-118">必要</span><span class="sxs-lookup"><span data-stu-id="99f52-118">Required</span></span> <br/> |<span data-ttu-id="99f52-119">System.String</span><span class="sxs-lookup"><span data-stu-id="99f52-119">System.String</span></span>  <br/> | <span data-ttu-id="99f52-120">指定儲存所有部署檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="99f52-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="99f52-121">輸入類型</span><span class="sxs-lookup"><span data-stu-id="99f52-121">Input Types</span></span>
<span data-ttu-id="99f52-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99f52-122"></span></span>

<span data-ttu-id="99f52-123">無。</span><span class="sxs-lookup"><span data-stu-id="99f52-123">None.</span></span> <span data-ttu-id="99f52-124">CcApplianceDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="99f52-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="99f52-125">傳回類型</span><span class="sxs-lookup"><span data-stu-id="99f52-125">Return Types</span></span>
<span data-ttu-id="99f52-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99f52-126"></span></span>

<span data-ttu-id="99f52-127">無</span><span class="sxs-lookup"><span data-stu-id="99f52-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99f52-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="99f52-128">See also</span></span>
<span data-ttu-id="99f52-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99f52-129"></span></span>

<span data-ttu-id="99f52-130">無</span><span class="sxs-lookup"><span data-stu-id="99f52-130">None</span></span>
  

