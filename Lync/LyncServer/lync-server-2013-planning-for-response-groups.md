---
title: Lync Server 2013：規劃回應群組
description: Lync Server 2013：規劃回應群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response groups
ms:assetid: 7c10ce08-0068-4b22-8ecc-33e94811c900
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398617(v=OCS.15)
ms:contentKeyID: 48184608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3e5abbcf3620a628f2929059b03ffc3588f5349
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549249"
---
# <a name="planning-for-response-groups-in-lync-server-2013"></a><span data-ttu-id="34160-103">在 Lync Server 2013 中規劃回應群組</span><span class="sxs-lookup"><span data-stu-id="34160-103">Planning for response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34160-104">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="34160-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="34160-105">如果您的組織擁有接聽和管理特定通話類型的人員群組，例如，針對客戶服務、內部服務台或部門的一般電話支援，您可以部署 Lync Server 回應群組應用程式來管理這些呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="34160-105">If your organization has groups of people who answer and manage certain types of calls, such as for customer service, an internal help desk, or general telephone support for a department, you can deploy the Lync Server Response Group application to manage these types of calls.</span></span> <span data-ttu-id="34160-106">回應群組應用程式會將來電路由和佇列傳送給指定的人員（稱為代理人）。</span><span class="sxs-lookup"><span data-stu-id="34160-106">The Response Group application routes and queues incoming calls to designated persons, who are known as agents.</span></span> <span data-ttu-id="34160-107">藉由使用回應群組，您可以增加電話支援服務的使用頻率，並減少為執行這些服務所產生的負荷。</span><span class="sxs-lookup"><span data-stu-id="34160-107">You can increase the use of telephone support services and reduce the overhead of running these services by using response groups.</span></span> <span data-ttu-id="34160-108">本節說明回應群組的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="34160-108">This section describes planning considerations for Response Group.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34160-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="34160-109">In This Section</span></span>

  - [<span data-ttu-id="34160-110">Lync Server 2013 的回應群組應用程式概述</span><span class="sxs-lookup"><span data-stu-id="34160-110">Overview of the Response Group application in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-response-group-application.md)

  - [<span data-ttu-id="34160-111">Lync Server 2013 中回應群組使用的元件</span><span class="sxs-lookup"><span data-stu-id="34160-111">Components used by Response Group in Lync Server 2013</span></span>](lync-server-2013-components-used-by-response-group.md)

  - [<span data-ttu-id="34160-112">Lync Server 2013 中回應群組的技術需求</span><span class="sxs-lookup"><span data-stu-id="34160-112">Technical requirements for Response Group in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-response-group.md)

  - [<span data-ttu-id="34160-113">Lync Server 2013 中支援回應群組的用戶端</span><span class="sxs-lookup"><span data-stu-id="34160-113">Clients supported for Response Group in Lync Server 2013</span></span>](lync-server-2013-clients-supported-for-response-group.md)

  - [<span data-ttu-id="34160-114">在 Lync Server 2013 中規劃回應群組的容量</span><span class="sxs-lookup"><span data-stu-id="34160-114">Capacity planning for Response Group in Lync Server 2013</span></span>](lync-server-2013-capacity-planning-for-response-group.md)

  - [<span data-ttu-id="34160-115">Lync Server 2013 中回應群組的部署程式</span><span class="sxs-lookup"><span data-stu-id="34160-115">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

