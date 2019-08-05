---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190795"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="36dbf-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="36dbf-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="36dbf-104">Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。</span><span class="sxs-lookup"><span data-stu-id="36dbf-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="36dbf-105">範例</span><span class="sxs-lookup"><span data-stu-id="36dbf-105">Examples</span></span>
<span data-ttu-id="36dbf-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="36dbf-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="36dbf-107">Example 1</span></span>

<span data-ttu-id="36dbf-108">下列範例會將 Path 參數設定為目錄路徑, 而不是檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="36dbf-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="36dbf-109">它會產生檔案 c:\test\CCERootCertificates.p7b。</span><span class="sxs-lookup"><span data-stu-id="36dbf-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="36dbf-110">詳細描述</span><span class="sxs-lookup"><span data-stu-id="36dbf-110">Detailed Description</span></span>
<span data-ttu-id="36dbf-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-111"></span></span>

<span data-ttu-id="36dbf-112">Export CcRootCertificate Cmdlet 可讓您將根及中間憑證儲存至檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="36dbf-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="36dbf-113">在災難復原案例中, 這會很有用。</span><span class="sxs-lookup"><span data-stu-id="36dbf-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="36dbf-114">參數</span><span class="sxs-lookup"><span data-stu-id="36dbf-114">Parameters</span></span>
<span data-ttu-id="36dbf-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-115"></span></span>

|<span data-ttu-id="36dbf-116">**參數**</span><span class="sxs-lookup"><span data-stu-id="36dbf-116">**Parameter**</span></span>|<span data-ttu-id="36dbf-117">**必要**</span><span class="sxs-lookup"><span data-stu-id="36dbf-117">**Required**</span></span>|<span data-ttu-id="36dbf-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="36dbf-118">**Type**</span></span>|<span data-ttu-id="36dbf-119">**說明**</span><span class="sxs-lookup"><span data-stu-id="36dbf-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36dbf-120">路徑</span><span class="sxs-lookup"><span data-stu-id="36dbf-120">Path</span></span>  <br/> |<span data-ttu-id="36dbf-121">必要</span><span class="sxs-lookup"><span data-stu-id="36dbf-121">Required</span></span>  <br/> |<span data-ttu-id="36dbf-122">System.String</span><span class="sxs-lookup"><span data-stu-id="36dbf-122">System.String</span></span>  <br/> |<span data-ttu-id="36dbf-123">要儲存憑證的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="36dbf-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="36dbf-124">輸入類型</span><span class="sxs-lookup"><span data-stu-id="36dbf-124">Input Types</span></span>
<span data-ttu-id="36dbf-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-125"></span></span>

<span data-ttu-id="36dbf-126">無。</span><span class="sxs-lookup"><span data-stu-id="36dbf-126">None.</span></span> <span data-ttu-id="36dbf-127">Export CcRootCertificate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="36dbf-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="36dbf-128">傳回類型</span><span class="sxs-lookup"><span data-stu-id="36dbf-128">Return Types</span></span>
<span data-ttu-id="36dbf-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-129"></span></span>

<span data-ttu-id="36dbf-130">無</span><span class="sxs-lookup"><span data-stu-id="36dbf-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36dbf-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="36dbf-131">See also</span></span>
<span data-ttu-id="36dbf-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36dbf-132"></span></span>

<span data-ttu-id="36dbf-133">無</span><span class="sxs-lookup"><span data-stu-id="36dbf-133">None</span></span>
  

