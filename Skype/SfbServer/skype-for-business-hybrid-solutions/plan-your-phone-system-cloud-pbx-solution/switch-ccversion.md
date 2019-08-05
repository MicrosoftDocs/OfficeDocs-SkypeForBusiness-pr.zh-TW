---
title: 切換 CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: CcVersion Cmdlet 會中斷正在執行的裝置的連線, 並切換到新部署或備份裝置。
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190603"
---
# <a name="switch-ccversion"></a><span data-ttu-id="0abda-103">切換 CcVersion</span><span class="sxs-lookup"><span data-stu-id="0abda-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="0abda-104">CcVersion Cmdlet 會中斷正在執行的裝置的連線, 並切換到新部署或備份裝置。</span><span class="sxs-lookup"><span data-stu-id="0abda-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="0abda-105">範例</span><span class="sxs-lookup"><span data-stu-id="0abda-105">Examples</span></span>
<span data-ttu-id="0abda-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0abda-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="0abda-107">Example 1</span></span>

<span data-ttu-id="0abda-108">下列範例會耗盡目前正在執行的裝置的服務, 然後切換到新部署或備份裝置:</span><span class="sxs-lookup"><span data-stu-id="0abda-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0abda-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="0abda-109">Example 2</span></span>

<span data-ttu-id="0abda-110">下一個範例會排出目前正在執行的裝置的服務, 並在排出服務失敗時強行停止服務。</span><span class="sxs-lookup"><span data-stu-id="0abda-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="0abda-111">然後, 命令會切換到新部署或備份裝置:</span><span class="sxs-lookup"><span data-stu-id="0abda-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="0abda-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="0abda-112">Detailed Description</span></span>
<span data-ttu-id="0abda-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-113"></span></span>

<span data-ttu-id="0abda-114">在中繼伺服器與 Edge 伺服器上耗盡雲端連接器服務的 CcVersion Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0abda-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="0abda-115">所有執行中的通話都將完成, 但裝置將拒絕任何新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0abda-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="0abda-116">在排出之後, 此 Cmdlet 會將執行中的裝置與公司和網際網路網路中斷連線, 關閉所有屬於該裝置的虛擬機器, 然後將備份裝置連線到企業和網際網路網路。</span><span class="sxs-lookup"><span data-stu-id="0abda-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0abda-117">參數</span><span class="sxs-lookup"><span data-stu-id="0abda-117">Parameters</span></span>
<span data-ttu-id="0abda-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-118"></span></span>

|<span data-ttu-id="0abda-119">**參數**</span><span class="sxs-lookup"><span data-stu-id="0abda-119">**Parameter**</span></span>|<span data-ttu-id="0abda-120">**必要**</span><span class="sxs-lookup"><span data-stu-id="0abda-120">**Required**</span></span>|<span data-ttu-id="0abda-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="0abda-121">**Type**</span></span>|<span data-ttu-id="0abda-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="0abda-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0abda-123">Force</span><span class="sxs-lookup"><span data-stu-id="0abda-123">Force</span></span> <br/> | <span data-ttu-id="0abda-124">選用</span><span class="sxs-lookup"><span data-stu-id="0abda-124">Optional</span></span> <br/> |<span data-ttu-id="0abda-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0abda-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="0abda-126">如果排出服務失敗, 請強行停止服務。</span><span class="sxs-lookup"><span data-stu-id="0abda-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0abda-127">輸入類型</span><span class="sxs-lookup"><span data-stu-id="0abda-127">Input Types</span></span>
<span data-ttu-id="0abda-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-128"></span></span>

<span data-ttu-id="0abda-129">無</span><span class="sxs-lookup"><span data-stu-id="0abda-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0abda-130">傳回類型</span><span class="sxs-lookup"><span data-stu-id="0abda-130">Return Types</span></span>
<span data-ttu-id="0abda-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-131"></span></span>

<span data-ttu-id="0abda-132">無</span><span class="sxs-lookup"><span data-stu-id="0abda-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0abda-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0abda-133">See also</span></span>
<span data-ttu-id="0abda-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0abda-134"></span></span>

<span data-ttu-id="0abda-135">無</span><span class="sxs-lookup"><span data-stu-id="0abda-135">None</span></span>
  

