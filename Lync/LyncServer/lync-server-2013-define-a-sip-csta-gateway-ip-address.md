---
title: Lync Server 2013：定義 SIP/CSTA 閘道 IP 位址
description: Lync Server 2013：定義 SIP/CSTA 閘道 IP 位址。
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
ms.openlocfilehash: 23286b2748df3af06f905a791bf0ee80c6f0a919
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560429"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="bb1eb-103">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="bb1eb-103">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb1eb-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="bb1eb-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="bb1eb-105">若 Lync Server 會使用傳輸控制通訊協定 (TCP) 連線，連接至您為遠端呼叫控制部署的 SIP/CSTA 閘道，則您必須在拓撲產生器中定義閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-105">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="bb1eb-106">在支援傳輸層安全性 (TLS) 連線的閘道時，不需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-106">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="bb1eb-107">對於任何支援 TLS 連線的閘道，您可以跳過此程式，並遵循在 [Lync Server 2013 中啟用 [遠端呼叫] 控制中的 [啟用 lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)] 中的步驟，繼續部署遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-107">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="bb1eb-108">使用拓撲產生器定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="bb1eb-108">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="bb1eb-109">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="bb1eb-110">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="bb1eb-111">選擇下載現有拓撲的選項。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-111">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="bb1eb-112">展開 **[信任的應用程式伺服器]** 節點。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-112">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="bb1eb-113">以滑鼠右鍵按一下您所建立的信任應用程式集區（如在 [Lync Server 2013 中設定遠端呼叫控制的信任應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)中所述），然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-113">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="bb1eb-114">清除 [ **啟用設定資料到此集區的** 複寫] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-114">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="bb1eb-115">按一下 [ **將服務使用方式限制為選取的 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-115">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="bb1eb-116">預設設定是 **使用所有設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-116">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="bb1eb-117">在 [ **主要 IP 位址** ] 文字方塊中，輸入 SIP/CSTA 閘道的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-117">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="bb1eb-118">若要更新中央管理存放區中的拓撲，請按一下主控台樹中的 [ **Lync Server**]，然後從 [ **動作** ] 窗格中，按一下 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="bb1eb-118">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb1eb-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb1eb-119">See Also</span></span>


[<span data-ttu-id="bb1eb-120">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="bb1eb-120">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="bb1eb-121">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="bb1eb-121">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

