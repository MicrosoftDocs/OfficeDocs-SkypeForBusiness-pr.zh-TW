---
title: Lync Server 2013：支援通話駐留的用戶端
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
ms.openlocfilehash: 52304a0241425a3b88c7f9419afa57f3d768fbb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f7cbc-102">Lync Server 2013 中支援通話駐留的用戶端</span><span class="sxs-lookup"><span data-stu-id="f7cbc-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7cbc-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f7cbc-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f7cbc-104">本節會識別可以用來寄存通話的用戶端，以及可用於檢索暫停通話的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="f7cbc-105">支援停用通話的用戶端</span><span class="sxs-lookup"><span data-stu-id="f7cbc-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="f7cbc-106">來自任何 IP、私人分支 exchange （PBX）、公用交換電話網絡（PSTN）或行動電話的呼叫都可以停用。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cbc-107">只有音訊通話可以停用。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-107">Only audio calls can be parked.</span></span> <span data-ttu-id="f7cbc-108">無法停用立即訊息和會議。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-108">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="f7cbc-109">下列用戶端可以使用通話駐留撥出電話：</span><span class="sxs-lookup"><span data-stu-id="f7cbc-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="f7cbc-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f7cbc-110">Lync 2013</span></span>

  - <span data-ttu-id="f7cbc-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f7cbc-111">Lync 2010</span></span>

  - <span data-ttu-id="f7cbc-112">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="f7cbc-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="f7cbc-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f7cbc-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cbc-114">行動電話無法使用通話駐留撥出電話。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="f7cbc-115">支援的用戶端檢索通話</span><span class="sxs-lookup"><span data-stu-id="f7cbc-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="f7cbc-116">軌道範圍是設定為虛擬延伸的區塊（不含指派使用者或電話的延伸）。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-116">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="f7cbc-117">當您將 [軌道式] 設定為 [虛擬延伸] 時，行動電話和 PSTN 手機無法取得停用的通話。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-117">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="f7cbc-118">同盟使用者無法取得停用的通話。</span><span class="sxs-lookup"><span data-stu-id="f7cbc-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="f7cbc-119">下列用戶端可以檢索寄存在通話寄存上的通話：</span><span class="sxs-lookup"><span data-stu-id="f7cbc-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="f7cbc-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f7cbc-120">Lync 2013</span></span>

  - <span data-ttu-id="f7cbc-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f7cbc-121">Lync 2010</span></span>

  - <span data-ttu-id="f7cbc-122">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="f7cbc-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="f7cbc-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f7cbc-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="f7cbc-124">IP 通用區域電話</span><span class="sxs-lookup"><span data-stu-id="f7cbc-124">IP common area phones</span></span>

  - <span data-ttu-id="f7cbc-125">連線至 Lync Server 2013 基礎結構的非 IP 電話，包括通用的區域電話和私人分支 exchange （PBX）電話</span><span class="sxs-lookup"><span data-stu-id="f7cbc-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

