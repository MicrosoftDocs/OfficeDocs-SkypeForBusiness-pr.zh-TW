---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800843"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="e8242-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="e8242-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="e8242-105">CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。</span><span class="sxs-lookup"><span data-stu-id="e8242-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="e8242-106">所有部署檔案都儲存在這個目錄中。</span><span class="sxs-lookup"><span data-stu-id="e8242-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="e8242-107">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="e8242-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="e8242-108">參數</span><span class="sxs-lookup"><span data-stu-id="e8242-108">Parameters</span></span>

<span data-ttu-id="e8242-109">無</span><span class="sxs-lookup"><span data-stu-id="e8242-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e8242-110">範例</span><span class="sxs-lookup"><span data-stu-id="e8242-110">Examples</span></span>
<span data-ttu-id="e8242-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e8242-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e8242-112">範例 1</span><span class="sxs-lookup"><span data-stu-id="e8242-112">Example 1</span></span>

<span data-ttu-id="e8242-113">下列範例顯示了儲存雲端連接器元件配置和虛擬機器檔案的目前資料夾：</span><span class="sxs-lookup"><span data-stu-id="e8242-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="e8242-114">詳細描述</span><span class="sxs-lookup"><span data-stu-id="e8242-114">Detailed Description</span></span>
<span data-ttu-id="e8242-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e8242-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e8242-116">CcApplianceDirectory Cmdlet 顯示所有配置和虛擬機器檔案、記錄及外部憑證儲存在雲端連接器裝置上的位置。</span><span class="sxs-lookup"><span data-stu-id="e8242-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="e8242-117">每個雲端連接器裝置都有四個元件：中繼伺服器、集中式管理商店、邊緣伺服器以及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="e8242-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="e8242-118">預設資料夾為 C:\Users\%userprofile%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="e8242-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="e8242-119">您可以使用 CCApplianceDirectory Cmdlet 變更此資料夾。</span><span class="sxs-lookup"><span data-stu-id="e8242-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e8242-120">輸入類型</span><span class="sxs-lookup"><span data-stu-id="e8242-120">Input Types</span></span>
<span data-ttu-id="e8242-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8242-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e8242-122">無。</span><span class="sxs-lookup"><span data-stu-id="e8242-122">None.</span></span> <span data-ttu-id="e8242-123">CCApplianceDirectory Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="e8242-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e8242-124">傳回類型</span><span class="sxs-lookup"><span data-stu-id="e8242-124">Return Types</span></span>
<span data-ttu-id="e8242-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8242-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e8242-126">命令會傳回檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="e8242-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8242-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8242-127">See also</span></span>
<span data-ttu-id="e8242-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8242-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e8242-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="e8242-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

