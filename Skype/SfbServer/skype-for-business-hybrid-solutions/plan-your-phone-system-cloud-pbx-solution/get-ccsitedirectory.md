---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: CcSiteDirectory Cmdlet 會顯示網站層級設定檔的目前儲存目錄。 該資料夾包含基本 VHD 和商務用 Skype 雲端連接器版本安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003363"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="abc4f-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="abc4f-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="abc4f-106">CcSiteDirectory Cmdlet 會顯示網站層級設定檔的目前儲存目錄。</span><span class="sxs-lookup"><span data-stu-id="abc4f-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="abc4f-107">該資料夾包含基本 VHD 和商務用 Skype 雲端連接器版本安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="abc4f-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="abc4f-108">此資料夾應與雲端連接器網站的所有其他裝置共用。</span><span class="sxs-lookup"><span data-stu-id="abc4f-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="abc4f-109">這個 Cmdlet 適用于雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="abc4f-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="abc4f-110">參數</span><span class="sxs-lookup"><span data-stu-id="abc4f-110">Parameters</span></span>

<span data-ttu-id="abc4f-111">無</span><span class="sxs-lookup"><span data-stu-id="abc4f-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="abc4f-112">範例</span><span class="sxs-lookup"><span data-stu-id="abc4f-112">Examples</span></span>
<span data-ttu-id="abc4f-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="abc4f-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="abc4f-114">範例 1</span><span class="sxs-lookup"><span data-stu-id="abc4f-114">Example 1</span></span>

<span data-ttu-id="abc4f-115">下列範例顯示了儲存雲端連接器元件之配置和虛擬機器檔案的目前資料夾：</span><span class="sxs-lookup"><span data-stu-id="abc4f-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="abc4f-116">詳細描述</span><span class="sxs-lookup"><span data-stu-id="abc4f-116">Detailed Description</span></span>
<span data-ttu-id="abc4f-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="abc4f-117"></span></span>

<span data-ttu-id="abc4f-118">若要提供閘道關聯性與高可用性，可以將雲端連接器裝置合併在網站中。</span><span class="sxs-lookup"><span data-stu-id="abc4f-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="abc4f-119">使用者已指派給網站，而不是雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="abc4f-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="abc4f-120">每個網站都有儲存基本 VHD 和雲端連接器安裝檔案的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="abc4f-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="abc4f-121">裝置會在部署期間使用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="abc4f-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="abc4f-122">預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="abc4f-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="abc4f-123">您可以使用 CcSiteDirectory Cmdlet 變更路徑。</span><span class="sxs-lookup"><span data-stu-id="abc4f-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="abc4f-124">輸入類型</span><span class="sxs-lookup"><span data-stu-id="abc4f-124">Input Types</span></span>
<span data-ttu-id="abc4f-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="abc4f-125"></span></span>

<span data-ttu-id="abc4f-126">無。</span><span class="sxs-lookup"><span data-stu-id="abc4f-126">None.</span></span> <span data-ttu-id="abc4f-127">CcSiteDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="abc4f-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="abc4f-128">傳回類型</span><span class="sxs-lookup"><span data-stu-id="abc4f-128">Return Types</span></span>
<span data-ttu-id="abc4f-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="abc4f-129"></span></span>

<span data-ttu-id="abc4f-130">這個命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="abc4f-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="abc4f-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="abc4f-131">See also</span></span>
<span data-ttu-id="abc4f-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="abc4f-132"></span></span>

[<span data-ttu-id="abc4f-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="abc4f-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

