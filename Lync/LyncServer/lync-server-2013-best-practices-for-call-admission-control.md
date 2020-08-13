---
title: Lync Server 2013：通話許可控制的最佳作法
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
ms.openlocfilehash: 1f9c7da9fd484ec0229417233de3f4338dd9f4b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="71701-102">Lync Server 2013 中通話許可控制的最佳作法</span><span class="sxs-lookup"><span data-stu-id="71701-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71701-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="71701-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="71701-104">若要增強效能及協助部署，請在部署通話許可控制時套用下列最佳作法：</span><span class="sxs-lookup"><span data-stu-id="71701-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="71701-105">確定已針對目前和預期的媒體流量充分佈建 Wan。</span><span class="sxs-lookup"><span data-stu-id="71701-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71701-106">建議您將緩衝區中的頻寬限制考慮在內。</span><span class="sxs-lookup"><span data-stu-id="71701-106">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="71701-107">有些案例會影響使用總頻寬的爭用狀況，而且可能會導致超出頻寬限制的情況。</span><span class="sxs-lookup"><span data-stu-id="71701-107">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="71701-108">例如，如果兩次來電嘗試在媒體流量接近頻寬限制時啟動，其中一位可能會遭到拒絕，因為另一個管理的功能會先開始。</span><span class="sxs-lookup"><span data-stu-id="71701-108">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="71701-109">監視網路使用量和詳細通話記錄，以便您可以選擇最優 CAC 設定，並在網路使用量變更時更新 CAC 設定。</span><span class="sxs-lookup"><span data-stu-id="71701-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="71701-110">使用 CAC 頻寬原則來補充 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="71701-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="71701-111">如果您想要將封鎖的來電重新路由至 PSTN，請驗證 PSTN 功能和容量。</span><span class="sxs-lookup"><span data-stu-id="71701-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="71701-112">如需詳細資訊，請參閱[規劃 Lync Server 2013 中的外寄語音路由](lync-server-2013-planning-outbound-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="71701-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71701-113">「容量」指的是您需要開啟以支援潛在 PSTN 重新路由的埠數目。</span><span class="sxs-lookup"><span data-stu-id="71701-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

