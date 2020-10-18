---
title: Lync Server 2013：失敗清單報告
description: Lync Server 2013：失敗清單報告。
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
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575049"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="b4154-103">Lync Server 2013 的失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="b4154-103">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4154-104">_**主題上次修改日期：** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="b4154-104">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="b4154-105">「失敗清單報告」會提供參與「對等」或「會議」會話失敗之人員的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b4154-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="b4154-106">此資訊包含發生問題之使用者的 URI，以及與失敗相關聯的 SIP 回應碼和診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="b4154-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="b4154-107">存取失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="b4154-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="b4154-108">若要存取失敗清單報告，請在 [ [Lync Server 2013] 中的 [失敗] 散佈報告](lync-server-2013-failure-distribution-report.md)上，按一下下列任一度量值：</span><span class="sxs-lookup"><span data-stu-id="b4154-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="b4154-109">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-109">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="b4154-110">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-110">Top modalities (sessions)</span></span>

  - <span data-ttu-id="b4154-111">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-111">Top pools (sessions)</span></span>

  - <span data-ttu-id="b4154-112">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-112">Top sources (sessions)</span></span>

  - <span data-ttu-id="b4154-113">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-113">Top components (sessions)</span></span>

  - <span data-ttu-id="b4154-114">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-114">Top from users (sessions)</span></span>

  - <span data-ttu-id="b4154-115">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-115">Top to users (sessions)</span></span>

  - <span data-ttu-id="b4154-116">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="b4154-116">Top from user agents (sessions)</span></span>

<span data-ttu-id="b4154-117">在 [失敗清單] 報告中，您可以按一下點對點工作階段的會話詳細資料計量， [以在 Lync Server 2013 中存取 Peer-to-Peer 會話詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="b4154-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="b4154-118">您也可以按一下會議的會議度量來存取會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="b4154-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="b4154-119">讓 [失敗清單] 報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="b4154-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="b4154-120">在 [失敗清單] 報告中，只要將滑鼠停留在該值上，您就可以查看每個回應代碼或每個診斷識別碼的描述。</span><span class="sxs-lookup"><span data-stu-id="b4154-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="b4154-121">例如，如果您將滑鼠停留在診斷 ID 7025 上，您會看到工具提示中顯示下列內容：</span><span class="sxs-lookup"><span data-stu-id="b4154-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="b4154-122">為使用者建立媒體時發生內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="b4154-122">Internal server error creating media for user.</span></span>

<span data-ttu-id="b4154-123">請務必注意，失敗清單報告並未提供直接找回至少參與一則失敗之會話之所有使用者的清單，也不會提供一種方法來判斷失敗的會話中最常參與的使用者。</span><span class="sxs-lookup"><span data-stu-id="b4154-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="b4154-124"> (一件事，失敗清單報告沒有篩選功能。 ) 不過，如果您匯出資料，然後將其轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 尋找類似問題的答案。</span><span class="sxs-lookup"><span data-stu-id="b4154-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="b4154-125">例如，假設您將資料儲存到。名為 C： \\ 資料 \\ 失敗 \_List.csv 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b4154-125">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="b4154-126">根據儲存在該檔案中的資料，此命令會列出至少包含一個失敗會話的所有使用者：</span><span class="sxs-lookup"><span data-stu-id="b4154-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="b4154-127">該命令會傳回類似以下的清單：</span><span class="sxs-lookup"><span data-stu-id="b4154-127">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="b4154-128">這兩個命令傳回每位使用者參與的失敗會話總數：</span><span class="sxs-lookup"><span data-stu-id="b4154-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="b4154-129">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="b4154-129">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b4154-130">篩選</span><span class="sxs-lookup"><span data-stu-id="b4154-130">Filters</span></span>

<span data-ttu-id="b4154-131">無。</span><span class="sxs-lookup"><span data-stu-id="b4154-131">None.</span></span> <span data-ttu-id="b4154-132">您無法篩選失敗清單報告。</span><span class="sxs-lookup"><span data-stu-id="b4154-132">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b4154-133">指標</span><span class="sxs-lookup"><span data-stu-id="b4154-133">Metrics</span></span>

<span data-ttu-id="b4154-134">下表列出每個失敗通話的失敗清單報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4154-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="b4154-135">失敗清單報告計量</span><span class="sxs-lookup"><span data-stu-id="b4154-135">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4154-136">姓名</span><span class="sxs-lookup"><span data-stu-id="b4154-136">Name</span></span></th>
<th><span data-ttu-id="b4154-137">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="b4154-137">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b4154-138">描述</span><span class="sxs-lookup"><span data-stu-id="b4154-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4154-139"><strong>報告時間</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-139"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-140">否</span><span class="sxs-lookup"><span data-stu-id="b4154-140">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-141">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="b4154-141">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4154-142"><strong>請求</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-142"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-143">否</span><span class="sxs-lookup"><span data-stu-id="b4154-143">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-144">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="b4154-144">SIP request type that failed.</span></span> <span data-ttu-id="b4154-145">例如，INVITE 或再見。</span><span class="sxs-lookup"><span data-stu-id="b4154-145">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4154-146"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-146"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-147">否</span><span class="sxs-lookup"><span data-stu-id="b4154-147">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-148">會議失敗時所傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="b4154-148">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4154-149"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-149"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-150">否</span><span class="sxs-lookup"><span data-stu-id="b4154-150">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-151">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="b4154-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4154-152"><strong>加入成本時間 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="b4154-152"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-153">否</span><span class="sxs-lookup"><span data-stu-id="b4154-153">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-154">使用者加入會議所需的時間長度 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="b4154-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4154-155"><strong>來源使用者</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-155"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-156">否</span><span class="sxs-lookup"><span data-stu-id="b4154-156">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-157">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b4154-157">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4154-158"><strong>從使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-158"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-159">否</span><span class="sxs-lookup"><span data-stu-id="b4154-159">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-160">起始通話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="b4154-160">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4154-161"><strong>目標使用者</strong></span><span class="sxs-lookup"><span data-stu-id="b4154-161"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="b4154-162">否</span><span class="sxs-lookup"><span data-stu-id="b4154-162">No</span></span></p></td>
<td><p><span data-ttu-id="b4154-163">呼叫之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b4154-163">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

