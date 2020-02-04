---
title: Lync Server 2013：驗證語音號碼標準化與路由
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
ms.openlocfilehash: 16739595878b0c67b37f988295a4b02877a3a6fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="f3869-102">驗證 Lync Server 2013 中的語音號碼標準化與路由</span><span class="sxs-lookup"><span data-stu-id="f3869-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3869-103">_**主題上次修改日期：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="f3869-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="f3869-104">正確的數位正常化與路由對於企業語音環境而言非常重要。</span><span class="sxs-lookup"><span data-stu-id="f3869-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="f3869-105">特別是在從專用分支 exchange （PBX）遷移到獨立的 Lync Server 環境時，成功遷移的其中一個金鑰就是顯示並記錄所有現有的撥號規則，並建立適當的正常化規則、語音原則[電話使用方式] 和 [路線]。</span><span class="sxs-lookup"><span data-stu-id="f3869-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="f3869-106">驗證編號正常化與路由不僅在遷移期間很重要，而且在系統的正常執行中也很重要。</span><span class="sxs-lookup"><span data-stu-id="f3869-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="f3869-107">我們建議您每天使用 Lync Server [控制台] 進行這項驗證，從針對 Lync Server 全域設定中發佈的目前正常化規則開發一組強健的測試案例開始。</span><span class="sxs-lookup"><span data-stu-id="f3869-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="f3869-108">這些測試案例應該每日執行，以醒目提示已作出並提交給撥號方案的任何不想要的變更。</span><span class="sxs-lookup"><span data-stu-id="f3869-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="f3869-109">Lync Server [控制台] 也可協助您視覺化、測試、變更、封存及共用有關語音路由與變更企業語音數位正常化規則、撥號方案、語音原則及路線的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="f3869-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="f3869-110">它還有其他功能可讓您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f3869-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="f3869-111">在系統之間匯出及匯入或備份語音路由資料。</span><span class="sxs-lookup"><span data-stu-id="f3869-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="f3869-112">在將配置變更上傳至實際系統之前先進行測試。</span><span class="sxs-lookup"><span data-stu-id="f3869-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="f3869-113">建立並執行配置測試案例，以協助確保在進行變更之後，路由資料的可用性，但在向已部署的系統提交變更之前。</span><span class="sxs-lookup"><span data-stu-id="f3869-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="f3869-114">建立及變更數位正常化規則、位置設定檔、語音原則及路由資料，而不需要撰寫必要的一般運算式。</span><span class="sxs-lookup"><span data-stu-id="f3869-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="f3869-115">分析位置設定檔與 Lync Server Phone Edition 的相容性。</span><span class="sxs-lookup"><span data-stu-id="f3869-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="f3869-116">您可以在[Lync Server 2013 的測試語音路由中](lync-server-2013-test-voice-routing.md)找到更多關於語音路由測試的資訊</span><span class="sxs-lookup"><span data-stu-id="f3869-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f3869-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="f3869-117">See Also</span></span>


[<span data-ttu-id="f3869-118">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="f3869-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

