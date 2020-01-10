---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: CcSiteDirectory Cmdlet 會設定要儲存商務用 Skype 雲端連接器版本的網站層級配置檔案所在的目錄。 該資料夾將會包含基本 VHD 和雲端連接器設定檔。
ms.openlocfilehash: d0cc8d2a66adb831ea2d85381902eb9d3df7ba6a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003193"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="93c21-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="93c21-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="93c21-105">CcSiteDirectory Cmdlet 會設定要儲存商務用 Skype 雲端連接器版本的網站層級配置檔案所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="93c21-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="93c21-106">該資料夾將會包含基本 VHD 和雲端連接器設定檔。</span><span class="sxs-lookup"><span data-stu-id="93c21-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="93c21-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="93c21-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="93c21-108">範例</span><span class="sxs-lookup"><span data-stu-id="93c21-108">Examples</span></span>
<span data-ttu-id="93c21-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="93c21-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="93c21-110">Example 1</span></span>

<span data-ttu-id="93c21-111">下列範例會將網站根目錄設定為\\SiteShare\CloudConnector：</span><span class="sxs-lookup"><span data-stu-id="93c21-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="93c21-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="93c21-112">Detailed Description</span></span>
<span data-ttu-id="93c21-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-113"></span></span>

<span data-ttu-id="93c21-114">若要提供閘道關聯性與高可用性，可以將雲端連接器裝置合併在網站中。</span><span class="sxs-lookup"><span data-stu-id="93c21-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="93c21-115">使用者已指派給網站，而不是雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="93c21-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="93c21-116">每個網站都有儲存基本 VHD 和雲端連接器安裝檔案的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="93c21-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="93c21-117">裝置會在部署期間使用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="93c21-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="93c21-118">這個資料夾應該與雲端連接器網站中的所有其他裝置共用。</span><span class="sxs-lookup"><span data-stu-id="93c21-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="93c21-119">預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="93c21-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="93c21-120">您可以使用 CcSiteDirectory Cmdlet 來查看路徑。</span><span class="sxs-lookup"><span data-stu-id="93c21-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="93c21-121">參數</span><span class="sxs-lookup"><span data-stu-id="93c21-121">Parameters</span></span>
<span data-ttu-id="93c21-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-122"></span></span>

|<span data-ttu-id="93c21-123">**參數**</span><span class="sxs-lookup"><span data-stu-id="93c21-123">**Parameter**</span></span>|<span data-ttu-id="93c21-124">**必要**</span><span class="sxs-lookup"><span data-stu-id="93c21-124">**Required**</span></span>|<span data-ttu-id="93c21-125">**類型**</span><span class="sxs-lookup"><span data-stu-id="93c21-125">**Type**</span></span>|<span data-ttu-id="93c21-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="93c21-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="93c21-127">路徑</span><span class="sxs-lookup"><span data-stu-id="93c21-127">Path</span></span> <br/> | <span data-ttu-id="93c21-128">必要</span><span class="sxs-lookup"><span data-stu-id="93c21-128">Required</span></span> <br/> | <span data-ttu-id="93c21-129">System.String</span><span class="sxs-lookup"><span data-stu-id="93c21-129">System.String</span></span> <br/> |<span data-ttu-id="93c21-130">提供將儲存雲端連接器網站檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="93c21-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="93c21-131">輸入類型</span><span class="sxs-lookup"><span data-stu-id="93c21-131">Input Types</span></span>
<span data-ttu-id="93c21-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-132"></span></span>

<span data-ttu-id="93c21-133">無。</span><span class="sxs-lookup"><span data-stu-id="93c21-133">None.</span></span> <span data-ttu-id="93c21-134">CcSiteDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="93c21-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="93c21-135">傳回類型</span><span class="sxs-lookup"><span data-stu-id="93c21-135">Return Types</span></span>
<span data-ttu-id="93c21-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-136"></span></span>

<span data-ttu-id="93c21-137">無</span><span class="sxs-lookup"><span data-stu-id="93c21-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93c21-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93c21-138">See also</span></span>
<span data-ttu-id="93c21-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="93c21-139"></span></span>

[<span data-ttu-id="93c21-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="93c21-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

