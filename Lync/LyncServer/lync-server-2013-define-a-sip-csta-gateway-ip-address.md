---
title: Lync Server 2013：定義 SIP/CSTA 閘道 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="01ea2-102">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="01ea2-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01ea2-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="01ea2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="01ea2-104">如果 Lync Server 會使用傳輸控制通訊協定（TCP）連線，連線到您為遠端通話控制所部署的 SIP/CSTA 閘道，則您必須在拓撲建立器中定義閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="01ea2-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="01ea2-105">對於支援傳輸層安全性（TLS）連線的閘道，不需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="01ea2-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="01ea2-106">針對支援 TLS 連線的任何閘道，您可以跳過這個程式，然後按照在[Lync Server 2013 中啟用遠端通話控制的 lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)中的步驟，繼續部署遠端通話控制。</span><span class="sxs-lookup"><span data-stu-id="01ea2-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="01ea2-107">使用拓撲產生器定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="01ea2-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="01ea2-108">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="01ea2-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="01ea2-109">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="01ea2-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="01ea2-110">選擇下載現有拓撲的選項。</span><span class="sxs-lookup"><span data-stu-id="01ea2-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="01ea2-111">展開 [**受信任的應用程式伺服器**] 節點。</span><span class="sxs-lookup"><span data-stu-id="01ea2-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="01ea2-112">以滑鼠右鍵按一下您所建立的受信任的應用程式池，如在[Lync Server 2013 的 [設定遠端通話控制的信任的應用程式專案] 中](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)所述，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="01ea2-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="01ea2-113">清除 [**啟用將配置資料複製到這個資源**區] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="01ea2-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="01ea2-114">按一下 [**將服務使用限制為選取的 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="01ea2-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="01ea2-115">預設設定是**使用所有已設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="01ea2-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="01ea2-116">在 [**主要 IP 位址**] 文字方塊中，輸入 SIP/CSTA 閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="01ea2-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="01ea2-117">若要更新中央管理存放區中的拓撲，請按一下主控台樹中的 [ **Lync Server**]，然後從 [**動作**] 窗格中按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="01ea2-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01ea2-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="01ea2-118">See Also</span></span>


[<span data-ttu-id="01ea2-119">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="01ea2-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="01ea2-120">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="01ea2-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

