---
title: 設定轉送伺服器
description: 設定轉送伺服器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5723d9446122b85f7bd1812f7c6f411c5c1c9dbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542999"
---
# <a name="configure-mediation-server"></a><span data-ttu-id="3f892-103">設定轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="3f892-103">Configure Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f892-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f892-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f892-105">本程式詳細說明設定 Lync Server 2013 集區使用 Lync Server 2013 轉送伺服器的步驟，而非舊版 Office 通訊伺服器的 2007 R2 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f892-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="3f892-p101">若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。您也可以委派適當的系統管理員權限與授權來新增伺服器角色。如需詳細資訊，請參閱 Standard Edition Server 或 Enterprise Edition Server 之部署文件中的委派設定權限。若要變更其他設定，只需具備 RTCUniversalServerAdmins 群組的成員資格即可。</span><span class="sxs-lookup"><span data-stu-id="3f892-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f892-110">如需尋找合格的 PSTN 閘道、IP PBXs 和 SIP 主幹服務（搭配 Lync Server 2013）的最新資訊，請參閱《 Microsoft 整合通訊開啟互通性程式》，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> 。</span><span class="sxs-lookup"><span data-stu-id="3f892-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="3f892-111">使用拓撲產生器設定中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3f892-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="3f892-112">從拓撲產生器開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="3f892-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="3f892-113">在左窗格中，瀏覽至 **[PSTN 閘道]**。</span><span class="sxs-lookup"><span data-stu-id="3f892-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="3f892-114">以滑鼠右鍵按一下 [PSTN 閘道]\*\*\*\*，然後按一下 [新增 IP/PSTN 閘道]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f892-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="3f892-115">在 **[定義新的 IP/PSTN 閘道]** 頁面中填入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="3f892-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="3f892-p102">輸入閘道 FQDN 或 IP 位址。如果閘道使用 TLS 通訊協定，就需要閘道的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3f892-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="3f892-118">接受 **[IP/PSTN 閘道的聆聽連接埠]** 的預設值；其如有修改，請輸入新的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="3f892-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="3f892-119">設定 [Sip 傳輸通訊協定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f892-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="3f892-120">在左窗格中，瀏覽至 [Enterprise Edition 前端集區]\*\*\*\* 或 [Standard Edition Server]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f892-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="3f892-121">以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f892-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="3f892-122">在 **[中繼伺服器]** 底下，設定 **[聆聽連接埠]**。</span><span class="sxs-lookup"><span data-stu-id="3f892-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="3f892-123">接著，選取新建的 PSTN 閘道並按一下 **[新增]**，建立關聯。</span><span class="sxs-lookup"><span data-stu-id="3f892-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="3f892-124">在 **[拓撲產生器]** 中選取最頂端的節點 **[Lync Server]**。</span><span class="sxs-lookup"><span data-stu-id="3f892-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="3f892-125">在 **[執行]** 功能表中，選取 **[發行拓撲]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3f892-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="3f892-126">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="3f892-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f892-127">請務必完成下一個主題： <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">變更語音路由以使用新的 Lync server 2013 轉送伺服器</A> ，以確保語音路由指向正確的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f892-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

