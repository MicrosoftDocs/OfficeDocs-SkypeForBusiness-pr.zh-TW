---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果舊版前端集區裝載通話許可控制（CAC），您必須先將 CAC 主控權移至商務用 Skype Server 2019 集區，才能移除舊版前端集區。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753295"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="ba84d-103">重設通話許可控制</span><span class="sxs-lookup"><span data-stu-id="ba84d-103">Reset call admission control</span></span>

<span data-ttu-id="ba84d-104">如果舊版前端集區裝載通話許可控制（CAC），您必須先將 CAC 主控權移至商務用 Skype Server 2019 集區，才能移除舊版前端集區。</span><span class="sxs-lookup"><span data-stu-id="ba84d-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="ba84d-105">重設 CAC</span><span class="sxs-lookup"><span data-stu-id="ba84d-105">To reset CAC</span></span>

1. <span data-ttu-id="ba84d-106">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="ba84d-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ba84d-107">以滑鼠右鍵按一下網站節點，然後按一下 **[編輯屬性]**。</span><span class="sxs-lookup"><span data-stu-id="ba84d-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="ba84d-108">在 **[通話許可控制設定]** 下方，確定已選取 **[啟用通話許可控制]**。</span><span class="sxs-lookup"><span data-stu-id="ba84d-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="ba84d-109">在 [前端集區] 下，**以執行通話許可控制（CAC）**，選取要裝載 CAC 的商務用 Skype Server 2019 集區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ba84d-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="ba84d-110">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="ba84d-110">Publish the topology.</span></span>
    

