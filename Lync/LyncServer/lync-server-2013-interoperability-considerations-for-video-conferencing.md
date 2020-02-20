---
title: Lync Server 2013： 的視訊會議的互通性考量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a061a87ee3c386160f9b94053d82d4ac05812f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="a115d-102">Lync Server 2013 中的視訊會議的互通性考量</span><span class="sxs-lookup"><span data-stu-id="a115d-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a115d-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="a115d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a115d-104">舊版用戶端和 Lync Server 2013 集區或 Lync Server 2013 用戶端與舊版集區之間的互通性時，本小節會說明在移轉共存階段期間的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="a115d-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="a115d-105">Lync Server 2013 集區</span><span class="sxs-lookup"><span data-stu-id="a115d-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="a115d-106">Lync Server 2013 集區中使用舊版用戶端時，使用者會遇到下列行為：</span><span class="sxs-lookup"><span data-stu-id="a115d-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="a115d-107">若為雙方通話，則視訊解析度和舊版集區中相同。</span><span class="sxs-lookup"><span data-stu-id="a115d-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="a115d-p101">若為多方會議，則視訊解析度及視訊會議功能和舊版集區中相同。不提供圖庫檢視及高解析度。</span><span class="sxs-lookup"><span data-stu-id="a115d-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="a115d-110">舊版集區</span><span class="sxs-lookup"><span data-stu-id="a115d-110">Legacy Pools</span></span>

<span data-ttu-id="a115d-111">當舊版集區中使用 Lync Server 2013 用戶端時，使用者會遇到下列行為：</span><span class="sxs-lookup"><span data-stu-id="a115d-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="a115d-112">若為雙方通話，Lync Server 2013 用戶端可用的新功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a115d-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="a115d-113">若雙方參與者皆使用 Lync Server 2013 用戶端使用 H.264。</span><span class="sxs-lookup"><span data-stu-id="a115d-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="a115d-114">因為舊版伺服器不會傳送此資訊與頻內佈建 Lync Server 2013 用戶端會使用 totalreceivevideobitratekb，預設值。</span><span class="sxs-lookup"><span data-stu-id="a115d-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="a115d-115">若為多方會議，則視訊解析度及視訊功能和舊版集區中舊版使用者所經歷的相同。</span><span class="sxs-lookup"><span data-stu-id="a115d-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a115d-116">當舊版伺服器主控的 Lync Server 2013 用戶端時，就可以設定視訊會議的頻寬，以便在集區上的所有使用者接收僅低解析度的視訊] 中，但傳送高解析度的視訊。</span><span class="sxs-lookup"><span data-stu-id="a115d-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="a115d-117">此情況的範例即是在媒體組態中將 MaxVideoRateAllowed 設為 CIF-250K，在會議原則中將 VideoBitRateKb 設為 2000 kbps。</span><span class="sxs-lookup"><span data-stu-id="a115d-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="a115d-118">此情況所產生的影響就是集區中的使用者無法收到高解析度。</span><span class="sxs-lookup"><span data-stu-id="a115d-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="a115d-119">MaxVideoRateAllowed 不再用於 Lync Server 2013 用戶端，因為它無法防止 Lync Server 2013 用戶端要求高解析度的視訊。</span><span class="sxs-lookup"><span data-stu-id="a115d-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="a115d-120">改成在會議原則中針對集區的所有使用者，將 VideoBitRateKb 設定為與 MaxVideoRateAllowed 相同的值 (亦即將 CIF 設為 250 kbps，或將 VGA 設為 600 kbps，或將 HD 設為 1500 kbps)。</span><span class="sxs-lookup"><span data-stu-id="a115d-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

