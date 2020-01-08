---
title: 確認外部使用者的同盟及遠端存取
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33eb8fddaef96da047a6e87f1961b2fbea73c29d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="ade70-102">確認外部使用者的同盟及遠端存取</span><span class="sxs-lookup"><span data-stu-id="ade70-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ade70-103">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="ade70-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="ade70-104">將同盟路由轉換為 Lync Server 2013 Edge 伺服器之後，您應該執行一些功能測試，以驗證同盟是否如預期方式執行。</span><span class="sxs-lookup"><span data-stu-id="ade70-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="ade70-105">外部使用者存取的測試應該包括貴組織支援的每一種外部使用者類型，包括下列任一或所有類型的使用者。</span><span class="sxs-lookup"><span data-stu-id="ade70-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="ade70-106">測試外部使用者與外部存取的連通性</span><span class="sxs-lookup"><span data-stu-id="ade70-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="ade70-107">至少有一個聯盟網域的使用者，也就是 Lync Server 2013 上的內部使用者，以及 Lync Server 2010 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="ade70-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="ade70-108">測試立即訊息（IM）、目前狀態、音訊/視頻（A/V）與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="ade70-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="ade70-109">貴組織支援的每個公用 IM 服務提供者的使用者（以及已完成哪些預配）與 Lync Server 2013 上的使用者以及 Lync Server 2010 上的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ade70-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="ade70-110">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="ade70-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="ade70-111">在 lync Server 2010 上使用遠端使用者存取（從內部網路外部2010（不含 VPN），使用 Lync server 2013 上的使用者以及 Lync Server 2010 上的使用者來託管的使用者。</span><span class="sxs-lookup"><span data-stu-id="ade70-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="ade70-112">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="ade70-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="ade70-113">在 lync Server 2013 上使用遠端使用者存取（從內部網路外部2013（不含 VPN），使用 Lync server 2013 上的使用者以及 Lync Server 2010 上的使用者來託管的使用者。</span><span class="sxs-lookup"><span data-stu-id="ade70-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="ade70-114">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="ade70-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

