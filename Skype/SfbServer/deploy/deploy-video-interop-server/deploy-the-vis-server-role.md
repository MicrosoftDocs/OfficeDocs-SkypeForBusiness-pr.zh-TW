---
title: 在商務用 Skype Server 中部署 VIS 伺服器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 摘要：在商務用 Skype Server 中部署影片互通性伺服器（VIS）角色。
ms.openlocfilehash: 1fadab718a37dba2ffee5338d4dc898316b4d24d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798040"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="33d7c-103">在商務用 Skype Server 中部署 VIS 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="33d7c-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="33d7c-104">**摘要：** 在商務用 Skype Server 中部署影片互通性伺服器（VIS）角色。</span><span class="sxs-lookup"><span data-stu-id="33d7c-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="33d7c-105">若要在剛剛在 [拓撲建立器] 中建立的伺服器上設定 VIS 服務，請啟動 [商務用 Skype Server 部署嚮導]，然後按下 [**安裝或更新商務用 Skype Server 系統**]，然後依照嚮導中的步驟執行：</span><span class="sxs-lookup"><span data-stu-id="33d7c-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="33d7c-106">選取 [**安裝本機配置存放區**]。</span><span class="sxs-lookup"><span data-stu-id="33d7c-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="33d7c-107">選取 [**設定] 或 [移除商務用 Skype Server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="33d7c-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="33d7c-108">選取 [**要求]、[安裝或指派憑證**]。</span><span class="sxs-lookup"><span data-stu-id="33d7c-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="33d7c-109">選取 [**啟動服務**]。</span><span class="sxs-lookup"><span data-stu-id="33d7c-109">Select **Start services**.</span></span>
    
<span data-ttu-id="33d7c-110">此服務的軟體現已安裝並正在執行。</span><span class="sxs-lookup"><span data-stu-id="33d7c-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="33d7c-111">您可以開啟 [服務] mmc 工具，查看商務用 skype **Server 視頻互通性伺服器**服務是否與其他商務用 skype server 服務一起執行。</span><span class="sxs-lookup"><span data-stu-id="33d7c-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="33d7c-112">接下來，您必須設定 VIS 伺服器或池子。</span><span class="sxs-lookup"><span data-stu-id="33d7c-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="33d7c-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="33d7c-113">See also</span></span>

[<span data-ttu-id="33d7c-114">在商務用 Skype Server 中設定視頻交互操作伺服器</span><span class="sxs-lookup"><span data-stu-id="33d7c-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
