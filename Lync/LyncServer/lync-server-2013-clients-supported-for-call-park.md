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
ms.openlocfilehash: 74e9231c99754f0916d1ddf94ba36d1dce81fb1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499260"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="77bc1-102">Lync Server 2013 中支援通話駐留的用戶端</span><span class="sxs-lookup"><span data-stu-id="77bc1-102">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77bc1-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="77bc1-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="77bc1-104">本節識別可用於寄存通話的用戶端，以及可用於檢索寄存通話的用戶端。</span><span class="sxs-lookup"><span data-stu-id="77bc1-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="77bc1-105">支援駐留通話的用戶端</span><span class="sxs-lookup"><span data-stu-id="77bc1-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="77bc1-106">來自任何 IP、專用交換機 (PBX) 、公用交換電話網路 (PSTN) 或行動電話可以寄存的電話。</span><span class="sxs-lookup"><span data-stu-id="77bc1-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77bc1-107">只有音訊通話可以寄存。</span><span class="sxs-lookup"><span data-stu-id="77bc1-107">Only audio calls can be parked.</span></span> <span data-ttu-id="77bc1-108">立即訊息和會議無法停用。</span><span class="sxs-lookup"><span data-stu-id="77bc1-108">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="77bc1-109">下列用戶端可以將通話駐留用於駐留通話：</span><span class="sxs-lookup"><span data-stu-id="77bc1-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="77bc1-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="77bc1-110">Lync 2013</span></span>

  - <span data-ttu-id="77bc1-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="77bc1-111">Lync 2010</span></span>

  - <span data-ttu-id="77bc1-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="77bc1-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="77bc1-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="77bc1-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77bc1-114">行動電話無法將通話駐留用於寄存通話。</span><span class="sxs-lookup"><span data-stu-id="77bc1-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="77bc1-115">支援檢索呼叫的用戶端</span><span class="sxs-lookup"><span data-stu-id="77bc1-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="77bc1-116">軌道範圍會設定為不需要指派使用者或電話) 的虛擬分機區塊 (擴充。</span><span class="sxs-lookup"><span data-stu-id="77bc1-116">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="77bc1-117">當您將軌道式設定為虛擬分機時，行動電話和 PSTN 電話便無法檢索寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="77bc1-117">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="77bc1-118">同盟使用者無法檢索寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="77bc1-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="77bc1-119">下列用戶端可以檢索寄存在通話駐留上的通話：</span><span class="sxs-lookup"><span data-stu-id="77bc1-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="77bc1-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="77bc1-120">Lync 2013</span></span>

  - <span data-ttu-id="77bc1-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="77bc1-121">Lync 2010</span></span>

  - <span data-ttu-id="77bc1-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="77bc1-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="77bc1-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="77bc1-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="77bc1-124">IP 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="77bc1-124">IP common area phones</span></span>

  - <span data-ttu-id="77bc1-125">連線至 Lync Server 2013 基礎結構的非 IP 電話，包括通用區域電話和專用交換機 (PBX) 電話</span><span class="sxs-lookup"><span data-stu-id="77bc1-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

