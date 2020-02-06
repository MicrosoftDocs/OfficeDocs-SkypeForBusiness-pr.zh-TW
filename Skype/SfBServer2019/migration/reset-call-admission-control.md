---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果舊版前端池是託管 [呼叫許可控制] （CAC），您必須先將 CAC 託管到商務用 Skype Server 2019 池，才能移除舊版的前端池。
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812801"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="782bc-103">重設通話許可控制</span><span class="sxs-lookup"><span data-stu-id="782bc-103">Reset call admission control</span></span>

<span data-ttu-id="782bc-104">如果舊版前端池是託管 [呼叫許可控制] （CAC），您必須先將 CAC 託管到商務用 Skype Server 2019 池，才能移除舊版的前端池。</span><span class="sxs-lookup"><span data-stu-id="782bc-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="782bc-105">若要重設 CAC</span><span class="sxs-lookup"><span data-stu-id="782bc-105">To reset CAC</span></span>

1. <span data-ttu-id="782bc-106">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="782bc-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="782bc-107">以滑鼠右鍵按一下網站節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="782bc-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="782bc-108">在 [**呼叫許可控制設定**] 底下，請確認已選取 [**啟用撥號許可控制**]。</span><span class="sxs-lookup"><span data-stu-id="782bc-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="782bc-109">在 [前端池] 底下，**若要執行 [呼叫許可控制] （CAC）**，請選取要裝載 CAC 的商務用 Skype Server 2019 池，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="782bc-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="782bc-110">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="782bc-110">Publish the topology.</span></span>
    

