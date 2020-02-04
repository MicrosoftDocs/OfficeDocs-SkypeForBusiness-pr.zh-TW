---
title: Lync Server 2013：視訊會議的互通性考慮
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
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="85c60-102">Lync Server 2013 中的視訊會議的互通性考慮</span><span class="sxs-lookup"><span data-stu-id="85c60-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85c60-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="85c60-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="85c60-104">本節說明當舊版用戶端與 Lync server 2013 池或 Lync Server 2013 用戶端與舊版池之間的互通性時，在遷移共存階段中的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="85c60-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="85c60-105">Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="85c60-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="85c60-106">當舊版用戶端用於 Lync Server 2013 池中時，使用者會遇到下列行為：</span><span class="sxs-lookup"><span data-stu-id="85c60-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="85c60-107">對於雙方通話，影片解析度就與舊版池中的相同。</span><span class="sxs-lookup"><span data-stu-id="85c60-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="85c60-108">對於多方會議，影片解析度和視訊會議功能與舊版池中相同。</span><span class="sxs-lookup"><span data-stu-id="85c60-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="85c60-109">[庫視圖] 和 [高解析度] 無法使用。</span><span class="sxs-lookup"><span data-stu-id="85c60-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="85c60-110">舊版池</span><span class="sxs-lookup"><span data-stu-id="85c60-110">Legacy Pools</span></span>

<span data-ttu-id="85c60-111">在舊版池中使用 Lync Server 2013 用戶端時，使用者會遇到下列行為：</span><span class="sxs-lookup"><span data-stu-id="85c60-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="85c60-112">對於雙方通話，Lync Server 2013 用戶端可以使用下列新功能：</span><span class="sxs-lookup"><span data-stu-id="85c60-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="85c60-113">如果兩個參與者都使用 Lync Server 2013 用戶端，則可以使用 h-p。</span><span class="sxs-lookup"><span data-stu-id="85c60-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="85c60-114">Lync Server 2013 用戶端會使用 TotalReceiveVideoBitRateKb 的預設值，因為舊版伺服器不會以帶外的置備傳送此資訊。</span><span class="sxs-lookup"><span data-stu-id="85c60-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="85c60-115">對於多方會議，影片解析度和視訊會議功能與舊版池中的舊版用戶端所體驗。</span><span class="sxs-lookup"><span data-stu-id="85c60-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85c60-116">當舊版伺服器承載 Lync Server 2013 用戶端時，您可以設定視訊會議頻寬，讓該文件庫上的所有使用者只收到低解析度的影片，但傳送高解析度的影片。</span><span class="sxs-lookup"><span data-stu-id="85c60-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="85c60-117">例如，當您在媒體設定中將 MaxVideoRateAllowed 設定為 CIF-250K，且 VideoBitRateKb 在會議原則中設定為 2000 kbps 時會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="85c60-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="85c60-118">此情況的實際效果是，不可能針對該池使用者提供高解析度。</span><span class="sxs-lookup"><span data-stu-id="85c60-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="85c60-119">因為 MaxVideoRateAllowed 已不再用於 Lync Server 2013 用戶端，所以無法防止 Lync Server 2013 用戶端要求高解析度的影片。</span><span class="sxs-lookup"><span data-stu-id="85c60-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="85c60-120">相反地，請將所有使用者在會議原則中的 [VideoBitRateKb] 設定為與 MaxVideoRateAllowed 相同的值（即，CIF 設定為 250 kbps，或將 600 VGA 設定為 1500 kbps）。</span><span class="sxs-lookup"><span data-stu-id="85c60-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

