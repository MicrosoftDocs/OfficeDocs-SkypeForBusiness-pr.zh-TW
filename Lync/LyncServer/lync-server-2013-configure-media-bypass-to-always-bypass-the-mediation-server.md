---
title: Lync Server 2013：將 [旁路媒體] 設定為 [總是略過轉送伺服器]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="36be3-102">在 Lync Server 2013 中設定媒體旁路，以永遠略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="36be3-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36be3-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="36be3-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36be3-104">本主題假設您已針對特定的網路電話服務提供者（ITSP），為對等（公開交換電話網絡（PSTN）閘道、IP PBX 或會話邊界控制器（）上的任何干線連線設定媒體旁路您想要媒體略過中繼伺服器的網站或服務。</span><span class="sxs-lookup"><span data-stu-id="36be3-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="36be3-105">您不能將媒體設定為永遠略過中繼伺服器，同時也能啟用 [呼叫許可控制]。</span><span class="sxs-lookup"><span data-stu-id="36be3-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="36be3-106">這些設定不相容，因此在 Lync Server [控制台] 使用者介面中則是相互排斥的設定。</span><span class="sxs-lookup"><span data-stu-id="36be3-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="36be3-107">除了啟用與對轉送伺服器相關聯的個別幹線連線的媒體旁路，您也必須設定媒體旁路的全域設定。</span><span class="sxs-lookup"><span data-stu-id="36be3-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="36be3-108">如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在 Lync 端點與您在中繼連線中設定媒體旁路的任何對等都有良好的連線性。</span><span class="sxs-lookup"><span data-stu-id="36be3-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="36be3-109">如果您在 Lync 伺服器端點與所有對等的伺服器端點之間沒有良好的連線，則您必須設定全域媒體旁路設定，才能在下列情況下使用網站和區域資訊採用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="36be3-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="36be3-110">這可讓您在判斷媒體繞過中繼伺服器的時間進行更多控制。</span><span class="sxs-lookup"><span data-stu-id="36be3-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="36be3-111">若要這樣做，請使用 [在[Lync server 2013 中設定媒體旁路全域設定] 中的步驟，以使用網站和區域資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)，並[在 lync Server 2013 中將子網與網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="36be3-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="36be3-112">若要讓媒體不使用全域方式，就能一直略過中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="36be3-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="36be3-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="36be3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36be3-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="36be3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="36be3-115">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="36be3-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="36be3-116">按兩下清單中的**全域**配置。</span><span class="sxs-lookup"><span data-stu-id="36be3-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="36be3-117">在 [**編輯全域設定**] 頁面上，選取 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="36be3-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="36be3-118">按一下 [**永遠略過**]。</span><span class="sxs-lookup"><span data-stu-id="36be3-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="36be3-119">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="36be3-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36be3-120">請參閱</span><span class="sxs-lookup"><span data-stu-id="36be3-120">See Also</span></span>


[<span data-ttu-id="36be3-121">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="36be3-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="36be3-122">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="36be3-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="36be3-123">Lync Server 2013 中的媒體旁路和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="36be3-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="36be3-124">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="36be3-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

