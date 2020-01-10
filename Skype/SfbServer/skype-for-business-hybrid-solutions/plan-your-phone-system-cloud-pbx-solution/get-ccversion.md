---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 傳回雲端連接器裝置的版本。 CCVersion 只能在雲端連接器的主機電腦上使用。
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003343"
---
# <a name="get-ccversion"></a><span data-ttu-id="6e4db-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="6e4db-104">Get-CcVersion</span></span>
 
<span data-ttu-id="6e4db-105">傳回雲端連接器裝置的版本。</span><span class="sxs-lookup"><span data-stu-id="6e4db-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="6e4db-106">CCVersion 只能在雲端連接器的主機電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="6e4db-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="6e4db-107">詳細描述</span><span class="sxs-lookup"><span data-stu-id="6e4db-107">Detailed Description</span></span>

<span data-ttu-id="6e4db-108">根據已安裝的 PowerShell 腳本、裝置目錄中的檔案，以及部署于主機伺服器上的虛擬機器，傳回雲端連接器裝置的版本。</span><span class="sxs-lookup"><span data-stu-id="6e4db-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6e4db-109">參數</span><span class="sxs-lookup"><span data-stu-id="6e4db-109">Parameters</span></span>

|<span data-ttu-id="6e4db-110">**參數**</span><span class="sxs-lookup"><span data-stu-id="6e4db-110">**Parameter**</span></span>|<span data-ttu-id="6e4db-111">**必要**</span><span class="sxs-lookup"><span data-stu-id="6e4db-111">**Required**</span></span>|<span data-ttu-id="6e4db-112">**類型**</span><span class="sxs-lookup"><span data-stu-id="6e4db-112">**Type**</span></span>|<span data-ttu-id="6e4db-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="6e4db-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e4db-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="6e4db-114">VersionType</span></span>  <br/> |<span data-ttu-id="6e4db-115">選用</span><span class="sxs-lookup"><span data-stu-id="6e4db-115">Optional</span></span>  <br/> |<span data-ttu-id="6e4db-116">System.String</span><span class="sxs-lookup"><span data-stu-id="6e4db-116">System.String</span></span>  <br/> |<span data-ttu-id="6e4db-117">版本類型。</span><span class="sxs-lookup"><span data-stu-id="6e4db-117">Type of version.</span></span> <span data-ttu-id="6e4db-118">參數的值可以是 RunningScripts、RunningBits、BackupBits 或 All。</span><span class="sxs-lookup"><span data-stu-id="6e4db-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="6e4db-119">預設值為 RunningScripts。</span><span class="sxs-lookup"><span data-stu-id="6e4db-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="6e4db-120">範例</span><span class="sxs-lookup"><span data-stu-id="6e4db-120">Examples</span></span>
<span data-ttu-id="6e4db-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4db-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="6e4db-122">範例 1</span><span class="sxs-lookup"><span data-stu-id="6e4db-122">Example 1</span></span>

<span data-ttu-id="6e4db-123">下列範例顯示開啟的 PowerShell 主控台中目前執行的腳本的雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="6e4db-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="6e4db-124">範例 2</span><span class="sxs-lookup"><span data-stu-id="6e4db-124">Example 2</span></span>

<span data-ttu-id="6e4db-125">下列範例顯示目前正在執行的二進位檔案在虛擬機器上部署的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="6e4db-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="6e4db-126">您可以在 Hyper-v 管理員的 [執行中的虛擬機器名稱] 中查看版本：</span><span class="sxs-lookup"><span data-stu-id="6e4db-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="6e4db-127">輸入類型</span><span class="sxs-lookup"><span data-stu-id="6e4db-127">Input Types</span></span>
<span data-ttu-id="6e4db-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4db-128"></span></span>

<span data-ttu-id="6e4db-129">無。</span><span class="sxs-lookup"><span data-stu-id="6e4db-129">None.</span></span> <span data-ttu-id="6e4db-130">CcVersion Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="6e4db-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6e4db-131">傳回類型</span><span class="sxs-lookup"><span data-stu-id="6e4db-131">Return Types</span></span>
<span data-ttu-id="6e4db-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4db-132"></span></span>

<span data-ttu-id="6e4db-133">無。</span><span class="sxs-lookup"><span data-stu-id="6e4db-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e4db-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6e4db-134">See also</span></span>
<span data-ttu-id="6e4db-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4db-135"></span></span>

<span data-ttu-id="6e4db-136">無。</span><span class="sxs-lookup"><span data-stu-id="6e4db-136">None.</span></span>
  

