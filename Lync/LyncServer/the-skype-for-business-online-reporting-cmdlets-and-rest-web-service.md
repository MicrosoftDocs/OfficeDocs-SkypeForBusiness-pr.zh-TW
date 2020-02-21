---
title: Skype 商務 Online 報告指令程式和 REST web 服務
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbce4dda006bb45606a09eef29d8c47946ad2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="0fa38-102">Skype 商務 Online 報告指令程式和 REST web 服務</span><span class="sxs-lookup"><span data-stu-id="0fa38-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fa38-103">_**上次修改主題：** 2014年-09-05_</span><span class="sxs-lookup"><span data-stu-id="0fa38-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="0fa38-104">搭配報告功能，商務用 Skype 會提供存取五個 Windows PowerShell cmdlet 幫助產生這些報告，而且也可用於系統管理員所傳回的自訂報告的資料。</span><span class="sxs-lookup"><span data-stu-id="0fa38-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="0fa38-105">Skype 商務 Online 也包含 REST (Representational State Transfer)，可以由開發人員用來擷取自訂報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="0fa38-106">系統管理員可報告指令程式包括：</span><span class="sxs-lookup"><span data-stu-id="0fa38-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="0fa38-107">Get-CsActiveUserReport，其提供作用中的使用者 （也就是使用者已登入 Skype for Business Online 並參與至少一個會議或對等通訊工作階段） 之數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="0fa38-108">在 [音訊/視訊會議所花費的 Get-csavconferencetimereport，其提供的時間 （以分鐘為單位） 的使用者數量的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="0fa38-109">Get-csconferencereport，提供資訊的數量和類型的會議使用者參與。</span><span class="sxs-lookup"><span data-stu-id="0fa38-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="0fa38-110">Get-csp2pavtimereport，可提供包含音訊和/或視訊的端對端工作階段中所花費的時間 （以分鐘為單位） 使用者的數量的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="0fa38-111">Get-csp2psessionreport，其提供的數量和類型的使用者參與的對等工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="0fa38-112">大部分的系統管理員會使用 Microsoft 365 系統管理中心中的可用的報告： 不只是這些報告自動產生，但它們也會提供更容易解譯比所傳回的原始號碼值的資料的圖形表示報告指令程式。</span><span class="sxs-lookup"><span data-stu-id="0fa38-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="0fa38-113">不過，系統管理員熟悉 Windows PowerShell cmdlet 可用於報告傳回未備妥從 Lync Online 報告的資料。</span><span class="sxs-lookup"><span data-stu-id="0fa38-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="0fa38-114">例如，報告指令程式傳回工作階段期間的相關資訊 （以分鐘為單位，每個工作階段持續的時間量）。</span><span class="sxs-lookup"><span data-stu-id="0fa38-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="0fa38-115">個別的工作階段期間不提供使用 Lync Online 的報告。</span><span class="sxs-lookup"><span data-stu-id="0fa38-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="0fa38-116">同樣地，在每日檢視 Lync Online 報告顯示先前的 14 天的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="0fa38-117">如果您想要檢閱每日總計將不同的日期 （例如，從四個月以前的日期） 您可以使用報告指令程式來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0fa38-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="0fa38-118">系統管理員也可能會感興趣的文件中[使用 Excel 擷取 Office 365 報表資料](https://msdn.microsoft.com/library/dn781442.aspx)，以及說明如何使用 Microsoft Excel 中的 OData 資料查詢功能，來建立自訂的 office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="0fa38-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="0fa38-119">自訂的報表可讓您能夠語音輸入的資料 （及多少資料） 會傳回從 Office 365 報告服務。</span><span class="sxs-lookup"><span data-stu-id="0fa38-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="0fa38-120">自訂報告也可讓您指定應該如何排序及群組，資料的變得和提供存取不會顯示在系統管理中心中的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="0fa38-121">具有開發背景的系統管理員可以使用 REST web 服務以取得未顯示在 Skype 商務 Online 系統管理中心中的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fa38-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="0fa38-122">REST 服務的類似的 SOAP 服務，在於每項技術提供用戶端與伺服器之間傳輸 XML 資料的方式。</span><span class="sxs-lookup"><span data-stu-id="0fa38-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="0fa38-123">不過，REST 服務有至少兩個優點透過 SOAP 服務。</span><span class="sxs-lookup"><span data-stu-id="0fa38-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="0fa38-124">其中，其餘部分會執行使用標準化的格式，又稱為 ATOM 整合格式的 XML 資料傳輸。</span><span class="sxs-lookup"><span data-stu-id="0fa38-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="0fa38-125">相反地，SOAP 傳送資料時使用非標準格式。</span><span class="sxs-lookup"><span data-stu-id="0fa38-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="0fa38-126">此外，其餘部分會能夠跨封鎖 HTTP 動詞 GET 與文章以外的網路傳送資料。</span><span class="sxs-lookup"><span data-stu-id="0fa38-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0fa38-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0fa38-127">See Also</span></span>


<span data-ttu-id="0fa38-128">[Lync Online 報告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0fa38-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="0fa38-129">Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="0fa38-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="0fa38-130">了解 Office 365 報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="0fa38-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="0fa38-131">[Exchange Online 報告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0fa38-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="0fa38-132">使用 Excel 擷取 Office 365 報表資料</span><span class="sxs-lookup"><span data-stu-id="0fa38-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

