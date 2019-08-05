---
title: CcVersion
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
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190747"
---
# <a name="get-ccversion"></a><span data-ttu-id="c2b50-104">CcVersion</span><span class="sxs-lookup"><span data-stu-id="c2b50-104">Get-CcVersion</span></span>
 
<span data-ttu-id="c2b50-105">傳回雲端連接器裝置的版本。</span><span class="sxs-lookup"><span data-stu-id="c2b50-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="c2b50-106">CCVersion 只能在雲端連接器的主機電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="c2b50-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="c2b50-107">詳細描述</span><span class="sxs-lookup"><span data-stu-id="c2b50-107">Detailed Description</span></span>

<span data-ttu-id="c2b50-108">根據已安裝的 PowerShell 腳本、裝置目錄中的檔案, 以及部署于主機伺服器上的虛擬機器, 傳回雲端連接器裝置的版本。</span><span class="sxs-lookup"><span data-stu-id="c2b50-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c2b50-109">參數</span><span class="sxs-lookup"><span data-stu-id="c2b50-109">Parameters</span></span>

|<span data-ttu-id="c2b50-110">**參數**</span><span class="sxs-lookup"><span data-stu-id="c2b50-110">**Parameter**</span></span>|<span data-ttu-id="c2b50-111">**必要**</span><span class="sxs-lookup"><span data-stu-id="c2b50-111">**Required**</span></span>|<span data-ttu-id="c2b50-112">**類型**</span><span class="sxs-lookup"><span data-stu-id="c2b50-112">**Type**</span></span>|<span data-ttu-id="c2b50-113">**說明**</span><span class="sxs-lookup"><span data-stu-id="c2b50-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2b50-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="c2b50-114">VersionType</span></span>  <br/> |<span data-ttu-id="c2b50-115">選用</span><span class="sxs-lookup"><span data-stu-id="c2b50-115">Optional</span></span>  <br/> |<span data-ttu-id="c2b50-116">System.String</span><span class="sxs-lookup"><span data-stu-id="c2b50-116">System.String</span></span>  <br/> |<span data-ttu-id="c2b50-117">版本類型。</span><span class="sxs-lookup"><span data-stu-id="c2b50-117">Type of version.</span></span> <span data-ttu-id="c2b50-118">參數的值可以是 RunningScripts、RunningBits、BackupBits 或 All。</span><span class="sxs-lookup"><span data-stu-id="c2b50-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="c2b50-119">預設值為 RunningScripts。</span><span class="sxs-lookup"><span data-stu-id="c2b50-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="c2b50-120">範例</span><span class="sxs-lookup"><span data-stu-id="c2b50-120">Examples</span></span>
<span data-ttu-id="c2b50-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2b50-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="c2b50-122">範例 1</span><span class="sxs-lookup"><span data-stu-id="c2b50-122">Example 1</span></span>

<span data-ttu-id="c2b50-123">下列範例顯示開啟的 PowerShell 主控台中目前執行的腳本的雲端連接器版本:</span><span class="sxs-lookup"><span data-stu-id="c2b50-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="c2b50-124">範例 2</span><span class="sxs-lookup"><span data-stu-id="c2b50-124">Example 2</span></span>

<span data-ttu-id="c2b50-125">下列範例顯示目前正在執行的二進位檔案在虛擬機器上部署的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="c2b50-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="c2b50-126">您可以在 Hyper-v 管理員的 [執行中的虛擬機器名稱] 中查看版本:</span><span class="sxs-lookup"><span data-stu-id="c2b50-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="c2b50-127">輸入類型</span><span class="sxs-lookup"><span data-stu-id="c2b50-127">Input Types</span></span>
<span data-ttu-id="c2b50-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2b50-128"></span></span>

<span data-ttu-id="c2b50-129">無。</span><span class="sxs-lookup"><span data-stu-id="c2b50-129">None.</span></span> <span data-ttu-id="c2b50-130">CcVersion Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="c2b50-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c2b50-131">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c2b50-131">Return Types</span></span>
<span data-ttu-id="c2b50-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2b50-132"></span></span>

<span data-ttu-id="c2b50-133">無。</span><span class="sxs-lookup"><span data-stu-id="c2b50-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2b50-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c2b50-134">See also</span></span>
<span data-ttu-id="c2b50-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2b50-135"></span></span>

<span data-ttu-id="c2b50-136">無。</span><span class="sxs-lookup"><span data-stu-id="c2b50-136">None.</span></span>
  

