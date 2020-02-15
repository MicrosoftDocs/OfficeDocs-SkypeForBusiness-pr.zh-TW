---
title: Lync Server 2013： 建立 VoIP 路由原則為分支使用者
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
ms.openlocfilehash: 308c4ad3a7371c9a27f668b79623a512227623b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="d5796-102">在 Lync Server 2013 中建立分支使用者 VoIP 路由原則</span><span class="sxs-lookup"><span data-stu-id="d5796-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5796-103">_**主題上次修改日期：** 2012年-09-23_</span><span class="sxs-lookup"><span data-stu-id="d5796-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="d5796-104">我們建議您為分支網站的使用者建立個別的 VoIP 原則。</span><span class="sxs-lookup"><span data-stu-id="d5796-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="d5796-105">此原則應該包含從 Survivable Branch Appliance 閘道或 Survivable Branch 伺服器外部閘道的輸出路由和備份來自閘道在中央網站的輸出路由。</span><span class="sxs-lookup"><span data-stu-id="d5796-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="d5796-106">不論其中使用者註冊，不論是在備份登錄器叢集在中央網站，或 Survivable Branch Appliance 或 Survivable Branch 伺服器上之登錄器上使用者的 VoIP 原則一律是作用中。</span><span class="sxs-lookup"><span data-stu-id="d5796-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="d5796-107">若要為分支使用者設定 VoIP 路由原則</span><span class="sxs-lookup"><span data-stu-id="d5796-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="d5796-108">建立使用者層級撥號對應表，並將其指派給分公司使用者。</span><span class="sxs-lookup"><span data-stu-id="d5796-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="d5796-109">（請參閱[建立撥號對應表 Lync Server 2013 中](lync-server-2013-create-a-dial-plan.md)的作業文件中。）</span><span class="sxs-lookup"><span data-stu-id="d5796-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="d5796-110">指派與該網站上使用者撥號習慣對應的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="d5796-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="d5796-111">如果 Survivable Branch Appliance 或 Survivable Branch 伺服器的使用者容錯移轉至中央網站的備份登錄器集區，相同的撥號對應表中會生效。</span><span class="sxs-lookup"><span data-stu-id="d5796-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="d5796-112">（請參閱[建立撥號對應表 Lync Server 2013 中](lync-server-2013-create-a-dial-plan.md)的作業文件中。）</span><span class="sxs-lookup"><span data-stu-id="d5796-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="d5796-113">設定從 Survivable Branch Appliance 閘道或 Survivable Branch 伺服器的外部閘道 egresses 語音路由。</span><span class="sxs-lookup"><span data-stu-id="d5796-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="d5796-114">（請參閱[建立 Lync Server 2013 中的語音路由](lync-server-2013-create-a-voice-route.md)作業 > 文件中）。</span><span class="sxs-lookup"><span data-stu-id="d5796-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="d5796-115">Survivable Branch Appliance 或 Survivable Branch 伺服器閘道指向備份登錄器集區 （與中繼伺服器組合） 在中央網站上設定的備份呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d5796-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="d5796-116">（請參閱 Survivable Branch Appliance 或 Survivable Branch 伺服器廠商文件）。</span><span class="sxs-lookup"><span data-stu-id="d5796-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5796-117">此備份通話路由設定有助於確保與分支網站使用者的輸入的呼叫正常的 Survivable Branch Appliance 或 Survivable Branch 伺服器無法使用時 （例如，如果它是向下維護）。</span><span class="sxs-lookup"><span data-stu-id="d5796-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="d5796-118">如果登錄器和中繼伺服器上的 Survivable Branch Appliance 或 Survivable Branch 伺服器都無法使用，而且使用者註冊在中央網站的備份登錄器集區，撥入的通話可以仍然會路由傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="d5796-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="d5796-119">**下一步**：[設定語音信箱重新路由設定 Lync Server 2013 中](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d5796-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

