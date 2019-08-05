---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 將商務用 Skype 雲端連接器版本設定匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190822"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="7cd3b-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cd3b-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="7cd3b-104">將商務用 Skype 雲端連接器版本設定匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="7cd3b-105">範例</span><span class="sxs-lookup"><span data-stu-id="7cd3b-105">Examples</span></span>
<span data-ttu-id="7cd3b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="7cd3b-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="7cd3b-107">Example 1</span></span>

<span data-ttu-id="7cd3b-108">下列範例會將 Path 參數設定為完整的檔案路徑, 並將設定匯出至該檔案。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="7cd3b-109">詳細描述</span><span class="sxs-lookup"><span data-stu-id="7cd3b-109">Detailed Description</span></span>
<span data-ttu-id="7cd3b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-110"></span></span>

<span data-ttu-id="7cd3b-111">Export CcConfiguration Cmdlet 可讓您將雲端連接器設定儲存至選取路徑中的檔案。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="7cd3b-112">此命令是在雲端連接器版本2.0 中引入。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7cd3b-113">參數</span><span class="sxs-lookup"><span data-stu-id="7cd3b-113">Parameters</span></span>
<span data-ttu-id="7cd3b-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-114"></span></span>

|<span data-ttu-id="7cd3b-115">**參數**</span><span class="sxs-lookup"><span data-stu-id="7cd3b-115">**Parameter**</span></span>|<span data-ttu-id="7cd3b-116">**必要**</span><span class="sxs-lookup"><span data-stu-id="7cd3b-116">**Required**</span></span>|<span data-ttu-id="7cd3b-117">**類型**</span><span class="sxs-lookup"><span data-stu-id="7cd3b-117">**Type**</span></span>|<span data-ttu-id="7cd3b-118">**說明**</span><span class="sxs-lookup"><span data-stu-id="7cd3b-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7cd3b-119">路徑</span><span class="sxs-lookup"><span data-stu-id="7cd3b-119">Path</span></span>  <br/> |<span data-ttu-id="7cd3b-120">必要</span><span class="sxs-lookup"><span data-stu-id="7cd3b-120">Required</span></span>  <br/> |<span data-ttu-id="7cd3b-121">System.String</span><span class="sxs-lookup"><span data-stu-id="7cd3b-121">System.String</span></span>  <br/> |<span data-ttu-id="7cd3b-122">將儲存雲端連接器設定的完整檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7cd3b-123">輸入類型</span><span class="sxs-lookup"><span data-stu-id="7cd3b-123">Input Types</span></span>
<span data-ttu-id="7cd3b-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-124"></span></span>

<span data-ttu-id="7cd3b-125">無。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-125">None.</span></span> <span data-ttu-id="7cd3b-126">Export CcConfiguration Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7cd3b-127">傳回類型</span><span class="sxs-lookup"><span data-stu-id="7cd3b-127">Return Types</span></span>
<span data-ttu-id="7cd3b-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-128"></span></span>

<span data-ttu-id="7cd3b-129">無。</span><span class="sxs-lookup"><span data-stu-id="7cd3b-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7cd3b-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7cd3b-130">See also</span></span>
<span data-ttu-id="7cd3b-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7cd3b-131"></span></span>

<span data-ttu-id="7cd3b-132">匯入-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cd3b-132">Import-CcConfiguration</span></span>
  

