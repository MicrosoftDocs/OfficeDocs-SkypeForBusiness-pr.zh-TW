---
title: Lync Server 2013： (選用) 驗證回應群組部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b28fa4a83e89e446c5f4739d95fedea88769bc3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530740"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="ea200-102">在 Lync Server 2013 中 (選用) 驗證回應群組部署</span><span class="sxs-lookup"><span data-stu-id="ea200-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea200-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ea200-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ea200-104">在您設定回應群組之後，您必須驗證設定，以確保回應群組如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="ea200-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="ea200-105">至少要使用下列類型的使用者驗證下列案例：</span><span class="sxs-lookup"><span data-stu-id="ea200-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="ea200-106">**Users**</span><span class="sxs-lookup"><span data-stu-id="ea200-106">**Users**</span></span>

  - <span data-ttu-id="ea200-107">位於 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="ea200-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="ea200-108">使用公用交換電話網路的外部使用者 (PSTN) </span><span class="sxs-lookup"><span data-stu-id="ea200-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="ea200-109">位於 Lync Server 2013 的代理人</span><span class="sxs-lookup"><span data-stu-id="ea200-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="ea200-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="ea200-110">**Scenarios**</span></span>

  - <span data-ttu-id="ea200-111">Lync Server 2013 使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="ea200-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="ea200-112">外部使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="ea200-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="ea200-113">當專員在接聽另一通電話而排入佇列時，使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="ea200-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

