---
title: 通話駐留的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="2b7f7-102">Lync Server 2013 中的通話駐留概觀</span><span class="sxs-lookup"><span data-stu-id="2b7f7-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b7f7-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="2b7f7-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="2b7f7-104">Lync Server 2013 通話駐留應用程式可讓 Enterprise Voice 使用者執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="2b7f7-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="2b7f7-105">將呼叫放入保留，然後從相同電話或其他電話擷取通話。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="2b7f7-106">將呼叫放入保留，並將它轉接至某個部門或一般區域 (例如，能夠銷售部門或是倉儲是公共區域電話)。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="2b7f7-107">放入保留的通話，並保留原始的自動答錄服務電話空出來處理通話。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="2b7f7-108">當使用者公園通話，Lync Server 將傳輸的暫存的數字，稱為*軌道*，通話保留並在擷取或逾時之前呼叫。Lync Server 會將軌道傳送給駐留通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="2b7f7-109">若要擷取駐留的通話，使用者可以撥打軌道號碼，或按一下軌道連結] 或 [交談] 視窗中的按鈕。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="2b7f7-110">駐留通話的使用者可以通知有人能夠軌道號碼給其他人使用外部的機制，例如立即訊息 (IM) 或分頁系統，來擷取通話。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="2b7f7-111">駐留通話的使用者可以將保留的交談視窗開啟擷取通話時收到通知。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="2b7f7-112">因為軌道範圍是全域唯一的就可以從任何 Lync Server 網站或 PBX 電話擷取通話，如果路由已適當設定。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="2b7f7-113">如果沒有人在可設定的時間內擷取通話，電話鈴響會回到駐留的人員。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="2b7f7-114">如果該人員未接聽回電時，來電會被轉接至後援目的地，例如運算子，如果有設定。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="2b7f7-115">您可以設定的前一到十個一定時間轉接電話鈴響備份的次數。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="2b7f7-116">如果沒有人接聽的轉接的來電，通話會中斷。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="2b7f7-117">擷取或中斷連線的來電時，會釋出軌道。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="2b7f7-118">當您部署通話駐留時，您需要為駐留通話保留範圍的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="2b7f7-119">這些副檔名必須是虛擬分機： 沒有任何使用者或電話指派給他們的分機。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2b7f7-120">您接著使用的分機號碼的範圍設定通話駐留軌道表，並指定哪些應用程式服務主控處理每個範圍的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="2b7f7-121">每個前端集區上對應後端伺服器用來管理通話駐留的集區具有通話駐留列表。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="2b7f7-122">軌道範圍的清單是否儲存在中央管理存放區，而且會用來將軌道路由傳送至目的地集區。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="2b7f7-123">通話駐留應用程式已在其中部署及設定每個 Lync 伺服器集區可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="2b7f7-124">在 Lync Server 部署，軌道範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="2b7f7-125">您也可以設定其他通話駐留設定，例如其中來電會被重新導向若使用者逾時間，以及是否在電話上的人所聽到駐留時的等候音樂。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="2b7f7-126">您也可以指定要播放在通話時的等候音樂檔保留。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b7f7-127">通話駐留的自訂等候音樂上保留檔案不會備份 Lync Server 2013 災害復原程序的一部分，而且如果損毀、 損毀，或清除上傳至集區的檔案將會遺失。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="2b7f7-128">永遠保持個別檔案的備份自訂等候音樂上保留已上傳的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="2b7f7-129">通話駐留應用程式是企業語音元件。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="2b7f7-130">當您部署企業語音時，將通話駐留應用程式已安裝，並自動啟動。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="2b7f7-131">您可以使用通話駐留之前，不過，Enterprise Voice 系統管理員必須將其設定並啟用的使用者透過語音原則。</span><span class="sxs-lookup"><span data-stu-id="2b7f7-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

