---
title: Lync Server 2013： 裝置報告
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
ms.openlocfilehash: 5dbfb056107d84aa0f3c483100619b27251feff4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="66c18-102">Lync Server 2013 中的裝置報告</span><span class="sxs-lookup"><span data-stu-id="66c18-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c18-103">_**上次修改主題：** 2013年-11-12_</span><span class="sxs-lookup"><span data-stu-id="66c18-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="66c18-104">裝置報告可能是更妥善地標題為 「 麥克風和喇叭報告;這是因為 「 裝置報告擷取通話相關計量 （例如 [收訊不良通話百分比、 和回音，且語音交換時間） 依據麥克風和喇叭呼叫時所使用。</span><span class="sxs-lookup"><span data-stu-id="66c18-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="66c18-105">如果您有興趣 IP 電話 （通常也稱為 「 裝置 」），請改為使用[Lync Server 2013 中的 IP 電話清查報告](lync-server-2013-ip-phone-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="66c18-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="66c18-106">裝置報告是裝置的非常適合在判斷特定類型發生大量比其他通話品質不良的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="66c18-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="66c18-107">接著，這可能影響任何提到時間若要購買新的裝置或取代現有的裝置時，您必須進行的決策。</span><span class="sxs-lookup"><span data-stu-id="66c18-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="66c18-108">根據預設，「 裝置報告中顯示的資訊是也根據 （的擷取裝置） 的麥克風和喇叭/耳機 （轉換裝置） 呼叫時所使用。</span><span class="sxs-lookup"><span data-stu-id="66c18-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="66c18-109">例如，假設您有幾個使用下列的擷取裝置的使用者，且下列轉換裝置： 根據預設，「 裝置報告中顯示的資訊也會根據 （的擷取裝置） 的麥克風和喇叭/耳機 （轉換裝置） 呼叫時所使用。</span><span class="sxs-lookup"><span data-stu-id="66c18-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="66c18-110">例如，假設您有幾個使用下列的擷取裝置的使用者，且下列轉換裝置：</span><span class="sxs-lookup"><span data-stu-id="66c18-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="66c18-111">擷取裝置--麥克風 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="66c18-112">轉換裝置--耳麥式耳機 (Microsoft LifeChat lx-3000)</span><span class="sxs-lookup"><span data-stu-id="66c18-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="66c18-113">如果這些使用者總共來電 254 您會看到類似報表中的項目：</span><span class="sxs-lookup"><span data-stu-id="66c18-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c18-114">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-114">Capture device</span></span></th>
<th><span data-ttu-id="66c18-115">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-115">Render device</span></span></th>
<th><span data-ttu-id="66c18-116">[通話數</span><span class="sxs-lookup"><span data-stu-id="66c18-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c18-117">麥克風 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="66c18-118">耳麥式耳機 (Microsoft LifeChat lx-3000)</span><span class="sxs-lookup"><span data-stu-id="66c18-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="66c18-119">254</span><span class="sxs-lookup"><span data-stu-id="66c18-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66c18-120">現在，假設您有使用相同的擷取裝置，但不同轉換裝置的使用者人數的數字。</span><span class="sxs-lookup"><span data-stu-id="66c18-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="66c18-121">在此情況下，您必須第二行項目在報告中，一個唯一組合的擷取裝置和轉換裝置：</span><span class="sxs-lookup"><span data-stu-id="66c18-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c18-122">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-122">Capture device</span></span></th>
<th><span data-ttu-id="66c18-123">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-123">Render device</span></span></th>
<th><span data-ttu-id="66c18-124">[通話數</span><span class="sxs-lookup"><span data-stu-id="66c18-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c18-125">麥克風 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="66c18-126">耳麥式耳機 (Microsoft LifeChat lx-3000)</span><span class="sxs-lookup"><span data-stu-id="66c18-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="66c18-127">254</span><span class="sxs-lookup"><span data-stu-id="66c18-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-128">麥克風 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="66c18-129">喇叭 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="66c18-130">319</span><span class="sxs-lookup"><span data-stu-id="66c18-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66c18-131">如果您想看到的特定裝置 （例如，針對 SoundMAX 擷取裝置，不論用轉換裝置） 合併的總計，請從裝置類型] 下拉式清單 （擷取裝置或轉換裝置） 選取適當的選項。</span><span class="sxs-lookup"><span data-stu-id="66c18-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="66c18-132">如果您選取擷取裝置在這個範例中，這樣會顯示類似這樣的您輸出：</span><span class="sxs-lookup"><span data-stu-id="66c18-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c18-133">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-133">Capture device</span></span></th>
<th><span data-ttu-id="66c18-134">[通話數</span><span class="sxs-lookup"><span data-stu-id="66c18-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c18-135">麥克風 (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="66c18-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="66c18-136">573</span><span class="sxs-lookup"><span data-stu-id="66c18-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="66c18-137">存取裝置報告</span><span class="sxs-lookup"><span data-stu-id="66c18-137">Accessing the Device Report</span></span>

<span data-ttu-id="66c18-138">裝置報告通常是從監視報告首頁存取。</span><span class="sxs-lookup"><span data-stu-id="66c18-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="66c18-139">不過，如果您正在檢視[Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)您可以按一下向下切入裝置報告特定裝置的下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="66c18-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="66c18-140">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-140">Capture Device</span></span>

  - <span data-ttu-id="66c18-141">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-141">Render Device</span></span>

<span data-ttu-id="66c18-142">從 「 裝置報告您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="66c18-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="66c18-143">[通話數</span><span class="sxs-lookup"><span data-stu-id="66c18-143">Call volume</span></span>

  - <span data-ttu-id="66c18-144">通話不良百分比</span><span class="sxs-lookup"><span data-stu-id="66c18-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="66c18-145">裝置報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="66c18-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="66c18-146">裝置名稱，對過濾極詳細說明 「 裝置報告;例如，假設您有下列擷取裝置：</span><span class="sxs-lookup"><span data-stu-id="66c18-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="66c18-147">Aastra 3002 麥克風 (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="66c18-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="66c18-148">Aastra 3002 麥克風 (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="66c18-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="66c18-149">Aastra 3002 麥克風 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="66c18-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="66c18-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="66c18-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="66c18-151">Aastra 6725ip 麥克風 (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-152">Aastra 6725ip 麥克風 (10-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="66c18-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="66c18-153">Aastra 6725ip 麥克風 (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-154">Aastra 6725ip 麥克風 (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-155">Aastra 6725ip 麥克風 (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-156">Aastra 6725ip 麥克風 (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-157">Aastra 6725ip 麥克風 (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-158">Aastra 6725ip 麥克風 (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-159">Aastra 6725ip 麥克風 (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-160">Aastra 6725ip 麥克風 (9-Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="66c18-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="66c18-161">Aastra 6725ip 麥克風 (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="66c18-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="66c18-162">Aastra 6725ip 麥克風 (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="66c18-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="66c18-163">Aastra 6725ip 麥克風 （USB 音訊裝置）</span><span class="sxs-lookup"><span data-stu-id="66c18-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="66c18-164">Aastra 6725ip 麥克風 （USB 音訊裝置）-V0</span><span class="sxs-lookup"><span data-stu-id="66c18-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66c18-165">請記住，擷取裝置名稱可能不相同如果您執行 Lync Server 2013 的當地語系化的版本。</span><span class="sxs-lookup"><span data-stu-id="66c18-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="66c18-166">裝置，名為 Aastra 6725ip 麥克風 (Aastra 6725ip)-V0 中美式英文可能有不同的名稱，在法文或西班牙文。</span><span class="sxs-lookup"><span data-stu-id="66c18-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="66c18-167">通常時間，您會想該層級的詳細資料;在其他時候，不過，您可能只會感興趣多少通話，請使用任何 Aastra 麥克風，不論型號。</span><span class="sxs-lookup"><span data-stu-id="66c18-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="66c18-168">以像取得資訊的其中一個方法是將裝置報告資料匯出至 Microsoft Excel，然後將該資料儲存成逗點分隔值檔案 (例如 c:\\資料\\裝置\_Report.csv)。</span><span class="sxs-lookup"><span data-stu-id="66c18-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="66c18-169">您接著可以使用一組類似以下的命令匯入。CSV 檔案至 Windows PowerShell 及報表後使用 Aastra 擷取裝置進行的通話總數：</span><span class="sxs-lookup"><span data-stu-id="66c18-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="66c18-170">這樣會傳回 single 值，代表使用 Aastra 擷取裝置進行的通話總數。</span><span class="sxs-lookup"><span data-stu-id="66c18-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="66c18-171">例如：</span><span class="sxs-lookup"><span data-stu-id="66c18-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="66c18-172">篩選</span><span class="sxs-lookup"><span data-stu-id="66c18-172">Filters</span></span>

<span data-ttu-id="66c18-173">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="66c18-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="66c18-174">例如，「 裝置報告可讓您篩選上為通話類型等項目 （亦即已呼叫用戶端通話），會議通話或公用交換的電話網路 (PSTN) 通話。</span><span class="sxs-lookup"><span data-stu-id="66c18-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="66c18-175">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="66c18-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="66c18-176">在此情況下，裝置會依據小時、 日、 週或月。</span><span class="sxs-lookup"><span data-stu-id="66c18-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="66c18-177">下表列出您可以使用 「 裝置報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="66c18-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="66c18-178">裝置報告篩選器</span><span class="sxs-lookup"><span data-stu-id="66c18-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c18-179">名稱</span><span class="sxs-lookup"><span data-stu-id="66c18-179">Name</span></span></th>
<th><span data-ttu-id="66c18-180">描述</span><span class="sxs-lookup"><span data-stu-id="66c18-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c18-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-p111">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c18-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="66c18-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="66c18-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66c18-p112">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="66c18-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66c18-187">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="66c18-187">7/7/2012</span></span></p>
<p><span data-ttu-id="66c18-188">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="66c18-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66c18-189">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="66c18-189">7/3/2012</span></span></p>
<p><span data-ttu-id="66c18-190">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="66c18-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-p113">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c18-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="66c18-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="66c18-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66c18-p114">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="66c18-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66c18-197">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="66c18-197">7/7/2012</span></span></p>
<p><span data-ttu-id="66c18-198">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="66c18-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66c18-199">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="66c18-199">7/3/2012</span></span></p>
<p><span data-ttu-id="66c18-200">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="66c18-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-201"><strong>語音交換原因</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-202">呼叫必須被放入半雙工模式，以避免回音的原因的原因。</span><span class="sxs-lookup"><span data-stu-id="66c18-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="66c18-203">在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。</span><span class="sxs-lookup"><span data-stu-id="66c18-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="66c18-204">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-205">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-206">無</span><span class="sxs-lookup"><span data-stu-id="66c18-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-207">不正確的時間戳記</span><span class="sxs-lookup"><span data-stu-id="66c18-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-208">回音</span><span class="sxs-lookup"><span data-stu-id="66c18-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-209">DNLP （動態非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="66c18-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-210">低複雜性</span><span class="sxs-lookup"><span data-stu-id="66c18-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-211">不良的裝置狀態</span><span class="sxs-lookup"><span data-stu-id="66c18-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-212">Post aec 後的回音 （柔和式迴音效果取消功能）</span><span class="sxs-lookup"><span data-stu-id="66c18-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-213"><strong>回音的原因</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-214">原因的呼叫中偵測到上方的可接受的層級的回音的原因。</span><span class="sxs-lookup"><span data-stu-id="66c18-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="66c18-215">（在電信，回音就是為什麼聲音，您會聽到您是否吼叫到知名的底部相同現象）。選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-216">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-217">無</span><span class="sxs-lookup"><span data-stu-id="66c18-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-218">不正確的時間戳記</span><span class="sxs-lookup"><span data-stu-id="66c18-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-219">Post aec 後的回音 （柔和式迴音效果取消功能）</span><span class="sxs-lookup"><span data-stu-id="66c18-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-220">ANLP （調適型非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="66c18-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-221">DNLP （動態非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="66c18-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-222">麥克風雜音</span><span class="sxs-lookup"><span data-stu-id="66c18-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-223"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-224">會指出所進行之通話的類型。</span><span class="sxs-lookup"><span data-stu-id="66c18-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="66c18-225">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-226">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-227">用戶端通話</span><span class="sxs-lookup"><span data-stu-id="66c18-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-228">PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="66c18-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-229">電話會議</span><span class="sxs-lookup"><span data-stu-id="66c18-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-230"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-p118">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-233">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-234">內部</span><span class="sxs-lookup"><span data-stu-id="66c18-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-235">External</span><span class="sxs-lookup"><span data-stu-id="66c18-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-236"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-p119">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-239">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-240">有線</span><span class="sxs-lookup"><span data-stu-id="66c18-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-241">無線</span><span class="sxs-lookup"><span data-stu-id="66c18-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-p120">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-245">[全部]</span><span class="sxs-lookup"><span data-stu-id="66c18-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-246">VPN</span><span class="sxs-lookup"><span data-stu-id="66c18-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-247">非 VPN</span><span class="sxs-lookup"><span data-stu-id="66c18-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-248"><strong>裝置類型</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-249">會指出裝置的類型。</span><span class="sxs-lookup"><span data-stu-id="66c18-249">Indicates the type of device.</span></span> <span data-ttu-id="66c18-250">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="66c18-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-251">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-252">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="66c18-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="66c18-253">擷取/轉換裝置配對</span><span class="sxs-lookup"><span data-stu-id="66c18-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-254"><strong>裝置名稱</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-255">擷取或轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="66c18-255">Name of the capture or render device.</span></span> <span data-ttu-id="66c18-256">您可以輸入裝置名稱的任何部分或完整的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="66c18-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="66c18-257">例如，若要尋找麥克風的裝置 （Microsoft LifeCam VX-1000 個。），您可以輸入完整的裝置名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c18-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="66c18-258">麥克風 （Microsoft LifeCam VX-1000 個。）</span><span class="sxs-lookup"><span data-stu-id="66c18-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="66c18-259">或者，您可以輸入只是部分名稱。</span><span class="sxs-lookup"><span data-stu-id="66c18-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="66c18-260">例如：</span><span class="sxs-lookup"><span data-stu-id="66c18-260">For example:</span></span></p>
<p><span data-ttu-id="66c18-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="66c18-261">LifeCam</span></span></p>
<p><span data-ttu-id="66c18-262">請注意，上述篩選中會傳回包含字串的任何裝置&quot;LifeCam&quot;其名稱中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="66c18-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="66c18-263">計量</span><span class="sxs-lookup"><span data-stu-id="66c18-263">Metrics</span></span>

<span data-ttu-id="66c18-264">下表列出裝置報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="66c18-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="66c18-265">裝置報告計量</span><span class="sxs-lookup"><span data-stu-id="66c18-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c18-266">名稱</span><span class="sxs-lookup"><span data-stu-id="66c18-266">Name</span></span></th>
<th><span data-ttu-id="66c18-267">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="66c18-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="66c18-268">描述</span><span class="sxs-lookup"><span data-stu-id="66c18-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c18-269"><strong>擷取裝置</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-270">是</span><span class="sxs-lookup"><span data-stu-id="66c18-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-271">裝置 （例如，麥克風或網路攝影機） 用於傳輸音訊。</span><span class="sxs-lookup"><span data-stu-id="66c18-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-272"><strong>轉換裝置</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-273">是</span><span class="sxs-lookup"><span data-stu-id="66c18-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-274">裝置 （例如，耳機或喇叭） 用於接收音訊。</span><span class="sxs-lookup"><span data-stu-id="66c18-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-275"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-276">是</span><span class="sxs-lookup"><span data-stu-id="66c18-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-277">撥打的通話總數。</span><span class="sxs-lookup"><span data-stu-id="66c18-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-278"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-279">是</span><span class="sxs-lookup"><span data-stu-id="66c18-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-280">之已分類為通話的百分比&quot;不佳。&quot;通話不良是任何來電指至少一項計算超出允許的值 （例如，通話過多的抖動）。</span><span class="sxs-lookup"><span data-stu-id="66c18-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-281"><strong>唯一的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-282">是</span><span class="sxs-lookup"><span data-stu-id="66c18-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-283">使用裝置的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="66c18-283">Unique users who used the device.</span></span> <span data-ttu-id="66c18-284">如果使用者使用裝置 13 時間他或她會視為一個唯一的使用者，僅使用一次裝置使用者相同。</span><span class="sxs-lookup"><span data-stu-id="66c18-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-285"><strong>語音交換時間的比率</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-286">是</span><span class="sxs-lookup"><span data-stu-id="66c18-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-287">必須進行半雙工模式，以避免回音的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="66c18-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="66c18-288">在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。</span><span class="sxs-lookup"><span data-stu-id="66c18-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-289"><strong>麥克風未運作的比率</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-290">是</span><span class="sxs-lookup"><span data-stu-id="66c18-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-291">通話百分比在其中的擷取裝置已不正常在可接受的層級。</span><span class="sxs-lookup"><span data-stu-id="66c18-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="66c18-292">高值的建議通話品質問題已主要是由於擷取裝置未如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="66c18-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-293"><strong>喇叭未運作的比率</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-294">是</span><span class="sxs-lookup"><span data-stu-id="66c18-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-295">通話百分比中的轉換裝置已無法正常運作可接受的層級。</span><span class="sxs-lookup"><span data-stu-id="66c18-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="66c18-296">高值的建議通話品質問題已主要是由於轉換裝置未如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="66c18-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-297"><strong>語音交換 （%） 的通話</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-298">是</span><span class="sxs-lookup"><span data-stu-id="66c18-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-299">這必須放入半雙工模式的總通話百分比。</span><span class="sxs-lookup"><span data-stu-id="66c18-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="66c18-300">在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。</span><span class="sxs-lookup"><span data-stu-id="66c18-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-301"><strong>麥克風回音 （%）</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-302">是</span><span class="sxs-lookup"><span data-stu-id="66c18-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-303">回音麥克風擷取資料流中偵測到時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="66c18-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="66c18-304">一般而言，值為低，耳機或 handsets，及喇叭電話或獨立喇叭較高。</span><span class="sxs-lookup"><span data-stu-id="66c18-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="66c18-305">針對支援委任柔和式迴音效果取消功能的裝置，高的值可指出回音外洩。</span><span class="sxs-lookup"><span data-stu-id="66c18-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="66c18-306">針對其他裝置，此評量不應該用來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="66c18-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c18-307"><strong>回音傳送 （%）</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-308">是</span><span class="sxs-lookup"><span data-stu-id="66c18-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-309">傳送給其他使用者的回音百分比。</span><span class="sxs-lookup"><span data-stu-id="66c18-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c18-310"><strong>有回音 （%） 的通話</strong></span><span class="sxs-lookup"><span data-stu-id="66c18-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="66c18-311">是</span><span class="sxs-lookup"><span data-stu-id="66c18-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="66c18-312">回音超出可接受的層級的總通話百分比。</span><span class="sxs-lookup"><span data-stu-id="66c18-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

