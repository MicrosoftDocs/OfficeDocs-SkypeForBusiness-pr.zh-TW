---
title: Lync Server 2013： 確認外部使用者的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14d3dbc74119ff4f5669776dafce8a7cc2dee21a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="70ab7-102">確認 Lync Server 2013 中的外部使用者的連線</span><span class="sxs-lookup"><span data-stu-id="70ab7-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ab7-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="70ab7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="70ab7-104">要驗證外部使用者連線能力，必須先確保從使用者至伺服器，以及 Access Edge Service 連接埠的連線能力。</span><span class="sxs-lookup"><span data-stu-id="70ab7-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="70ab7-105">重要資源的外部使用者存取的案例中確認您的設定，以及連線、 傳送及接收正確的郵件需要是 Remote Connectivity Analyzer 網站 (<http://www.testocsconnectivity.com>)。</span><span class="sxs-lookup"><span data-stu-id="70ab7-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="70ab7-106">網站是由管理和維護 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="70ab7-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="70ab7-107">如要瀏覽遠端連線分析程式，請在瀏覽器中開啟該網站，然後遵循指示來選取案例。</span><span class="sxs-lookup"><span data-stu-id="70ab7-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="70ab7-108">測試外部使用者與外部存取連線能力</span><span class="sxs-lookup"><span data-stu-id="70ab7-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="70ab7-109">測試外部使用者存取時，必須包括組織支援的每一種外部使用者類型，包含下列任一或全部項目：</span><span class="sxs-lookup"><span data-stu-id="70ab7-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="70ab7-110">來自至少一個同盟網路、測試 IM、目前狀態、A/V 與桌面共用的使用者。</span><span class="sxs-lookup"><span data-stu-id="70ab7-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="70ab7-111">組織所支援的每個公用 IM 服務提供者 (以及已經完成佈建作業) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="70ab7-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="70ab7-112">匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="70ab7-112">Anonymous users.</span></span>

  - <span data-ttu-id="70ab7-113">從遠端登入 Lync (但不是透過 VPN) 的組織內使用者。</span><span class="sxs-lookup"><span data-stu-id="70ab7-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="70ab7-114">這些測試決定了您的 Edge Server 是否：</span><span class="sxs-lookup"><span data-stu-id="70ab7-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="70ab7-115">使用網路外部的 telnet 用戶端聆聽必要的連接埠。</span><span class="sxs-lookup"><span data-stu-id="70ab7-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="70ab7-116">範例：telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="70ab7-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="70ab7-117">依據您的部署，透過 Edge Server 或 Edge Server 集區對您使用的連接埠執行先前測試。</span><span class="sxs-lookup"><span data-stu-id="70ab7-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="70ab7-118">執行準確的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="70ab7-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="70ab7-p102">從網路外部偵測 (ping) Edge 或 Edge 集區的個別外部 FQDN。即使偵測 (ping) 作業失敗，您還是會看到 IP 位址，方便您與指派的 IP 位址進行比較。</span><span class="sxs-lookup"><span data-stu-id="70ab7-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

