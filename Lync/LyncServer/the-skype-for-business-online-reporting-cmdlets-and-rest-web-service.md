---
title: 商務用 Skype Online 報告 Cmdlet 和 REST web 服務
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1e11b4c9d68dbc5e177d684cd3053a83df8ea
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "40977903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="288af-102">商務用 Skype Online 報告 Cmdlet 和 REST web 服務</span><span class="sxs-lookup"><span data-stu-id="288af-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="288af-103">_**主題上次修改日期：** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="288af-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="288af-104">與 [報告] 功能搭配使用時，商務用 Skype Online 提供五個 Windows PowerShell Cmdlet 的存取權，以協助產生這些報告，而且也可供系統管理員用來傳回自訂的報告資料。</span><span class="sxs-lookup"><span data-stu-id="288af-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="288af-105">商務用 Skype Online 也包含 REST （Representational 狀態傳輸），開發人員可使用這些功能來取得自訂的報告資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="288af-106">系統管理員可使用的報告 Cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="288af-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="288af-107">CsActiveUserReport，提供作用中使用者數的相關資訊（也就是已登入商務用 Skype Online 並參與至少一個會議或對等通訊會話的使用者）。</span><span class="sxs-lookup"><span data-stu-id="288af-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="288af-108">CsAVConferenceTimeReport，可提供使用者在音訊/視訊會議中花費的時間（分鐘）數的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="288af-109">CsConferenceReport，提供使用者參與之會議數量與類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="288af-110">CsP2PAVTimeReport，可提供使用者在點對點工作階段中所花費的時間（以分鐘為單位），其中包含音訊和/或影片的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="288af-111">CsP2PSessionReport，可提供使用者參與之點對點工作階段之數量與類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="288af-112">大多數系統管理員會使用 Microsoft 365 系統管理中心提供的報告：不只是那些自動產生的報表，但它們也提供資料的圖形化表示，這些資料通常容易解讀，而不是由所傳回的原始數值值報告 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="288af-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="288af-113">不過，熟悉 Windows PowerShell 的系統管理員可以使用報告 Cmdlet，傳回 Lync Online 報表中無法使用的資料。</span><span class="sxs-lookup"><span data-stu-id="288af-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="288af-114">例如，報告 Cmdlet 會傳回會話期間的相關資訊（每個會話持續的時間長度，以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="288af-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="288af-115">無法使用 Lync Online 報表來使用個別的會話期間。</span><span class="sxs-lookup"><span data-stu-id="288af-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="288af-116">同樣地，在 [每日] 視圖中，Lync Online 報告只會顯示前14天的資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="288af-117">如果您想要查看不同日的每日總計（例如，四個月前的日期），您可以使用報表 Cmdlet 來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="288af-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="288af-118">系統管理員可能也會對[使用 Excel 來取得 Office 365 報告資料](http://msdn.microsoft.com/en-us/library/dn781442.aspx)的文章感興趣，說明如何在 Microsoft Excel 中使用 OData 資料查詢功能來建立自訂的 Office 365 報表。</span><span class="sxs-lookup"><span data-stu-id="288af-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="288af-119">自訂報告可讓您指示從 Office 365 報表服務傳回哪些資料（以及多少資料）。</span><span class="sxs-lookup"><span data-stu-id="288af-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="288af-120">您也可以使用自訂報表來指定資料排序與分組的方式，以及提供不在系統管理中心顯示之資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="288af-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="288af-121">擁有開發背景的系統管理員可以使用 REST web 服務，來取得商務用 Skype Online 系統管理中心未顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="288af-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="288af-122">REST 服務與 SOAP 服務類似，因為每項技術都提供一種在用戶端與伺服器之間傳輸 XML 資料的方式。</span><span class="sxs-lookup"><span data-stu-id="288af-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="288af-123">不過，REST 服務至少有兩個與 SOAP 服務有關的優點。</span><span class="sxs-lookup"><span data-stu-id="288af-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="288af-124">若是一個，REST 會使用稱為 ATOM 供稿格式的標準化格式來執行 XML 資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="288af-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="288af-125">相比之下，在傳輸資料時，使用非標準格式的 SOAP。</span><span class="sxs-lookup"><span data-stu-id="288af-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="288af-126">此外，REST 可以在封鎖除 [取得] 和 [張貼] 以外的 HTTP 動詞的網路上傳輸資料。</span><span class="sxs-lookup"><span data-stu-id="288af-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="288af-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="288af-127">See Also</span></span>


<span data-ttu-id="288af-128">[Lync Online 報告](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="288af-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="288af-129">Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="288af-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="288af-130">瞭解 Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="288af-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="288af-131">[Exchange Online 報告 Cmdlet](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="288af-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="288af-132">使用 Excel 來取得 Office 365 報告資料</span><span class="sxs-lookup"><span data-stu-id="288af-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

