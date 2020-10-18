---
title: Lync Server 2013：裝置報告
description: Lync Server 2013：裝置報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575119"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="3fcda-103">Lync Server 2013 中的裝置報表</span><span class="sxs-lookup"><span data-stu-id="3fcda-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fcda-104">_**主題上次修改日期：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="3fcda-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="3fcda-105">裝置報告可能更好的名稱是麥克風和揚聲器報告;這是因為裝置報表會檢索與通話相關的計量，例如通話百分比、迴響和語音切換時間) 依通話中使用的麥克風群組所進行的 (。</span><span class="sxs-lookup"><span data-stu-id="3fcda-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="3fcda-106">如果您想要使用 IP 電話 (也通常稱為 "裝置" ) ，請改用 [Lync Server 2013 中的 IP 電話清查報告](lync-server-2013-ip-phone-inventory-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="3fcda-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="3fcda-107">裝置報告對於判斷特定類型的裝置是否有超過其他的高品質通話時，對系統管理員非常有用。</span><span class="sxs-lookup"><span data-stu-id="3fcda-107">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="3fcda-108">反過來，這可能會影響購買新裝置或更換現有裝置時必須進行的任何決策。</span><span class="sxs-lookup"><span data-stu-id="3fcda-108">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="3fcda-109">根據預設，裝置報告中顯示的資訊也是以麥克風 () 和揚聲器/耳機 () 在通話中使用的呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="3fcda-109">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="3fcda-110">例如，假設您有數個使用者使用下列捕獲裝置及下列轉譯裝置：根據預設，裝置報告中顯示的資訊也是以麥克風 () 和揚聲器/耳機 () 在通話中使用的呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="3fcda-110">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="3fcda-111">例如，假設您有數個使用者使用下列捕獲裝置及下列 render 裝置：</span><span class="sxs-lookup"><span data-stu-id="3fcda-111">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="3fcda-112">Capture device--麥克風 (SoundMAX 整合式數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="3fcda-113">Render 裝置--耳機耳機 (Microsoft LifeChat LX-3000) </span><span class="sxs-lookup"><span data-stu-id="3fcda-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="3fcda-114">如果這些使用者總共撥打254，您會在報告中看到如下的輸入：</span><span class="sxs-lookup"><span data-stu-id="3fcda-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fcda-115">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-115">Capture device</span></span></th>
<th><span data-ttu-id="3fcda-116">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-116">Render device</span></span></th>
<th><span data-ttu-id="3fcda-117">通話數量</span><span class="sxs-lookup"><span data-stu-id="3fcda-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-118">麥克風 (SoundMAX 整合的數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-119">耳機耳機 (Microsoft LifeChat LX-3000) </span><span class="sxs-lookup"><span data-stu-id="3fcda-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-120">254</span><span class="sxs-lookup"><span data-stu-id="3fcda-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fcda-121">現在，假設您有許多使用者使用相同的捕獲裝置，但有不同的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="3fcda-121">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="3fcda-122">在此情況下，報表中會有第二個行專案，一個用於捕獲裝置和 render 裝置的唯一組合：</span><span class="sxs-lookup"><span data-stu-id="3fcda-122">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fcda-123">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-123">Capture device</span></span></th>
<th><span data-ttu-id="3fcda-124">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-124">Render device</span></span></th>
<th><span data-ttu-id="3fcda-125">通話數量</span><span class="sxs-lookup"><span data-stu-id="3fcda-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-126">麥克風 (SoundMAX 整合的數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-127">耳機耳機 (Microsoft LifeChat LX-3000) </span><span class="sxs-lookup"><span data-stu-id="3fcda-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-128">254</span><span class="sxs-lookup"><span data-stu-id="3fcda-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-129">麥克風 (SoundMAX 整合的數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-130">揚聲器 (SoundMAX 整合的數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-131">319</span><span class="sxs-lookup"><span data-stu-id="3fcda-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fcda-132">如果您想要查看指定裝置的組合總數 (例如，針對 SoundMAX 捕獲裝置，不論) 使用的呈現裝置為何，請從 [裝置類型] 下拉式清單中選取適當的選項， ([捕獲裝置] 或 [轉譯裝置]) 。</span><span class="sxs-lookup"><span data-stu-id="3fcda-132">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="3fcda-133">如果您在此範例中選取 [捕獲裝置]，將會提供如下的輸出：</span><span class="sxs-lookup"><span data-stu-id="3fcda-133">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fcda-134">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-134">Capture device</span></span></th>
<th><span data-ttu-id="3fcda-135">通話數量</span><span class="sxs-lookup"><span data-stu-id="3fcda-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-136">麥克風 (SoundMAX 整合的數位 HD 音訊) </span><span class="sxs-lookup"><span data-stu-id="3fcda-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="3fcda-137">573</span><span class="sxs-lookup"><span data-stu-id="3fcda-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="3fcda-138">存取裝置報告</span><span class="sxs-lookup"><span data-stu-id="3fcda-138">Accessing the Device Report</span></span>

<span data-ttu-id="3fcda-139">裝置報告通常是從監控報告首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="3fcda-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3fcda-140">不過，如果您要 [在 Lync Server 2013 中查看 [通話詳細資料包告](lync-server-2013-call-detail-report.md) ]，您可以按一下下列其中一個計量，以深入查看特定裝置的裝置報告：</span><span class="sxs-lookup"><span data-stu-id="3fcda-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3fcda-141">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-141">Capture Device</span></span>

  - <span data-ttu-id="3fcda-142">Render 裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-142">Render Device</span></span>

<span data-ttu-id="3fcda-143">在裝置報告中，您可以按一下下列其中一項度量，向下流覽 [Lync Server 2013 中的 [通話清單] 報告](lync-server-2013-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="3fcda-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3fcda-144">通話數量</span><span class="sxs-lookup"><span data-stu-id="3fcda-144">Call volume</span></span>

  - <span data-ttu-id="3fcda-145">通話百分比不佳</span><span class="sxs-lookup"><span data-stu-id="3fcda-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="3fcda-146">充分運用裝置報告</span><span class="sxs-lookup"><span data-stu-id="3fcda-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="3fcda-147">當您進入裝置名稱時，裝置報告非常詳細;例如，假設您有下列捕獲裝置：</span><span class="sxs-lookup"><span data-stu-id="3fcda-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="3fcda-148">Aastra 3002 麥克風 (2-Aastra 3002) </span><span class="sxs-lookup"><span data-stu-id="3fcda-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="3fcda-149">Aastra 3002 麥克風 (3-Aastra 3002) </span><span class="sxs-lookup"><span data-stu-id="3fcda-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="3fcda-150">Aastra 3002 麥克風 (Aastra 3002) </span><span class="sxs-lookup"><span data-stu-id="3fcda-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="3fcda-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="3fcda-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="3fcda-152">Aastra 6725ip 麥克風 (10-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-153">Aastra 6725ip 麥克風 (10-Aastra 6725ip) -V0</span><span class="sxs-lookup"><span data-stu-id="3fcda-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="3fcda-154">Aastra 6725ip 麥克風 (2-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-155">Aastra 6725ip 麥克風 (3-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-156">Aastra 6725ip 麥克風 (4-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-157">Aastra 6725ip 麥克風 (5 Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-158">Aastra 6725ip 麥克風 (6-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-159">Aastra 6725ip 麥克風 (7-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-160">Aastra 6725ip 麥克風 (9-Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-161">Aastra 6725ip 麥克風 (9-Aastra 6725ip) -V0</span><span class="sxs-lookup"><span data-stu-id="3fcda-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="3fcda-162">Aastra 6725ip 麥克風 (Aastra 6725ip) </span><span class="sxs-lookup"><span data-stu-id="3fcda-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="3fcda-163">Aastra 6725ip 麥克風 (Aastra 6725ip) -V0</span><span class="sxs-lookup"><span data-stu-id="3fcda-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="3fcda-164">Aastra 6725ip 麥克風 (USB 音訊裝置) </span><span class="sxs-lookup"><span data-stu-id="3fcda-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="3fcda-165">Aastra 6725ip 麥克風 (USB 音訊裝置) -V0</span><span class="sxs-lookup"><span data-stu-id="3fcda-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fcda-166">請記住，如果您正在執行 Lync Server 2013 的當地語系化版本，則捕獲裝置名稱可能不會相同。</span><span class="sxs-lookup"><span data-stu-id="3fcda-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="3fcda-167">名為 Aastra 6725ip 麥克風 (Aastra 6725ip 的裝置會以法文或西班牙文以不同的名稱) -V0。</span><span class="sxs-lookup"><span data-stu-id="3fcda-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="3fcda-168">您經常會想要此層級的詳細資料。不過，在其他時間，您可能只會對使用任何 Aastra 麥克風的來電數目感興趣，不論型號為何。</span><span class="sxs-lookup"><span data-stu-id="3fcda-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="3fcda-169">取得資訊的方法之一，例如，將裝置報表資料匯出至 Microsoft Excel，然後將該資料儲存到逗號分隔值檔案 (例如 C： \\ data \\ Devices \_Report.csv) 。</span><span class="sxs-lookup"><span data-stu-id="3fcda-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="3fcda-170">然後，您可以使用類似下列的一組命令，匯入。CSV 檔案至 Windows PowerShell 並傳回使用 Aastra capture device 進行的呼叫總數：</span><span class="sxs-lookup"><span data-stu-id="3fcda-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="3fcda-171">這會傳回單一值，代表使用 Aastra capture device 進行的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="3fcda-171">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="3fcda-172">例如：</span><span class="sxs-lookup"><span data-stu-id="3fcda-172">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3fcda-173">篩選</span><span class="sxs-lookup"><span data-stu-id="3fcda-173">Filters</span></span>

<span data-ttu-id="3fcda-174">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="3fcda-174">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3fcda-175">例如，裝置報表可讓您篩選諸如通話類型 (，也就是呼叫用戶端呼叫) 、電話會議或公用交換電話網路 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="3fcda-175">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="3fcda-176">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="3fcda-176">You can also choose how data should be grouped.</span></span> <span data-ttu-id="3fcda-177">在此情況下，裝置會依小時、天、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="3fcda-177">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3fcda-178">下表列出您可以搭配設備報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="3fcda-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="3fcda-179">裝置報表篩選</span><span class="sxs-lookup"><span data-stu-id="3fcda-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fcda-180">名稱</span><span class="sxs-lookup"><span data-stu-id="3fcda-180">Name</span></span></th>
<th><span data-ttu-id="3fcda-181">描述</span><span class="sxs-lookup"><span data-stu-id="3fcda-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-182"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-p111">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3fcda-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3fcda-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3fcda-p112">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3fcda-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3fcda-188">7/7/2012</span></span></p>
<p><span data-ttu-id="3fcda-189">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="3fcda-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3fcda-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3fcda-190">7/3/2012</span></span></p>
<p><span data-ttu-id="3fcda-191">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="3fcda-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-192"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-p113">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3fcda-195">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3fcda-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3fcda-p114">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3fcda-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3fcda-198">7/7/2012</span></span></p>
<p><span data-ttu-id="3fcda-199">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="3fcda-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3fcda-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3fcda-200">7/3/2012</span></span></p>
<p><span data-ttu-id="3fcda-201">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="3fcda-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-202"><strong>語音開關原因</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-203">為何必須將通話設定為半雙工模式，以避免回聲。</span><span class="sxs-lookup"><span data-stu-id="3fcda-203">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="3fcda-204">在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。</span><span class="sxs-lookup"><span data-stu-id="3fcda-204">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="3fcda-205">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-205">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-206">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-207">無</span><span class="sxs-lookup"><span data-stu-id="3fcda-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-208">錯誤的時間戳記</span><span class="sxs-lookup"><span data-stu-id="3fcda-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-209">回音</span><span class="sxs-lookup"><span data-stu-id="3fcda-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-210">DNLP (動態非線性處理器) </span><span class="sxs-lookup"><span data-stu-id="3fcda-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-211">低複雜性</span><span class="sxs-lookup"><span data-stu-id="3fcda-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-212">錯誤的裝置狀態</span><span class="sxs-lookup"><span data-stu-id="3fcda-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-213">AEC 回聲 (的回聲取消) </span><span class="sxs-lookup"><span data-stu-id="3fcda-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-214"><strong>回聲原因</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-215">在來電中偵測到接受之層級的回聲的原因。</span><span class="sxs-lookup"><span data-stu-id="3fcda-215">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="3fcda-216"> (在電信中，迴響是聲音的反射，當您 yell 時，您會聽到的相同現象。 ) 選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-216">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-217">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-218">無</span><span class="sxs-lookup"><span data-stu-id="3fcda-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-219">錯誤的時間戳記</span><span class="sxs-lookup"><span data-stu-id="3fcda-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-220">AEC 回聲 (的回聲取消) </span><span class="sxs-lookup"><span data-stu-id="3fcda-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-221">ANLP (自我調整非線性處理器) </span><span class="sxs-lookup"><span data-stu-id="3fcda-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-222">DNLP (動態非線性處理器) </span><span class="sxs-lookup"><span data-stu-id="3fcda-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-223">麥克風剪貼</span><span class="sxs-lookup"><span data-stu-id="3fcda-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-224"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-225">會指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="3fcda-225">Indicates the type of call that was made.</span></span> <span data-ttu-id="3fcda-226">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-226">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-227">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-228">用戶端呼叫</span><span class="sxs-lookup"><span data-stu-id="3fcda-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-229">PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="3fcda-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-230">電話會議</span><span class="sxs-lookup"><span data-stu-id="3fcda-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-231"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-p118">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-234">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-235">內部</span><span class="sxs-lookup"><span data-stu-id="3fcda-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-236">外部</span><span class="sxs-lookup"><span data-stu-id="3fcda-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-237"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-p119">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-240">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-241">有線</span><span class="sxs-lookup"><span data-stu-id="3fcda-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-242">無線</span><span class="sxs-lookup"><span data-stu-id="3fcda-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-p120">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-246">一切</span><span class="sxs-lookup"><span data-stu-id="3fcda-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-247">VPN</span><span class="sxs-lookup"><span data-stu-id="3fcda-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-248">非 VPN</span><span class="sxs-lookup"><span data-stu-id="3fcda-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-249"><strong>裝置類型</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-250">會指出裝置的類型。</span><span class="sxs-lookup"><span data-stu-id="3fcda-250">Indicates the type of device.</span></span> <span data-ttu-id="3fcda-251">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3fcda-251">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-252">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-253">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="3fcda-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3fcda-254">捕獲/呈現裝置配對</span><span class="sxs-lookup"><span data-stu-id="3fcda-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-255"><strong>裝置名稱</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-256">Capture 或 render 裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="3fcda-256">Name of the capture or render device.</span></span> <span data-ttu-id="3fcda-257">您可以輸入完整的裝置名稱或任何部分的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3fcda-257">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="3fcda-258">例如，若要在 Microsoft LifeCam VX-1000 ) 中尋找裝置麥克風 (，您可以輸入完整的裝置名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fcda-258">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="3fcda-259">麥克風 (Microsoft LifeCam VX-1000。 ) </span><span class="sxs-lookup"><span data-stu-id="3fcda-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="3fcda-260">或者，您可以只輸入名稱的一部分。</span><span class="sxs-lookup"><span data-stu-id="3fcda-260">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="3fcda-261">例如：</span><span class="sxs-lookup"><span data-stu-id="3fcda-261">For example:</span></span></p>
<p><span data-ttu-id="3fcda-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="3fcda-262">LifeCam</span></span></p>
<p><span data-ttu-id="3fcda-263">請注意，前述的篩選會傳回任何 &quot; &quot; 在名稱中包含字串 LifeCam 任何地方的裝置。</span><span class="sxs-lookup"><span data-stu-id="3fcda-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3fcda-264">指標</span><span class="sxs-lookup"><span data-stu-id="3fcda-264">Metrics</span></span>

<span data-ttu-id="3fcda-265">下表列出裝置報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="3fcda-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="3fcda-266">裝置報表計量</span><span class="sxs-lookup"><span data-stu-id="3fcda-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fcda-267">姓名</span><span class="sxs-lookup"><span data-stu-id="3fcda-267">Name</span></span></th>
<th><span data-ttu-id="3fcda-268">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="3fcda-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3fcda-269">描述</span><span class="sxs-lookup"><span data-stu-id="3fcda-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-270"><strong>擷取裝置</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-271">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-272">裝置 (例如，用來傳送音訊的麥克風或網路攝像機) 。</span><span class="sxs-lookup"><span data-stu-id="3fcda-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-273"><strong>轉換裝置</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-274">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-275">裝置 (例如，耳機或揚聲器) 用於接收音訊。</span><span class="sxs-lookup"><span data-stu-id="3fcda-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-276"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-277">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-278">發出的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="3fcda-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-279"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-280">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-281">分類為不良之通話的百分比 &quot; 。 &quot; 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="3fcda-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-282"><strong>唯一使用者</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-283">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-284">使用裝置的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="3fcda-284">Unique users who used the device.</span></span> <span data-ttu-id="3fcda-285">如果使用者使用的設備13次，他或她會算作一個唯一的使用者，與只使用裝置一次的使用者相同。</span><span class="sxs-lookup"><span data-stu-id="3fcda-285">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-286"><strong>語音切換時間的比例</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-287">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-288">必須以半雙工模式進行的通話所占的百分比，以避免回聲。</span><span class="sxs-lookup"><span data-stu-id="3fcda-288">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="3fcda-289">在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。</span><span class="sxs-lookup"><span data-stu-id="3fcda-289">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-290"><strong>麥克風未運作的比率</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-291">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-292">在可接受的層級上，捕獲裝置無法運作之通話所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-292">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="3fcda-293">高值表示呼叫的品質問題主要是由於捕獲裝置沒有如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="3fcda-293">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-294"><strong>音箱未運作的比例</strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-295">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-296">在可接受的層級上，呈現裝置無法運作的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-296">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="3fcda-297">高值表示呼叫的品質問題主要是因為呈現裝置未如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="3fcda-297">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-298"><strong>使用語音切換 (% ) 進行通話 </strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-299">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-300">必須放入半雙工模式之總通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-300">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="3fcda-301">在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。</span><span class="sxs-lookup"><span data-stu-id="3fcda-301">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-302"><strong>在 (% ) 中回顯麥克風 </strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-303">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-304">在麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="3fcda-305">通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。</span><span class="sxs-lookup"><span data-stu-id="3fcda-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="3fcda-306">針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="3fcda-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="3fcda-307">若為其他裝置，則不應該使用此度量來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="3fcda-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fcda-308"><strong>迴響傳送 (% ) </strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-309">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-310">傳送至其他使用者的回音百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fcda-311"><strong>使用迴響 (% ) 進行呼叫 </strong></span><span class="sxs-lookup"><span data-stu-id="3fcda-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="3fcda-312">是</span><span class="sxs-lookup"><span data-stu-id="3fcda-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="3fcda-313">迴響超過可接受層級之總通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="3fcda-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

