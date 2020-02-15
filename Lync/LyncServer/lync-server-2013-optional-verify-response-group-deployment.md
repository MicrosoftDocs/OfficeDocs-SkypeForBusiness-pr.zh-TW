---
title: 'Lync Server 2013: （選用） 確認回應群組部署'
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
ms.openlocfilehash: b5b99d5d2f1800a4d7d16b1d3fdf4d0aab213fd0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="1831e-102">（選用）Lync Server 2013 中驗證回應群組部署</span><span class="sxs-lookup"><span data-stu-id="1831e-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1831e-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="1831e-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1831e-104">設定回應群組之後，您必須確認組態，確定您的回應群組如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="1831e-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="1831e-105">在最低限度下，使用下列類型的使用者驗證下列案例：</span><span class="sxs-lookup"><span data-stu-id="1831e-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="1831e-106">**Users**</span><span class="sxs-lookup"><span data-stu-id="1831e-106">**Users**</span></span>

  - <span data-ttu-id="1831e-107">使用者隸屬於 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1831e-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="1831e-108">使用公用交換的電話網路 (PSTN) 外部使用者</span><span class="sxs-lookup"><span data-stu-id="1831e-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="1831e-109">在 Lync Server 2013 位於代理程式</span><span class="sxs-lookup"><span data-stu-id="1831e-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="1831e-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="1831e-110">**Scenarios**</span></span>

  - <span data-ttu-id="1831e-111">Lync Server 2013 使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="1831e-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="1831e-112">外部使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="1831e-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="1831e-113">當專員在接聽另一通電話而排入佇列時，使用者呼叫回應群組。</span><span class="sxs-lookup"><span data-stu-id="1831e-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

