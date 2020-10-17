---
title: Lync Server 2013：為分支使用者建立 VoIP 路由原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff0560c3647374433949fe547a5419c5f788714e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504700"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="93dcd-102">在 Lync Server 2013 中建立分支使用者的 VoIP 路由原則</span><span class="sxs-lookup"><span data-stu-id="93dcd-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93dcd-103">_**主題上次修改日期：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="93dcd-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="93dcd-104">我們建議您為分支網站的使用者建立個別的 VoIP 原則。</span><span class="sxs-lookup"><span data-stu-id="93dcd-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="93dcd-105">此原則應包含從中央網站之 Survivable Branch 裝置閘道或 Survivable Branch 伺服器外部閘道的傳出的路由，以及從閘道傳出的備份路由。</span><span class="sxs-lookup"><span data-stu-id="93dcd-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="93dcd-106">不論使用者登錄的位置為何，不論是在 Survivable Branch 裝置或 Survivable Branch Server 上的註冊機上，或是在中央網站的備份註冊機構叢集上，使用者的 VoIP 原則都是有效的。</span><span class="sxs-lookup"><span data-stu-id="93dcd-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="93dcd-107">若要為分支使用者設定 VoIP 路由原則</span><span class="sxs-lookup"><span data-stu-id="93dcd-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="93dcd-108">建立使用者層級撥號對應表，並將其指派給分支使用者。</span><span class="sxs-lookup"><span data-stu-id="93dcd-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="93dcd-109"> (請參閱 Operations 檔中的在 [Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表。 ) </span><span class="sxs-lookup"><span data-stu-id="93dcd-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="93dcd-110">指派與該網站上使用者撥號習慣對應的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="93dcd-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="93dcd-111">如果 Survivable 分支裝置或 Survivable Branch 伺服器使用者容錯移轉至中央網站的備份註冊機構集區，則相同的撥號對應表會生效。</span><span class="sxs-lookup"><span data-stu-id="93dcd-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="93dcd-112"> (請參閱 Operations 檔中的在 [Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表。 ) </span><span class="sxs-lookup"><span data-stu-id="93dcd-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="93dcd-113">設定從 Survivable Branch 裝置閘道或 Survivable Branch Server 外部閘道 egresses 的語音路由。</span><span class="sxs-lookup"><span data-stu-id="93dcd-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="93dcd-114"> (請參閱 Operations 檔中的在 [Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md) 。 ) </span><span class="sxs-lookup"><span data-stu-id="93dcd-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="93dcd-115">設定 Survivable Branch 裝置或 Survivable Branch Server 閘道上的備份呼叫路由，以指向中央網站上的轉送伺服器)  (組合的備份註冊機集區。</span><span class="sxs-lookup"><span data-stu-id="93dcd-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="93dcd-116"> (請參閱 Survivable Branch 裝置或 Survivable Branch Server 廠商檔。 ) </span><span class="sxs-lookup"><span data-stu-id="93dcd-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93dcd-117">此備份呼叫路由設定可協助確保當 Survivable Branch 裝置或 Survivable Branch 伺服器無法使用時，分支使用者的輸入呼叫可以運作 (例如，如果已關機以進行維護) 。</span><span class="sxs-lookup"><span data-stu-id="93dcd-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="93dcd-118">如果無法使用 Survivable Branch 裝置或 Survivable Branch Server 上的註冊機構和轉送伺服器，且使用者已向中央網站的備份註冊機構集區註冊，則輸入呼叫仍可路由傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="93dcd-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="93dcd-119">**後續步驟**： [在 Lync Server 2013 中設定語音信箱重新路由設定](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="93dcd-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

