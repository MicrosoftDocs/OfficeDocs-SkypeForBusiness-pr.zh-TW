---
title: Lync Server 2013： 定義 SIP/CSTA 閘道 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59b2d236cc9a261f07b2f2e9dc26102efff908f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="dbbf8-102">Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dbbf8-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbbf8-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="dbbf8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dbbf8-104">如果您使用的傳輸控制通訊協定 (TCP) 連線部署遠端呼叫控制的 SIP/CSTA 閘道將連接 Lync 伺服器，您必須在拓撲產生器中定義閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="dbbf8-105">這是不必要步驟支援傳輸層安全性 (TLS) 連線的閘道。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="dbbf8-106">任何支援 TLS 連線的閘道，您可以略過此程序，然後繼續遠端呼叫控制的部署中[啟用 Lync 之使用者的 Lync Server 2013 中的遠端呼叫控制](lync-server-2013-enable-lync-users-for-remote-call-control.md)的步驟執行。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="dbbf8-107">若要使用拓撲產生器定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dbbf8-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="dbbf8-108">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dbbf8-109">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="dbbf8-110">選擇下載現有拓撲的選項。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="dbbf8-111">展開 **[信任的應用程式伺服器]** 節點。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="dbbf8-112">以滑鼠右鍵按一下您建立的信任的應用程式集區[設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)，所述，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="dbbf8-113">清除 [**啟用組態資料複寫到此集區**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="dbbf8-114">按一下 [**選取 IP 位址限制服務使用情況**]。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="dbbf8-115">預設值為**使用所有設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="dbbf8-116">在 [**主要 IP 位址**] 文字方塊中，輸入 SIP/CSTA 閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="dbbf8-117">若要更新的拓撲中的中央管理存放區，在主控台樹狀目錄中，[ **Lync Server**]，並再從 [**動作**] 窗格中，按一下 [**發佈**。</span><span class="sxs-lookup"><span data-stu-id="dbbf8-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dbbf8-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dbbf8-118">See Also</span></span>


[<span data-ttu-id="dbbf8-119">在 Lync Server 2013 中設定為遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="dbbf8-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="dbbf8-120">設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="dbbf8-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

