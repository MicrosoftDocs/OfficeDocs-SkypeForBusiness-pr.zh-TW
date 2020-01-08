---
title: Lync Server 2013：驗證外部使用者的連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="05c87-102">在 Lync Server 2013 中驗證外部使用者的連線能力</span><span class="sxs-lookup"><span data-stu-id="05c87-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05c87-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="05c87-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="05c87-104">驗證外部使用者的連線性需要確保使用者能連線到伺服器和埠，以存取邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="05c87-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="05c87-105">一種重要資源，可確認您的設定，以及能夠連線、傳送及接收外部使用者存取所需之案例的正確訊息，就是遠端連線分析<http://www.testocsconnectivity.com>程式網站（）。</span><span class="sxs-lookup"><span data-stu-id="05c87-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="05c87-106">網站由 Microsoft 支援服務管理和維護。</span><span class="sxs-lookup"><span data-stu-id="05c87-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="05c87-107">若要到達遠端連線分析程式，請在瀏覽器中開啟網站，然後依照指示來選取案例。</span><span class="sxs-lookup"><span data-stu-id="05c87-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="05c87-108">測試外部使用者與外部存取的連通性</span><span class="sxs-lookup"><span data-stu-id="05c87-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="05c87-109">外部使用者存取的測試應該包括貴組織支援的每一種外部使用者類型，包括下列任何一項或所有專案：</span><span class="sxs-lookup"><span data-stu-id="05c87-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="05c87-110">至少一個聯盟網域中的使用者，並測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="05c87-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="05c87-111">貴組織支援的每個公用 IM 服務提供者（以及已完成哪些預配）的使用者。</span><span class="sxs-lookup"><span data-stu-id="05c87-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="05c87-112">匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="05c87-112">Anonymous users.</span></span>

  - <span data-ttu-id="05c87-113">貴組織內已登入 Lync 但無法使用 VPN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="05c87-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="05c87-114">這些測試會判斷您的邊緣伺服器是否為：</span><span class="sxs-lookup"><span data-stu-id="05c87-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="05c87-115">從您的網路外部使用 telnet 用戶端來偵聽必要的埠。</span><span class="sxs-lookup"><span data-stu-id="05c87-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="05c87-116">範例： telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="05c87-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="05c87-117">根據您的部署，在 Edge 伺服器或 Edge 伺服器池中所使用的埠上執行上述測試。</span><span class="sxs-lookup"><span data-stu-id="05c87-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="05c87-118">執行正確的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="05c87-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="05c87-119">從您的網路外部 ping 您的邊緣或邊緣池的每個外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="05c87-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="05c87-120">即使 ping 失敗，您也會看到 IP 位址，您可以將它們與您指派的 IP 位址進行比較。</span><span class="sxs-lookup"><span data-stu-id="05c87-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

