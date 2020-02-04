---
title: 設定中繼伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="ddef5-102">設定中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="ddef5-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddef5-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ddef5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ddef5-104">此程式會詳細說明將 Lync Server 2013 池設定為使用 Lync Server 2013 轉送伺服器的步驟，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ddef5-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="ddef5-105">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="ddef5-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="ddef5-106">您也可以委派適當的管理員權力和許可權來新增伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="ddef5-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="ddef5-107">如需詳細資訊，請參閱標準版 server 或企業版 server 部署檔中的委派設定許可權。</span><span class="sxs-lookup"><span data-stu-id="ddef5-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="ddef5-108">針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="ddef5-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ddef5-109">如需有關如何尋找符合 Lync Server 2013 之合格 PSTN 閘道、IP Pbx 及 SIP 中繼服務的最新資訊，請參閱「Microsoft 統一通訊開啟交互操作<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>性程式」。</span><span class="sxs-lookup"><span data-stu-id="ddef5-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="ddef5-110">使用拓撲建立器設定中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="ddef5-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="ddef5-111">從拓撲建立器開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ddef5-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="ddef5-112">在左窗格中，流覽至**PSTN 閘道**。</span><span class="sxs-lookup"><span data-stu-id="ddef5-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="ddef5-113">以滑鼠右鍵按一下**PSTN 閘道**，然後按一下 [**新增 IP/PSTN 閘道**]。</span><span class="sxs-lookup"><span data-stu-id="ddef5-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="ddef5-114">完成 [**定義新的 IP/PSTN 閘道**] 頁面，並提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ddef5-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="ddef5-115">輸入閘道 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ddef5-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="ddef5-116">如果閘道使用 TLS 通訊協定，則需要閘道的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ddef5-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="ddef5-117">接受**IP/PSTN 閘道偵聽埠**的預設值，或輸入新的偵聽埠（如果已修改的話）。</span><span class="sxs-lookup"><span data-stu-id="ddef5-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="ddef5-118">設定**Sip 傳輸通訊協定**。</span><span class="sxs-lookup"><span data-stu-id="ddef5-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="ddef5-119">在左窗格中，流覽至 [**企業版頂層端] 池**或 [**標準版] 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="ddef5-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="ddef5-120">以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ddef5-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="ddef5-121">在 [**中繼伺服器**] 底下，設定**偵聽埠**。</span><span class="sxs-lookup"><span data-stu-id="ddef5-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="ddef5-122">接下來，選取新建立的 PSTN 閘道，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ddef5-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="ddef5-123">在 [**拓撲**建立器] 中，選取最上方的 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="ddef5-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="ddef5-124">從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ddef5-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="ddef5-125">**發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="ddef5-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ddef5-126">請務必完成下一個主題，<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">將語音路由改為使用新的 Lync server 2013 轉送伺服器</A>，以確保語音路由指向正確的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="ddef5-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

