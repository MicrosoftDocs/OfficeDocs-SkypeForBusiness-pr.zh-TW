---
title: 支援的通話駐留的 Lync Server 2013： 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c59dde334b592b2dc78920a8c61e6322867475f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="423c0-102">通話駐留 Lync Server 2013 中支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="423c0-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="423c0-103">_**主題上次修改日期：** 2012年-09-13_</span><span class="sxs-lookup"><span data-stu-id="423c0-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="423c0-104">本節說明可用於駐留通話的用戶端和用戶端可以用來擷取駐留的通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="423c0-105">駐留通話支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="423c0-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="423c0-106">呼叫來自任何 IP、 專用交換機 (PBX)、 公用交換電話網路 (PSTN)，或可以駐留行動電話。</span><span class="sxs-lookup"><span data-stu-id="423c0-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="423c0-107">您可以駐留僅音訊通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-107">Only audio calls can be parked.</span></span> <span data-ttu-id="423c0-108">立即訊息和會議，無法駐留通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-108">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="423c0-109">下列用戶端可用於駐留通話的通話駐留：</span><span class="sxs-lookup"><span data-stu-id="423c0-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="423c0-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="423c0-110">Lync 2013</span></span>

  - <span data-ttu-id="423c0-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="423c0-111">Lync 2010</span></span>

  - <span data-ttu-id="423c0-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="423c0-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="423c0-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="423c0-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="423c0-114">行動電話無法使用通話駐留駐留通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="423c0-115">擷取通話支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="423c0-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="423c0-116">軌道範圍設定為虛擬分機 （而不需要指派的使用者或電話分機） 區塊。</span><span class="sxs-lookup"><span data-stu-id="423c0-116">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="423c0-117">當您為虛擬分機設定軌道時，行動電話和 PSTN 電話無法擷取駐留的通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-117">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="423c0-118">同盟的使用者無法擷取駐留的通話。</span><span class="sxs-lookup"><span data-stu-id="423c0-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="423c0-119">下列用戶端可以擷取駐留的通話駐留的通話：</span><span class="sxs-lookup"><span data-stu-id="423c0-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="423c0-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="423c0-120">Lync 2013</span></span>

  - <span data-ttu-id="423c0-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="423c0-121">Lync 2010</span></span>

  - <span data-ttu-id="423c0-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="423c0-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="423c0-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="423c0-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="423c0-124">IP 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="423c0-124">IP common area phones</span></span>

  - <span data-ttu-id="423c0-125">非 IP 電話連線至 Lync Server 2013 基礎結構，包括公共區域電話和專用交換機 (pbx) 電話</span><span class="sxs-lookup"><span data-stu-id="423c0-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

