---
title: Lync Server 2013：驗證語音號碼正常化和路由
description: Lync Server 2013：驗證語音號碼正常化和路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547139"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="0db4d-103">在 Lync Server 2013 中驗證語音號碼正常化和路由</span><span class="sxs-lookup"><span data-stu-id="0db4d-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0db4d-104">_**主題上次修改日期：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="0db4d-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="0db4d-105">正確的數位正規化和路由對功能性 Enterprise Voice 環境而言非常重要。</span><span class="sxs-lookup"><span data-stu-id="0db4d-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="0db4d-106">尤其是在從專用交換機遷移 (PBX) 到獨立的 Lync Server 環境時，成功遷移的其中一個按鍵是顯示並記錄所有現有的撥號規則，並建立適當的正規化規則、語音原則、電話使用方式和路由。</span><span class="sxs-lookup"><span data-stu-id="0db4d-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="0db4d-107">驗證編號正規化和路由是很重要的，不僅在遷移期間，也不是系統的一般穩定作業。</span><span class="sxs-lookup"><span data-stu-id="0db4d-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="0db4d-108">我們建議您每日使用 Lync Server 控制台，以針對在 Lync Server 全域設定中所發佈的目前正規化規則集開發一組強大的測試案例開始，進行此驗證。</span><span class="sxs-lookup"><span data-stu-id="0db4d-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="0db4d-109">應該每日執行這些測試案例，以反白顯示對撥號對應表進行的任何不需要的變更。</span><span class="sxs-lookup"><span data-stu-id="0db4d-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="0db4d-110">Lync Server 控制台也可協助您視覺化、測試、變更、封存和共用語音路由的設定資訊，以及變更企業語音號碼正規化規則、撥號對應表、語音原則和路由。</span><span class="sxs-lookup"><span data-stu-id="0db4d-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="0db4d-111">其還有其他功能可供您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="0db4d-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="0db4d-112">在系統之間匯出及匯入或備份語音路由資料。</span><span class="sxs-lookup"><span data-stu-id="0db4d-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="0db4d-113">先測試設定變更，再將其上傳至實際系統。</span><span class="sxs-lookup"><span data-stu-id="0db4d-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="0db4d-114">建立及執行設定測試案例，以協助確保在您對已部署的系統進行變更之後，路由資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="0db4d-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="0db4d-115">建立及變更編號正規化規則、位置設定檔、語音原則及路由資料，而不需撰寫必要的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="0db4d-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="0db4d-116">分析位置設定檔與 Lync Server Phone Edition 的相容性。</span><span class="sxs-lookup"><span data-stu-id="0db4d-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="0db4d-117">[在 Lync Server 2013 的測試語音路由中](lync-server-2013-test-voice-routing.md)，可以找到有關語音路由測試的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0db4d-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0db4d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0db4d-118">See Also</span></span>


[<span data-ttu-id="0db4d-119">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="0db4d-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

