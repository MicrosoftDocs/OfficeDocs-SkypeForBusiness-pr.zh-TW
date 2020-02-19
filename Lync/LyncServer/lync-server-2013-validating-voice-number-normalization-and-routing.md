---
title: Lync Server 2013： 驗證語音號碼正規化] 和 [路由
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
ms.openlocfilehash: f92809d018bf8b69e6bc3fd5cc640c40836249de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="8fe11-102">驗證語音號碼正規化和 Lync Server 2013 中的路由</span><span class="sxs-lookup"><span data-stu-id="8fe11-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fe11-103">_**上次修改主題：** 2014年-05-19_</span><span class="sxs-lookup"><span data-stu-id="8fe11-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="8fe11-104">正確的數字正規化] 和 [路由是非常重要功能的 Enterprise Voice 環境。</span><span class="sxs-lookup"><span data-stu-id="8fe11-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="8fe11-105">期間從專用交換機 (PBX) 至獨立 Lync Server 環境的移轉，尤其是一項成功移轉的機碼是顯示文件所有現有的撥號規則，並建立適當的正規化規則，語音原則，電話使用方式和路由。</span><span class="sxs-lookup"><span data-stu-id="8fe11-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="8fe11-106">驗證號碼正規化及路由重要不是只有在移轉期間，但也期間 normal，穩定的系統的作業。</span><span class="sxs-lookup"><span data-stu-id="8fe11-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="8fe11-107">我們建議使用 Lync Server Control Panel，啟動與開發功能強大的測試案例，對目前的 Lync Server 通用設定] 中已發佈的正規化規則集集每天執行此驗證。</span><span class="sxs-lookup"><span data-stu-id="8fe11-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="8fe11-108">這些測試案例應該執行每日] 可反白顯示任何不想要的變更進行並認可到撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8fe11-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="8fe11-109">Lync Server Control Panel 也可協助您視覺化、 測試、 變更、 封存和共用的組態資訊語音路由和變更 Enterprise Voice 號碼正規化規則、 撥號對應表、 語音原則和路由。</span><span class="sxs-lookup"><span data-stu-id="8fe11-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="8fe11-110">它具有額外的功能，為執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8fe11-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="8fe11-111">匯出及匯入或備份系統之間的語音路由的資料。</span><span class="sxs-lookup"><span data-stu-id="8fe11-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="8fe11-112">測試組態變更，再將它們上傳至 live 系統。</span><span class="sxs-lookup"><span data-stu-id="8fe11-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="8fe11-113">建立及部署的系統執行設定測試案例，以協助確保路由資料的可用性，變更之後，但它們認可之前所做的變更。</span><span class="sxs-lookup"><span data-stu-id="8fe11-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="8fe11-114">建立及變更數字正規化規則、 位置設定檔、 語音原則和路由資料，而不需要撰寫所需的規則運算式。</span><span class="sxs-lookup"><span data-stu-id="8fe11-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="8fe11-115">分析與 Lync Server Phone Edition 的相容性的位置設定檔。</span><span class="sxs-lookup"><span data-stu-id="8fe11-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="8fe11-116">可以在[測試語音路由 Lync Server 2013 中](lync-server-2013-test-voice-routing.md)找到的語音路由測試的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8fe11-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8fe11-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8fe11-117">See Also</span></span>


[<span data-ttu-id="8fe11-118">測試 Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="8fe11-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

