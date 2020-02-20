---
title: Lync Server 2013： 失敗清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc3d74e6613f54f346e00328f1fae929f7def27
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="1eeed-102">Lync Server 2013 中的失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="1eeed-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eeed-103">_**主題上次修改日期：** 2012年-07-02_</span><span class="sxs-lookup"><span data-stu-id="1eeed-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="1eeed-104">失敗清單報告提供參與失敗對等端對端或會議工作階段之個別參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1eeed-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="1eeed-105">此資訊包括遇到問題，以及 SIP 回應碼之使用者的 URI，並診斷識別碼相關聯失敗。</span><span class="sxs-lookup"><span data-stu-id="1eeed-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="1eeed-106">存取失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="1eeed-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="1eeed-107">按一下任何[失敗散佈報告在 Lync Server 2013](lync-server-2013-failure-distribution-report.md)上的下列計量來存取失敗清單報告：</span><span class="sxs-lookup"><span data-stu-id="1eeed-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="1eeed-108">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="1eeed-109">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="1eeed-110">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="1eeed-111">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="1eeed-112">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-112">Top components (sessions)</span></span>

  - <span data-ttu-id="1eeed-113">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="1eeed-114">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="1eeed-115">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="1eeed-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="1eeed-116">您可以從 Failure List Report]，即可工作階段詳細資料] 計量端對端工作階段存取[Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="1eeed-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="1eeed-117">您也可以藉由按一下 [會議] 計量的會議存取會議詳細資料報告。</span><span class="sxs-lookup"><span data-stu-id="1eeed-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="1eeed-118">失敗清單報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="1eeed-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="1eeed-119">在失敗清單報告中，您可以檢視每個回應程式碼或每個診斷識別碼的描述，只要該值上按住滑鼠。</span><span class="sxs-lookup"><span data-stu-id="1eeed-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="1eeed-120">例如，如果將滑鼠停留診斷識別碼 7025 您會看到下列工具提示中顯示：</span><span class="sxs-lookup"><span data-stu-id="1eeed-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="1eeed-121">建立使用者的媒體的內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="1eeed-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="1eeed-122">請務必注意 Failure List Report 不提供直接的方法，以直接擷取清單中的所有使用者參與至少一個與失敗工作階段，也不會提供方法來決定哪些使用者最常有關的失敗工作階段。</span><span class="sxs-lookup"><span data-stu-id="1eeed-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="1eeed-123">（第一，Failure List Report 有無篩選功能）。不過，如果您將資料匯出，然後將它轉換成逗點分隔值檔案，您可以使用 Windows PowerShell 來尋找類似這些問題的答案。</span><span class="sxs-lookup"><span data-stu-id="1eeed-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="1eeed-124">例如，假設您儲存的資料。CSV 檔名為 c:\\資料\\失敗\_List.csv。</span><span class="sxs-lookup"><span data-stu-id="1eeed-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="1eeed-125">根據儲存在該檔案中的資料，此命令會列出所有已至少一個失敗工作階段相關的使用者：</span><span class="sxs-lookup"><span data-stu-id="1eeed-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="1eeed-126">該命令會傳回清單類似這樣：</span><span class="sxs-lookup"><span data-stu-id="1eeed-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="1eeed-127">這兩個命令可回報告每位使用者遭遇的失敗工作階段總數：</span><span class="sxs-lookup"><span data-stu-id="1eeed-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="1eeed-128">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="1eeed-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1eeed-129">篩選</span><span class="sxs-lookup"><span data-stu-id="1eeed-129">Filters</span></span>

<span data-ttu-id="1eeed-130">無。</span><span class="sxs-lookup"><span data-stu-id="1eeed-130">None.</span></span> <span data-ttu-id="1eeed-131">您無法篩選 Failure List Report。</span><span class="sxs-lookup"><span data-stu-id="1eeed-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1eeed-132">計量</span><span class="sxs-lookup"><span data-stu-id="1eeed-132">Metrics</span></span>

<span data-ttu-id="1eeed-133">下表列出失敗清單報告針對每通失敗通話所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="1eeed-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="1eeed-134">失敗清單報告計量</span><span class="sxs-lookup"><span data-stu-id="1eeed-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eeed-135">名稱</span><span class="sxs-lookup"><span data-stu-id="1eeed-135">Name</span></span></th>
<th><span data-ttu-id="1eeed-136">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="1eeed-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eeed-137">描述</span><span class="sxs-lookup"><span data-stu-id="1eeed-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eeed-138"><strong>報告的時間</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-139">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-139">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-140">日期和時間報告的記錄。</span><span class="sxs-lookup"><span data-stu-id="1eeed-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eeed-141"><strong>要求</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-142">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-142">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-143">SIP 失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="1eeed-143">SIP request type that failed.</span></span> <span data-ttu-id="1eeed-144">例如，邀請或 BYE。</span><span class="sxs-lookup"><span data-stu-id="1eeed-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eeed-145"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-146">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-146">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-147">會議失敗時所傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="1eeed-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eeed-148"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-149">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-149">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-150">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="1eeed-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eeed-151"><strong>加入時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-152">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-152">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-153">量所需的使用者加入會議的時間 （以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="1eeed-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eeed-154"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-155">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-155">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-156">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="1eeed-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eeed-157"><strong>來源使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-158">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-158">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-159">撥打通話之使用者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="1eeed-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eeed-160"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="1eeed-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="1eeed-161">否</span><span class="sxs-lookup"><span data-stu-id="1eeed-161">No</span></span></p></td>
<td><p><span data-ttu-id="1eeed-162">要呼叫之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="1eeed-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

