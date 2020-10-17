---
title: Lync Server 2013：設定媒體旁路以永遠略過轉送伺服器
description: Lync Server 2013：設定媒體旁路，以永遠略過轉送伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b4981c7b12700d2f0bbf0bf05c8a51623bb8ba9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552689"
---
# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e96b8-103">在 Lync Server 2013 中設定媒體旁路，以永遠略過轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="e96b8-103">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e96b8-104">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e96b8-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e96b8-105">本主題假設您已針對想要讓媒體略過中繼伺服器的特定網站或服務，為所有與對等 (公用交換電話網路 (PSTN) 閘道、IP-PBX 或是與網際網路電話語音服務提供者 (ITSP) 的工作階段界限控制器 (SBC)) 的主幹連線設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="e96b8-105">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="e96b8-106">您無法設定媒體一律略過中繼伺服器，同時又啟用通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="e96b8-106">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="e96b8-107">在 Lync Server 控制台使用者介面中，這些設定是不相容的，因此是相互排斥的設定。</span><span class="sxs-lookup"><span data-stu-id="e96b8-107">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="e96b8-108">除了針對與中繼伺服器的對等相關聯的個別主幹連線啟用媒體旁路，您還必須設定全域的媒體旁路設定。</span><span class="sxs-lookup"><span data-stu-id="e96b8-108">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="e96b8-109">如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在 Lync 端點和任何對等的使用者之間，您已在主幹連線上設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="e96b8-109">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="e96b8-110">如果 Lync Server 端點和所有對等的轉送伺服器都未啟用媒體旁路之各自的主幹連線，您必須設定全域媒體旁路設定，以在使用媒體旁路時使用網站與地區資訊。</span><span class="sxs-lookup"><span data-stu-id="e96b8-110">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="e96b8-111">如此可對媒體略過中繼伺服器的時機有更精確的控制。</span><span class="sxs-lookup"><span data-stu-id="e96b8-111">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="e96b8-112">若要這麼做，請使用在 [lync server 2013 中設定媒體旁路全域設定中的步驟，使用網站與地區資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) ，並 [在 lync Server 2013 中將子網與網路網站產生關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md) 。</span><span class="sxs-lookup"><span data-stu-id="e96b8-112">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e96b8-113">全面啟用媒體旁路以永遠略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e96b8-113">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="e96b8-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e96b8-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e96b8-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e96b8-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e96b8-116">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="e96b8-116">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e96b8-117">按兩下清單中的 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="e96b8-117">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="e96b8-118">在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e96b8-118">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="e96b8-119">按一下 **[永遠略過]**。</span><span class="sxs-lookup"><span data-stu-id="e96b8-119">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="e96b8-120">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e96b8-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e96b8-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e96b8-121">See Also</span></span>


[<span data-ttu-id="e96b8-122">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e96b8-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="e96b8-123">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="e96b8-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="e96b8-124">Lync Server 2013 中的媒體旁路和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="e96b8-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="e96b8-125">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e96b8-125">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

