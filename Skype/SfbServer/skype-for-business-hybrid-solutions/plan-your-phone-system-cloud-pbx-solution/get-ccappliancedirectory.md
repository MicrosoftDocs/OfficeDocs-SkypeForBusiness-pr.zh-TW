---
title: CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190798"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="aaed8-104">CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="aaed8-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="aaed8-105">CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。</span><span class="sxs-lookup"><span data-stu-id="aaed8-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="aaed8-106">所有部署檔案都儲存在這個目錄中。</span><span class="sxs-lookup"><span data-stu-id="aaed8-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="aaed8-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="aaed8-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="aaed8-108">參數</span><span class="sxs-lookup"><span data-stu-id="aaed8-108">Parameters</span></span>

<span data-ttu-id="aaed8-109">無</span><span class="sxs-lookup"><span data-stu-id="aaed8-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="aaed8-110">範例</span><span class="sxs-lookup"><span data-stu-id="aaed8-110">Examples</span></span>
<span data-ttu-id="aaed8-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="aaed8-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="aaed8-112">範例 1</span><span class="sxs-lookup"><span data-stu-id="aaed8-112">Example 1</span></span>

<span data-ttu-id="aaed8-113">下列範例顯示了儲存雲端連接器元件配置和虛擬機器檔案的目前資料夾:</span><span class="sxs-lookup"><span data-stu-id="aaed8-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="aaed8-114">詳細描述</span><span class="sxs-lookup"><span data-stu-id="aaed8-114">Detailed Description</span></span>
<span data-ttu-id="aaed8-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="aaed8-115"></span></span>

<span data-ttu-id="aaed8-116">CcApplianceDirectory Cmdlet 顯示所有配置和虛擬機器檔案、記錄及外部憑證儲存在雲端連接器裝置上的位置。</span><span class="sxs-lookup"><span data-stu-id="aaed8-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="aaed8-117">每個雲端連接器裝置都有四個元件: 中繼伺服器、集中式管理商店、邊緣伺服器以及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="aaed8-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="aaed8-118">預設資料夾為 C:\Users\%userprofile%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="aaed8-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="aaed8-119">您可以使用 CCApplianceDirectory Cmdlet 變更此資料夾。</span><span class="sxs-lookup"><span data-stu-id="aaed8-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="aaed8-120">輸入類型</span><span class="sxs-lookup"><span data-stu-id="aaed8-120">Input Types</span></span>
<span data-ttu-id="aaed8-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aaed8-121"></span></span>

<span data-ttu-id="aaed8-122">無。</span><span class="sxs-lookup"><span data-stu-id="aaed8-122">None.</span></span> <span data-ttu-id="aaed8-123">CCApplianceDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="aaed8-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="aaed8-124">傳回類型</span><span class="sxs-lookup"><span data-stu-id="aaed8-124">Return Types</span></span>
<span data-ttu-id="aaed8-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aaed8-125"></span></span>

<span data-ttu-id="aaed8-126">命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="aaed8-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aaed8-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aaed8-127">See also</span></span>
<span data-ttu-id="aaed8-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="aaed8-128"></span></span>

[<span data-ttu-id="aaed8-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="aaed8-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

