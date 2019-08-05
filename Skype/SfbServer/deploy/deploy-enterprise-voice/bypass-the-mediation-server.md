---
title: 在商務用 Skype Server 中設定媒體旁路, 以永遠略過中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 在商務用 Skype Server Enterprise Voice 中啟用媒體旁路, 以永遠略過轉送伺服器。
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187435"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="25d86-103">在商務用 Skype Server 中設定媒體旁路, 以永遠略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="25d86-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="25d86-104">在商務用 Skype Server Enterprise Voice 中啟用媒體旁路, 以永遠略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="25d86-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="25d86-105">如果您使用本主題中的步驟來設定媒體旁路的全域設定, 假設您在商務用 Skype 端點和任何對等的使用者都有良好的連線能力, 您可以在主幹連線上設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="25d86-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="25d86-106">如果您在商務用 Skype 端點與所有對等都已啟用媒體旁路的中繼伺服器之間沒有良好的連線性, 您必須設定全域媒體旁路設定, 才能使用網站和區域資訊使用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="25d86-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="25d86-107">這可讓您在判斷媒體繞過中繼伺服器的時間進行更多控制。</span><span class="sxs-lookup"><span data-stu-id="25d86-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="25d86-108">若要這樣做, 請使用 [在[商務用 Skype 伺服器中設定媒體旁路全域設定] 中的步驟, 以使用網站和區域資訊](use-site-and-region-information.md), 並改為[將子網與網路網站建立關聯](deploy-network.md#BKMK_AssociateSubnets)。</span><span class="sxs-lookup"><span data-stu-id="25d86-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="25d86-109">若要讓媒體不使用全域方式, 就能一直略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="25d86-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="25d86-110">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="25d86-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="25d86-111">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="25d86-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="25d86-112">按兩下清單中的**全域**配置。</span><span class="sxs-lookup"><span data-stu-id="25d86-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="25d86-113">在 [**編輯全域設定**] 頁面上, 選取 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="25d86-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="25d86-114">按一下 [**永遠略過**]。</span><span class="sxs-lookup"><span data-stu-id="25d86-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="25d86-115">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25d86-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="25d86-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="25d86-116">See also</span></span>

[<span data-ttu-id="25d86-117">在商務用 Skype 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="25d86-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="25d86-118">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="25d86-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

