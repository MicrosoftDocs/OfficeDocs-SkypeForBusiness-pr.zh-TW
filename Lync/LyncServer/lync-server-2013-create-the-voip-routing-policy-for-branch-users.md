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
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="86cc2-102">在 Lync Server 2013 中為分支使用者建立 VoIP 路由原則</span><span class="sxs-lookup"><span data-stu-id="86cc2-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cc2-103">_**主題上次修改日期：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="86cc2-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="86cc2-104">我們建議針對分支網站上的使用者建立個別的 [語音 over IP] （VoIP）原則。</span><span class="sxs-lookup"><span data-stu-id="86cc2-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="86cc2-105">此原則應該包含來自 Survivable 分支裝置閘道的出口，或 Survivable 分支伺服器外部閘道，以及從中央網站上的閘道傳出的備份路由。</span><span class="sxs-lookup"><span data-stu-id="86cc2-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="86cc2-106">不論使用者的登錄位置為何，無論是在 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機構或中央網站的備份註冊機構群集上，使用者的 VoIP 原則都將會生效。</span><span class="sxs-lookup"><span data-stu-id="86cc2-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="86cc2-107">為分支使用者設定 VoIP 路由策略</span><span class="sxs-lookup"><span data-stu-id="86cc2-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="86cc2-108">建立使用者層級撥號方案並將其指派給分支使用者。</span><span class="sxs-lookup"><span data-stu-id="86cc2-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="86cc2-109">（請參閱在 [操作] 檔的[Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)）。</span><span class="sxs-lookup"><span data-stu-id="86cc2-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="86cc2-110">指派與使用者在該網站上的撥號習慣相對應的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="86cc2-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="86cc2-111">如果 Survivable 分支裝置或 Survivable 分支伺服器使用者無法容錯移轉到中央網站上的 [備份註冊機] 池，則相同的撥號方案將會生效。</span><span class="sxs-lookup"><span data-stu-id="86cc2-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="86cc2-112">（請參閱在 [操作] 檔的[Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)）。</span><span class="sxs-lookup"><span data-stu-id="86cc2-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="86cc2-113">設定從 Survivable 分支裝置閘道或 Survivable 分支伺服器外部閘道 egresses 的語音路由。</span><span class="sxs-lookup"><span data-stu-id="86cc2-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="86cc2-114">（請參閱在 Operations 檔中在[Lync Server 2013 中建立語音信箱](lync-server-2013-create-a-voice-route.md)。）</span><span class="sxs-lookup"><span data-stu-id="86cc2-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="86cc2-115">在 Survivable 分支裝置上設定備份呼叫路由，或 Survivable 分支伺服器閘道，以指向中央網站上的 [備份註冊器] 池（collocated 與中繼伺服器）。</span><span class="sxs-lookup"><span data-stu-id="86cc2-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="86cc2-116">（請參閱您的 Survivable 分支裝置或 Survivable 分支伺服器廠商檔。）</span><span class="sxs-lookup"><span data-stu-id="86cc2-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86cc2-117">此備份呼叫路線設定可協助確保當 Survivable 分支機搆或 Survivable 分支伺服器無法使用時，分支使用者的撥入呼叫可以正常運作（例如，如果是為了進行維護）。</span><span class="sxs-lookup"><span data-stu-id="86cc2-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="86cc2-118">如果 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機構和轉送器伺服器無法使用，而且使用者已在中央網站上的 [備份註冊機構] 池中註冊，則輸入通話仍會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="86cc2-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="86cc2-119">**後續步驟**：[在 Lync Server 2013 中設定語音信箱重新路由設定](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="86cc2-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

