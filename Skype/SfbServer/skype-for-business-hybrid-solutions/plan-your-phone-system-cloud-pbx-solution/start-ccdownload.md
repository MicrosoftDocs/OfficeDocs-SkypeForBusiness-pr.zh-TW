---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: CcDownload Cmdlet 會以同步方式下載商務用 Skype 雲端連接器版本 bits 與 msi 檔案。
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003183"
---
# <a name="start-ccdownload"></a><span data-ttu-id="c10a7-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="c10a7-103">Start-CcDownload</span></span>
 
<span data-ttu-id="c10a7-104">CcDownload Cmdlet 會以同步方式下載商務用 Skype 雲端連接器版本 bits 與 msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="c10a7-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="c10a7-105">使用雲端連接器版本2.0 和更新版本時，您也可以指定 DownloadBitsOnly 參數。</span><span class="sxs-lookup"><span data-stu-id="c10a7-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c10a7-106">範例</span><span class="sxs-lookup"><span data-stu-id="c10a7-106">Examples</span></span>
<span data-ttu-id="c10a7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="c10a7-108">範例 1</span><span class="sxs-lookup"><span data-stu-id="c10a7-108">Example 1</span></span>

<span data-ttu-id="c10a7-109">下列範例會從雲端連接器公用下載網站同步下載雲端連接器位和 msi 檔案：</span><span class="sxs-lookup"><span data-stu-id="c10a7-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="c10a7-110">範例 2</span><span class="sxs-lookup"><span data-stu-id="c10a7-110">Example 2</span></span>

<span data-ttu-id="c10a7-111">下一個範例會從私人下載網站同步下載雲端連接器位和 msi 檔案：</span><span class="sxs-lookup"><span data-stu-id="c10a7-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="c10a7-112">範例 3</span><span class="sxs-lookup"><span data-stu-id="c10a7-112">Example 3</span></span>

<span data-ttu-id="c10a7-113">第三個範例會從私人下載網站同步下載雲端連接器位和 msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="c10a7-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="c10a7-114">詳細描述</span><span class="sxs-lookup"><span data-stu-id="c10a7-114">Detailed Description</span></span>
<span data-ttu-id="c10a7-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-115"></span></span>

<span data-ttu-id="c10a7-116">如果下載網站中有可用的新版本，CcDownload 將會從下載網站下載並安裝 msi 檔案，然後以同步方式下載雲端連接器 bits。</span><span class="sxs-lookup"><span data-stu-id="c10a7-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="c10a7-117">如果沒有 msi 檔案的新版本，CcDownload 將只下載雲端連接器位。</span><span class="sxs-lookup"><span data-stu-id="c10a7-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="c10a7-118">如果已下載雲端連接器位，就不會執行 Start CcDownload。</span><span class="sxs-lookup"><span data-stu-id="c10a7-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c10a7-119">參數</span><span class="sxs-lookup"><span data-stu-id="c10a7-119">Parameters</span></span>
<span data-ttu-id="c10a7-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-120"></span></span>

|<span data-ttu-id="c10a7-121">**參數**</span><span class="sxs-lookup"><span data-stu-id="c10a7-121">**Parameter**</span></span>|<span data-ttu-id="c10a7-122">**必要**</span><span class="sxs-lookup"><span data-stu-id="c10a7-122">**Required**</span></span>|<span data-ttu-id="c10a7-123">**類型**</span><span class="sxs-lookup"><span data-stu-id="c10a7-123">**Type**</span></span>|<span data-ttu-id="c10a7-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="c10a7-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c10a7-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="c10a7-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="c10a7-126">選用</span><span class="sxs-lookup"><span data-stu-id="c10a7-126">Optional</span></span> <br/> |<span data-ttu-id="c10a7-127">System.String</span><span class="sxs-lookup"><span data-stu-id="c10a7-127">System.String</span></span>  <br/> | <span data-ttu-id="c10a7-128">私人下載網站中的特定雲端連接器版本完整 URL。</span><span class="sxs-lookup"><span data-stu-id="c10a7-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="c10a7-129">使用此參數時請謹慎，請務必注意您要下載的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="c10a7-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="c10a7-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="c10a7-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="c10a7-131">選用</span><span class="sxs-lookup"><span data-stu-id="c10a7-131">Optional</span></span>  <br/> |<span data-ttu-id="c10a7-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c10a7-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c10a7-133">略過步驟若要從下載網站下載並安裝 MSI，請只下載雲端連接器位。</span><span class="sxs-lookup"><span data-stu-id="c10a7-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c10a7-134">輸入類型</span><span class="sxs-lookup"><span data-stu-id="c10a7-134">Input Types</span></span>
<span data-ttu-id="c10a7-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-135"></span></span>

<span data-ttu-id="c10a7-136">無。</span><span class="sxs-lookup"><span data-stu-id="c10a7-136">None.</span></span> <span data-ttu-id="c10a7-137">Start-CcDownload Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="c10a7-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c10a7-138">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c10a7-138">Return Types</span></span>
<span data-ttu-id="c10a7-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-139"></span></span>

<span data-ttu-id="c10a7-140">無</span><span class="sxs-lookup"><span data-stu-id="c10a7-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c10a7-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c10a7-141">See also</span></span>
<span data-ttu-id="c10a7-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c10a7-142"></span></span>

<span data-ttu-id="c10a7-143">無</span><span class="sxs-lookup"><span data-stu-id="c10a7-143">None</span></span>
  

