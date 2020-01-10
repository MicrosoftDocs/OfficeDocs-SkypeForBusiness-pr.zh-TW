---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器 Edition 裝置的記錄。
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003393"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="62ec0-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="62ec0-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="62ec0-104">CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器 Edition 裝置的記錄。</span><span class="sxs-lookup"><span data-stu-id="62ec0-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="62ec0-105">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="62ec0-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="62ec0-106">參數</span><span class="sxs-lookup"><span data-stu-id="62ec0-106">Parameters</span></span>

<span data-ttu-id="62ec0-107">無</span><span class="sxs-lookup"><span data-stu-id="62ec0-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="62ec0-108">範例</span><span class="sxs-lookup"><span data-stu-id="62ec0-108">Examples</span></span>
<span data-ttu-id="62ec0-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="62ec0-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="62ec0-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="62ec0-110">Example 1</span></span>

<span data-ttu-id="62ec0-111">下列範例會顯示儲存雲端連接器目前裝置記錄的目前資料夾：</span><span class="sxs-lookup"><span data-stu-id="62ec0-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="62ec0-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="62ec0-112">Detailed Description</span></span>
<span data-ttu-id="62ec0-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="62ec0-113"></span></span>

<span data-ttu-id="62ec0-114">CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存雲端連接器裝置的記錄。</span><span class="sxs-lookup"><span data-stu-id="62ec0-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="62ec0-115">預設資料夾為 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="62ec0-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="62ec0-116">您可以使用 CcApplianceDirectory Cmdlet 變更目錄。</span><span class="sxs-lookup"><span data-stu-id="62ec0-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="62ec0-117">注意：沒有變更 [記錄] 資料夾位置，而不會變更裝置目錄的任何 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62ec0-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="62ec0-118">輸入類型</span><span class="sxs-lookup"><span data-stu-id="62ec0-118">Input Types</span></span>
<span data-ttu-id="62ec0-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62ec0-119"></span></span>

<span data-ttu-id="62ec0-120">無。</span><span class="sxs-lookup"><span data-stu-id="62ec0-120">None.</span></span> <span data-ttu-id="62ec0-121">CcApplianceLogDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="62ec0-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="62ec0-122">傳回類型</span><span class="sxs-lookup"><span data-stu-id="62ec0-122">Return Types</span></span>
<span data-ttu-id="62ec0-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62ec0-123"></span></span>

<span data-ttu-id="62ec0-124">這個命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="62ec0-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62ec0-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="62ec0-125">See also</span></span>
<span data-ttu-id="62ec0-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62ec0-126"></span></span>

[<span data-ttu-id="62ec0-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="62ec0-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

