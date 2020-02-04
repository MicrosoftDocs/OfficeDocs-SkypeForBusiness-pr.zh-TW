---
title: Lync Server 2013：通話許可控制的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="96d59-102">Lync Server 2013 中通話許可控制的最佳做法</span><span class="sxs-lookup"><span data-stu-id="96d59-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96d59-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="96d59-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="96d59-104">若要增強效能並簡化部署，請在部署 [通話許可控制] 時套用下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="96d59-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="96d59-105">確定 Wan 已充分為目前與預期媒體流量提供適當的配置。</span><span class="sxs-lookup"><span data-stu-id="96d59-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96d59-106">我們建議您將緩衝區中的頻寬限制為 [頻寬限制]。</span><span class="sxs-lookup"><span data-stu-id="96d59-106">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="96d59-107">在某些情況下，會影響頻寬限制所使用的總頻寬，並可能導致超出頻寬限制的情況。</span><span class="sxs-lookup"><span data-stu-id="96d59-107">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="96d59-108">例如，如果兩個來電嘗試在媒體流量接近頻寬限制時開始，可能是其中一個呼叫被拒絕，因為另一個管理的專案會先開始。</span><span class="sxs-lookup"><span data-stu-id="96d59-108">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="96d59-109">監控網路使用量和通話詳細資料記錄，讓您可以選擇最佳的 CAC 設定，並在網路使用量變更時更新 CAC 設定。</span><span class="sxs-lookup"><span data-stu-id="96d59-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="96d59-110">使用 CAC 頻寬原則來補充 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="96d59-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="96d59-111">如果您想要將封鎖的通話重新路由到 PSTN，請驗證 PSTN 功能和容量。</span><span class="sxs-lookup"><span data-stu-id="96d59-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="96d59-112">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃出站語音路由](lync-server-2013-planning-outbound-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="96d59-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96d59-113">[容量] 指的是您需要開啟以支援 PSTN 重新路由的埠數。</span><span class="sxs-lookup"><span data-stu-id="96d59-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

