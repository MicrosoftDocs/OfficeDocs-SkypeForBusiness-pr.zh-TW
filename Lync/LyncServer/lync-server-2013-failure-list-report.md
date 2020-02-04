---
title: Lync Server 2013：失敗清單報告
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
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="ab2ce-102">Lync Server 2013 中的 [失敗清單] 報告</span><span class="sxs-lookup"><span data-stu-id="ab2ce-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab2ce-103">_**主題上次修改日期：** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="ab2ce-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="ab2ce-104">[失敗清單] 報告會提供參與對等無法進行對等或會議會話的個別參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="ab2ce-105">此資訊包含遇到問題之使用者的 URI，以及與失敗相關聯的 SIP 回應程式碼與診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="ab2ce-106">存取失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="ab2ce-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="ab2ce-107">您可以在[Lync Server 2013 的 [失敗] 發佈報告中](lync-server-2013-failure-distribution-report.md)，按一下下列任何一個測量，以存取 [失敗清單] 報告：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="ab2ce-108">常見的診斷原因（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="ab2ce-109">熱門形式（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="ab2ce-110">頂層池（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="ab2ce-111">熱門來源（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="ab2ce-112">Top 元件（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-112">Top components (sessions)</span></span>

  - <span data-ttu-id="ab2ce-113">使用者的最上層（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="ab2ce-114">使用者的最上層（會話）</span><span class="sxs-lookup"><span data-stu-id="ab2ce-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="ab2ce-115">使用者代理程式（會話）的頂端</span><span class="sxs-lookup"><span data-stu-id="ab2ce-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="ab2ce-116">在 [失敗清單] 報告中，您可以透過按一下點對點工作階段的會話詳細資料指標，[在 Lync Server 2013 中存取點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="ab2ce-117">您也可以按一下會議的會議指標，以存取會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="ab2ce-118">充分利用 [失敗清單] 報告</span><span class="sxs-lookup"><span data-stu-id="ab2ce-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="ab2ce-119">在 [失敗清單] 報告中，您只要將滑鼠放在該值上，就能查看每個回應代碼或每個診斷 ID 的描述。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="ab2ce-120">例如，如果您將滑鼠放在診斷 ID 7025 上，您會看到下列顯示在工具提示中：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="ab2ce-121">為使用者建立媒體時發生內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="ab2ce-122">請務必注意，[失敗清單] 報告不會提供直接檢索至少參與一個失敗會話之所有使用者清單的簡單方法，也不會提供判斷哪些使用者最常參與失敗的方法。課時.</span><span class="sxs-lookup"><span data-stu-id="ab2ce-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="ab2ce-123">（一件事，失敗清單報告沒有篩選功能）。不過，如果您匯出資料，然後將它轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 來尋找問題等問題的答案。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="ab2ce-124">例如，假設您將資料儲存至。名為 C：\\資料\\失敗\_清單 .csv 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="ab2ce-125">根據儲存在該檔案中的資料，此命令會列出至少有一個失敗的會話中所涉及的所有使用者：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="ab2ce-126">該命令會傳回如下所示的清單：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="ab2ce-127">這兩個命令會傳回每位使用者所涉及的失敗會話總數：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="ab2ce-128">這樣會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="ab2ce-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ab2ce-129">濾鏡</span><span class="sxs-lookup"><span data-stu-id="ab2ce-129">Filters</span></span>

<span data-ttu-id="ab2ce-130">無。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-130">None.</span></span> <span data-ttu-id="ab2ce-131">您無法篩選失敗清單報告。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ab2ce-132">指標</span><span class="sxs-lookup"><span data-stu-id="ab2ce-132">Metrics</span></span>

<span data-ttu-id="ab2ce-133">下表列出每個失敗的通話在失敗清單報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="ab2ce-134">失敗清單報告度量單位</span><span class="sxs-lookup"><span data-stu-id="ab2ce-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab2ce-135">名稱</span><span class="sxs-lookup"><span data-stu-id="ab2ce-135">Name</span></span></th>
<th><span data-ttu-id="ab2ce-136">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="ab2ce-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ab2ce-137">說明</span><span class="sxs-lookup"><span data-stu-id="ab2ce-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab2ce-138"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-139">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-139">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-140">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2ce-141"><strong>徵求</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-142">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-142">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-143">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-143">SIP request type that failed.</span></span> <span data-ttu-id="ab2ce-144">例如，[邀請] 或 [再見]。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2ce-145"><strong>回應代碼</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-146">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-146">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-147">在會議失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2ce-148"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-149">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-149">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-150">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2ce-151"><strong>加入成本時間（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-152">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-152">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-153">使用者加入會議所需的時間長度（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2ce-154"><strong>從使用者</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-155">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-155">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-156">啟動通話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2ce-157"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-158">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-158">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-159">啟動通話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2ce-160"><strong>給使用者</strong></span><span class="sxs-lookup"><span data-stu-id="ab2ce-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2ce-161">否</span><span class="sxs-lookup"><span data-stu-id="ab2ce-161">No</span></span></p></td>
<td><p><span data-ttu-id="ab2ce-162">呼叫的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="ab2ce-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

