---
title: Lync Server 2013：規劃共用行外觀
description: Lync Server 2013：規劃共用行外觀。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c34a4792d6df9b37b138c08881699dfcdf684d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554379"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="b2e15-103">在 Lync Server 2013 中規劃共用行外觀</span><span class="sxs-lookup"><span data-stu-id="b2e15-103">Plan for Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2e15-104">_**主題上次修改日期：** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="b2e15-104">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="b2e15-105">閱讀此主題以瞭解如何在 Lync Server 2013 中規劃共用行外觀 (SLA) （累計更新四月2016）。</span><span class="sxs-lookup"><span data-stu-id="b2e15-105">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="b2e15-106">共用線外觀是 Lync Server 2013 中的一項功能，累積更新4月2016，用來處理特定號碼（稱為共用號碼）上的多個通話。</span><span class="sxs-lookup"><span data-stu-id="b2e15-106">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="b2e15-107">SLA 可將任何企業語音啟用的 Lync 使用者設定為具有多行的共用號碼，以回應多個通話。</span><span class="sxs-lookup"><span data-stu-id="b2e15-107">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="b2e15-108">呼叫並未實際接收共用號碼，而是轉寄給充當共用號碼代理人的使用者。</span><span class="sxs-lookup"><span data-stu-id="b2e15-108">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="b2e15-109">任何一位代理人都可以接聽來電，而其餘的代理人會在他們的電話上取得通知，告知已收取通話的人員，以及哪些線路已變得忙碌的結果。</span><span class="sxs-lookup"><span data-stu-id="b2e15-109">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="b2e15-110">您可以設定 SLA 中共用號碼的行數和代理人。</span><span class="sxs-lookup"><span data-stu-id="b2e15-110">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="b2e15-111">此外，高級選項（例如 BusyOption (所有線路忙碌) 和 MissedCallOption 時，會發生什麼情況）。 (所有代理人都不會拾取來電) 的情況，也可以設定共用號碼。</span><span class="sxs-lookup"><span data-stu-id="b2e15-111">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="b2e15-112">僅在下列電話裝置上支援 SLA，但電腦、行動電話或其他裝置上的 Lync 用戶端不支援 () ：</span><span class="sxs-lookup"><span data-stu-id="b2e15-112">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="b2e15-113">含固件更新5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="b2e15-113">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b2e15-114">含固件更新5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="b2e15-114">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b2e15-115">含固件更新5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="b2e15-115">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b2e15-116">含固件更新5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="b2e15-116">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="b2e15-117">SLA 是 Lync Server 2013 中的新功能，累積更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="b2e15-117">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="b2e15-118">如需部署 SLA 的相關資訊，請參閱 [在 Lync Server 2013 中部署共用線路外觀](lync-server-2013-deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="b2e15-118">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="b2e15-119">功能清單</span><span class="sxs-lookup"><span data-stu-id="b2e15-119">Feature List</span></span>

<span data-ttu-id="b2e15-120">設定 SLA 群組可啟用下列專案：</span><span class="sxs-lookup"><span data-stu-id="b2e15-120">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="b2e15-121">群組中的所有代理人都可以接聽撥入呼叫相同共用號碼。</span><span class="sxs-lookup"><span data-stu-id="b2e15-121">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="b2e15-122">通話可以是以 PSTN 為基礎或以 SIP 為基礎。</span><span class="sxs-lookup"><span data-stu-id="b2e15-122">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="b2e15-123">代理人可以保留及挑選通話。</span><span class="sxs-lookup"><span data-stu-id="b2e15-123">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="b2e15-124">代理人可將來電轉接至 SLA 群組以外的號碼。</span><span class="sxs-lookup"><span data-stu-id="b2e15-124">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="b2e15-125">代理人可以查看共用號碼目前有多少通話，並查看每個通話的狀態。</span><span class="sxs-lookup"><span data-stu-id="b2e15-125">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="b2e15-126">您可以設定共用號碼的並行通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="b2e15-126">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="b2e15-127">您也可以設定達到上限之後，要如何處理其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2e15-127">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="b2e15-128">過度通話可能會遭到忙碌，但會轉接至備用號碼，或轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b2e15-128">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="b2e15-129">您可以設定在特定時間) 進行處理時，要如何撥打未接來電 (通話的方式。</span><span class="sxs-lookup"><span data-stu-id="b2e15-129">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="b2e15-130">如果您為群組識別碼啟用語音信箱，未接來電會自動移至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b2e15-130">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="b2e15-131">如果您未啟用群組身分識別的「 (共用號碼」) 的語音信箱，您可以選擇將未接來電拒絕為繁忙的信號、轉寄至備用號碼，或中斷連線。</span><span class="sxs-lookup"><span data-stu-id="b2e15-131">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

