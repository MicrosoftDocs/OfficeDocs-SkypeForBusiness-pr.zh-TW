---
title: 設定商務用 Skype Server 中的媒體旁路，以永遠略過轉送伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 啟用媒體旁路，以在商務用 Skype Server Enterprise Voice 中永遠略過轉送伺服器。
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804213"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="569dd-103">設定商務用 Skype Server 中的媒體旁路，以永遠略過轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="569dd-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="569dd-104">啟用媒體旁路，以在商務用 Skype Server Enterprise Voice 中永遠略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="569dd-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="569dd-105">如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在 [商務用 Skype] 端點和任何對等的使用者之間，您已設定主幹連線上的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="569dd-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="569dd-106">如果您沒有在商務用 Skype 端點和所有對等機器間都有良好的連線，其各自的主幹連線已啟用媒體旁路，您必須設定全域媒體旁路設定，以在使用媒體旁路時使用網站與地區資訊。</span><span class="sxs-lookup"><span data-stu-id="569dd-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="569dd-107">如此可對媒體略過中繼伺服器的時機有更精確的控制。</span><span class="sxs-lookup"><span data-stu-id="569dd-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="569dd-108">若要這麼做，請使用在 [商務用 Skype Server 中設定媒體旁路全域設定中的步驟，以使用網站與地區資訊](use-site-and-region-information.md) ，並改為 [將子網與網路網站產生關聯](deploy-network.md#BKMK_AssociateSubnets) 。</span><span class="sxs-lookup"><span data-stu-id="569dd-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="569dd-109">全面啟用媒體旁路以永遠略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="569dd-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="569dd-110">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="569dd-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="569dd-111">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="569dd-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="569dd-112">按兩下清單中的 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="569dd-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="569dd-113">在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="569dd-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="569dd-114">按一下 **[永遠略過]**。</span><span class="sxs-lookup"><span data-stu-id="569dd-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="569dd-115">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="569dd-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="569dd-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="569dd-116">See also</span></span>

[<span data-ttu-id="569dd-117">在商務用 Skype 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="569dd-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="569dd-118">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="569dd-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

