---
title: Lync Server 2013：規劃分支網站語音彈性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for branch-site voice resiliency
ms:assetid: 67713f57-3ded-4127-ac37-57d8099bf384
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398477(v=OCS.15)
ms:contentKeyID: 48184351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c29c6de0ef215ebf09a53b1811e4dde3acf1c48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-branch-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="c6a06-102">在 Lync Server 2013 中規劃分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="c6a06-102">Planning for branch-site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6a06-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c6a06-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c6a06-104">如果您想要提供分支網站復原功能（也就是高可用性企業語音服務），您有三個選項可以執行此動作：</span><span class="sxs-lookup"><span data-stu-id="c6a06-104">If you want to provide branch-site resiliency, that is, high-availability Enterprise Voice service, you have three options for doing so:</span></span>

  - <span data-ttu-id="c6a06-105">Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="c6a06-105">Survivable Branch Appliance</span></span>

  - <span data-ttu-id="c6a06-106">Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="c6a06-106">Survivable Branch Server</span></span>

  - <span data-ttu-id="c6a06-107">分支網站上的完整 Lync Server 部署</span><span class="sxs-lookup"><span data-stu-id="c6a06-107">A full Lync Server deployment at the branch site</span></span>

<span data-ttu-id="c6a06-108">本指南將協助您評估最適合貴組織的復原方案，以及根據您的復原方案（要使用哪一種 PSTN 連接解決方案）。</span><span class="sxs-lookup"><span data-stu-id="c6a06-108">This guide will help you evaluate which resiliency solution is best for your organization and, based on your resiliency solution, which PSTN-connectivity solution to use.</span></span> <span data-ttu-id="c6a06-109">它也會協助您準備部署您選擇的解決方案，方法是描述先決條件及其他規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="c6a06-109">It will also help you prepare to deploy the solution that you choose by describing prerequisites and other planning considerations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6a06-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="c6a06-110">In This Section</span></span>

  - [<span data-ttu-id="c6a06-111">Lync Server 2013 中的分支網站彈性功能</span><span class="sxs-lookup"><span data-stu-id="c6a06-111">Branch-site resiliency features in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-features.md)

  - [<span data-ttu-id="c6a06-112">Lync Server 2013 中的分支網站恢復解決方案</span><span class="sxs-lookup"><span data-stu-id="c6a06-112">Branch-site resiliency solutions in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-solutions.md)

  - [<span data-ttu-id="c6a06-113">Lync Server 2013 的分支網站復原需求</span><span class="sxs-lookup"><span data-stu-id="c6a06-113">Branch-site resiliency requirements for Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-requirements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

