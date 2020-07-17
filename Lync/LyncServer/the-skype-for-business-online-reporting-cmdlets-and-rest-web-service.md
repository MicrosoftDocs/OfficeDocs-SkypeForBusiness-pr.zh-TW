---
title: 商務用 Skype Online 報告 Cmdlet 和 REST web 服務
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40d394ba69cf017c11d4eb6cd57246a9d425c0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="381bc-102">商務用 Skype Online 報告 Cmdlet 和 REST web 服務</span><span class="sxs-lookup"><span data-stu-id="381bc-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="381bc-103">_**主題上次修改日期：** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="381bc-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="381bc-104">與報表功能搭配使用，商務用 Skype Online 可讓您存取五個 Windows PowerShell Cmdlet，以協助產生這些報告，而且也可供系統管理員用來傳回自訂的報表資料。</span><span class="sxs-lookup"><span data-stu-id="381bc-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="381bc-105">商務用 Skype Online 也包含 REST （代表性 State 傳授），可供開發人員用來檢索自訂的報表資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="381bc-106">系統管理員可以使用的報告 Cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="381bc-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="381bc-107">Get-CsActiveUserReport，提供作用中使用者數目的相關資訊（也就是已登入商務用 Skype Online，並參與至少一部會議或對等通訊會話的使用者）。</span><span class="sxs-lookup"><span data-stu-id="381bc-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="381bc-108">Get-CsAVConferenceTimeReport，可提供使用者在音訊/視訊會議中所花費的時間（以分鐘為單位）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="381bc-109">Get-CsConferenceReport，提供使用者參與之會議的數量和類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="381bc-110">Get-CsP2PAVTimeReport，提供使用者在包含音訊和/或影片的點對點工作階段中所花費的時間長度（以分鐘為單位）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="381bc-111">Get-CsP2PSessionReport，提供使用者參與的點對點工作階段的數量和類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="381bc-112">大部分系統管理員會使用 Microsoft 365 系統管理中心提供的報告：這不僅是自動產生的報告，也提供了資料的圖形表示，但通常會比對報告指令程式所傳回的原始數位值更為容易轉譯。</span><span class="sxs-lookup"><span data-stu-id="381bc-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="381bc-113">不過，熟悉 Windows PowerShell 的系統管理員可以使用報告 Cmdlet，傳回 Lync Online 報告中無法輕易提供的資料。</span><span class="sxs-lookup"><span data-stu-id="381bc-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="381bc-114">例如，報告 Cmdlet 會傳回會話持續時間（每個會話持續時間（分鐘））的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="381bc-115">使用 Lync Online 報告無法使用個別的會話持續時間。</span><span class="sxs-lookup"><span data-stu-id="381bc-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="381bc-116">同樣地，在 [每日] 視圖中，Lync Online 報告只會顯示過去14天的資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="381bc-117">如果您想要查看不同一天的每日匯總（例如，從四個月之前的日期），您可以使用報告 Cmdlet 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="381bc-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="381bc-118">管理員可能也會有興趣[使用 Excel 來檢索 Office 365 報告資料](https://msdn.microsoft.com/library/dn781442.aspx)，這會說明如何使用 Microsoft Excel 中的 OData 資料查詢功能來建立自訂 Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="381bc-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="381bc-119">自訂報告讓您能夠聽寫從 Office 365 報表服務傳回的資料（和資料量）。</span><span class="sxs-lookup"><span data-stu-id="381bc-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="381bc-120">自訂報告也可讓您執行下列動作：指定資料的排序和群組方式，並提供系統管理員中心未顯示資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="381bc-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="381bc-121">具有開發背景的系統管理員可以使用 REST web 服務，以取得未顯示在商務用 Skype Online 系統管理中心中的資訊。</span><span class="sxs-lookup"><span data-stu-id="381bc-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="381bc-122">REST 服務與 SOAP 服務類似，每個技術都提供一種方法，可在用戶端與伺服器之間傳輸 XML 資料。</span><span class="sxs-lookup"><span data-stu-id="381bc-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="381bc-123">不過，REST 服務與 SOAP 服務具有至少兩個優點。</span><span class="sxs-lookup"><span data-stu-id="381bc-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="381bc-124">若為 one，REST 會使用稱為 ATOM 供稿格式的標準化格式來執行 XML 資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="381bc-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="381bc-125">相比之下，在傳輸資料時使用非標準格式的 SOAP。</span><span class="sxs-lookup"><span data-stu-id="381bc-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="381bc-126">此外，REST 可以跨封鎖接收和公告以外之 HTTP 動詞的網路傳輸資料。</span><span class="sxs-lookup"><span data-stu-id="381bc-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="381bc-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="381bc-127">See Also</span></span>


<span data-ttu-id="381bc-128">[Lync Online 報告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="381bc-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="381bc-129">Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="381bc-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="381bc-130">瞭解 Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="381bc-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="381bc-131">[Exchange Online 報告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="381bc-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="381bc-132">使用 Excel 擷取 Office 365 報表資料</span><span class="sxs-lookup"><span data-stu-id="381bc-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

