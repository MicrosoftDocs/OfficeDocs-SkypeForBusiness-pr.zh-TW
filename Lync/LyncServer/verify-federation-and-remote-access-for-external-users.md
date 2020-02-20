---
title: 驗證同盟及外部使用者的遠端存取
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f45029b4818a555dd21f7bf5afef70cdca5b50e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="55446-102">驗證同盟及外部使用者的遠端存取</span><span class="sxs-lookup"><span data-stu-id="55446-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55446-103">_**主題上次修改日期：** 2012年-09-18_</span><span class="sxs-lookup"><span data-stu-id="55446-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="55446-104">轉換至 Lync Server 2013 Edge Server 同盟路由之後，您應該執行一些功能測試以確認同盟如預期般。</span><span class="sxs-lookup"><span data-stu-id="55446-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="55446-105">外部使用者存取的測試應該包含組織支援的每種外部使用者類型，包括下列任一項或所有項目。</span><span class="sxs-lookup"><span data-stu-id="55446-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="55446-106">測試外部使用者與外部存取連線能力</span><span class="sxs-lookup"><span data-stu-id="55446-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="55446-107">來自至少一個同盟的網域、 內部使用者在 Lync Server 2013 和 Lync Server 2010 上的使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="55446-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="55446-108">測試立即訊息 (IM)、目前狀態、音訊/視訊 (A/V) 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="55446-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="55446-109">每個公用 IM 服務提供者的組織支援 （且其佈建完成） 的使用者與使用者在 Lync Server 2013 及 Lync Server 2010 上的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="55446-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="55446-110">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="55446-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="55446-111">Lync Server 2010 上的使用者及使用者的主控 Lync Server 2010 上使用 Lync Server 2013 上的使用者的遠端使用者存取 （登入 Lync Server 2010 從內部網路外，但沒有 VPN）。</span><span class="sxs-lookup"><span data-stu-id="55446-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="55446-112">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="55446-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="55446-113">Lync Server 2010 上的使用者及使用者的主控在 Lync Server 2013 與 Lync Server 2013 上的使用者使用遠端使用者存取 （登入 Lync Server 2013，從內部網路外，但沒有 VPN）。</span><span class="sxs-lookup"><span data-stu-id="55446-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="55446-114">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="55446-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

