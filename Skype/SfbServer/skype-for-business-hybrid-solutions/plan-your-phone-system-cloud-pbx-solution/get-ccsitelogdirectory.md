---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: CcSiteLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器版本的網站層級記錄。
ms.openlocfilehash: a03c4c0cc3e993fb5e1426f3f27f76a68d081c26
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003353"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="b1458-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="b1458-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="b1458-104">CcSiteLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器版本的網站層級記錄。</span><span class="sxs-lookup"><span data-stu-id="b1458-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="b1458-105">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="b1458-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="b1458-106">參數</span><span class="sxs-lookup"><span data-stu-id="b1458-106">Parameters</span></span>

<span data-ttu-id="b1458-107">無</span><span class="sxs-lookup"><span data-stu-id="b1458-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b1458-108">範例</span><span class="sxs-lookup"><span data-stu-id="b1458-108">Examples</span></span>
<span data-ttu-id="b1458-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b1458-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="b1458-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="b1458-110">Example 1</span></span>

<span data-ttu-id="b1458-111">下列範例顯示了儲存雲端連接器網站記錄檔的目前資料夾：</span><span class="sxs-lookup"><span data-stu-id="b1458-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b1458-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="b1458-112">Detailed Description</span></span>
<span data-ttu-id="b1458-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b1458-113"></span></span>

<span data-ttu-id="b1458-114">預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="b1458-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="b1458-115">您可以執行 CcSiteDirectory Cmdlet 來變更資料夾。</span><span class="sxs-lookup"><span data-stu-id="b1458-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="b1458-116">不會有單獨的 Cmdlet 會變更記錄資料夾位置，而不會變更網站目錄。</span><span class="sxs-lookup"><span data-stu-id="b1458-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b1458-117">輸入類型</span><span class="sxs-lookup"><span data-stu-id="b1458-117">Input Types</span></span>
<span data-ttu-id="b1458-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1458-118"></span></span>

<span data-ttu-id="b1458-119">無。</span><span class="sxs-lookup"><span data-stu-id="b1458-119">None.</span></span> <span data-ttu-id="b1458-120">CcSiteLogDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="b1458-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b1458-121">傳回類型</span><span class="sxs-lookup"><span data-stu-id="b1458-121">Return Types</span></span>
<span data-ttu-id="b1458-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1458-122"></span></span>

<span data-ttu-id="b1458-123">命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="b1458-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1458-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1458-124">See also</span></span>
<span data-ttu-id="b1458-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1458-125"></span></span>

[<span data-ttu-id="b1458-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="b1458-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

