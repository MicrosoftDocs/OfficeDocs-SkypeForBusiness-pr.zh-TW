---
title: Lync Server 2013：裝置報告
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
ms.openlocfilehash: dc453ca1e83d8077e67ef130ef7a83e03c138be2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="7e6d1-102">Lync Server 2013 中的裝置報表</span><span class="sxs-lookup"><span data-stu-id="7e6d1-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e6d1-103">_**主題上次修改日期：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="7e6d1-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="7e6d1-104">裝置報告可能更適合麥克風和喇叭報告;這是因為裝置報告會檢索與通話相關的度量標準（例如通話百分比、迴響及語音切換時間等），並依通話中使用的麥克風和喇叭分組。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="7e6d1-105">如果您對 IP 手機感興趣（通常也稱為 "裝置"），請改用[Lync Server 2013 中的 [IP 電話清點] 報告](lync-server-2013-ip-phone-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="7e6d1-106">裝置報告對於決定特定類型的裝置是否遇到大量低品質的呼叫（而不是其他人）而言，非常有用。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="7e6d1-107">反過來，這可能會影響購買新裝置或取代現有裝置時必須作出的任何決定。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="7e6d1-108">根據預設，裝置報告中顯示的資訊也是以在通話中使用的麥克風（擷取裝置）與喇叭/耳機（轉譯裝置）為基礎。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="7e6d1-109">例如，假設您有數個使用者使用下列擷取裝置及下列轉譯裝置：根據預設，裝置報告中顯示的資訊也是以在通話中使用的麥克風（擷取裝置）和喇叭/耳機（轉譯裝置）為基礎。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="7e6d1-110">例如，假設您有數個使用者使用下列擷取裝置及下列轉譯裝置：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="7e6d1-111">捕獲裝置--麥克風（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="7e6d1-112">轉譯裝置--耳機 Earphone （Microsoft LifeChat LX-3000）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="7e6d1-113">如果這些使用者總共進行254通話，您會在報表中看到如下所示的專案：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e6d1-114">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-114">Capture device</span></span></th>
<th><span data-ttu-id="7e6d1-115">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-115">Render device</span></span></th>
<th><span data-ttu-id="7e6d1-116">通話量</span><span class="sxs-lookup"><span data-stu-id="7e6d1-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-117">麥克風（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-118">耳機 Earphone （Microsoft LifeChat LX-3000）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-119">254</span><span class="sxs-lookup"><span data-stu-id="7e6d1-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e6d1-120">現在，假設您有多個使用者使用相同的捕獲裝置，而不是不同的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="7e6d1-121">在這種情況下，報表中將會有第二行專案，其中一個是 [擷取裝置] 與 [轉譯裝置] 的唯一組合：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e6d1-122">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-122">Capture device</span></span></th>
<th><span data-ttu-id="7e6d1-123">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-123">Render device</span></span></th>
<th><span data-ttu-id="7e6d1-124">通話量</span><span class="sxs-lookup"><span data-stu-id="7e6d1-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-125">麥克風（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-126">耳機 Earphone （Microsoft LifeChat LX-3000）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-127">254</span><span class="sxs-lookup"><span data-stu-id="7e6d1-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-128">麥克風（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-129">喇叭（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-130">319</span><span class="sxs-lookup"><span data-stu-id="7e6d1-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e6d1-131">如果您想要查看特定裝置（例如 SoundMAX 捕獲裝置）的合併總計（無論所使用的轉譯裝置為何），請從 [裝置類型] 下拉式清單中選取適當的選項（[捕獲裝置] 或 [轉譯裝置]）。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="7e6d1-132">如果您在這個範例中選取 [擷取裝置]，就會提供如下所示的輸出：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e6d1-133">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-133">Capture device</span></span></th>
<th><span data-ttu-id="7e6d1-134">通話量</span><span class="sxs-lookup"><span data-stu-id="7e6d1-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-135">麥克風（SoundMAX 整合式數位 HD 音訊）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-136">573</span><span class="sxs-lookup"><span data-stu-id="7e6d1-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="7e6d1-137">存取裝置報告</span><span class="sxs-lookup"><span data-stu-id="7e6d1-137">Accessing the Device Report</span></span>

<span data-ttu-id="7e6d1-138">裝置報告通常是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7e6d1-139">不過，如果您是[在 Lync Server 2013 中查看 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md)，您可以按一下下列其中一個度量，向下切入至特定裝置的裝置報告：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7e6d1-140">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-140">Capture Device</span></span>

  - <span data-ttu-id="7e6d1-141">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-141">Render Device</span></span>

<span data-ttu-id="7e6d1-142">在 [裝置] 報告中，您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7e6d1-143">通話量</span><span class="sxs-lookup"><span data-stu-id="7e6d1-143">Call volume</span></span>

  - <span data-ttu-id="7e6d1-144">通話百分比太差</span><span class="sxs-lookup"><span data-stu-id="7e6d1-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="7e6d1-145">充分利用裝置報告</span><span class="sxs-lookup"><span data-stu-id="7e6d1-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="7e6d1-146">在裝置名稱上時，裝置報告非常詳細;例如，假設您有下列捕獲裝置：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="7e6d1-147">Aastra 3002 麥克風（2-Aastra 3002）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="7e6d1-148">Aastra 3002 麥克風（3-Aastra 3002）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="7e6d1-149">Aastra 3002 麥克風（Aastra 3002）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="7e6d1-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="7e6d1-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="7e6d1-151">Aastra 6725ip 麥克風（10-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-152">Aastra 6725ip 麥克風（10-Aastra 6725ip）-V0</span><span class="sxs-lookup"><span data-stu-id="7e6d1-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7e6d1-153">Aastra 6725ip 麥克風（2-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-154">Aastra 6725ip 麥克風（3-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-155">Aastra 6725ip 麥克風（4-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-156">Aastra 6725ip 麥克風（5-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-157">Aastra 6725ip 麥克風（6-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-158">Aastra 6725ip 麥克風（7-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-159">Aastra 6725ip 麥克風（9-Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-160">Aastra 6725ip 麥克風（9-Aastra 6725ip）-V0</span><span class="sxs-lookup"><span data-stu-id="7e6d1-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7e6d1-161">Aastra 6725ip 麥克風（Aastra 6725ip）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="7e6d1-162">Aastra 6725ip 麥克風（Aastra 6725ip）-V0</span><span class="sxs-lookup"><span data-stu-id="7e6d1-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7e6d1-163">Aastra 6725ip 麥克風（USB 音訊裝置）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="7e6d1-164">Aastra 6725ip 麥克風（USB 音訊裝置）-V0</span><span class="sxs-lookup"><span data-stu-id="7e6d1-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e6d1-165">請記住，如果您執行的是 Lync Server 2013 的當地語系化版本，捕獲裝置名稱可能會不同。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="7e6d1-166">名為 Aastra 6725ip 麥克風的裝置（Aastra 6725ip）-美國英文的 V0 在法文或西班牙文中可能會有不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="7e6d1-167">您通常會想要該詳細資料層級;不過，在其他時間，您可能只對使用任何 Aastra 麥克風的通話數感興趣，不論型號為何。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="7e6d1-168">一種取得資訊的方法，例如，將裝置報告資料匯出至 Microsoft Excel，然後將該資料儲存到逗號分隔值檔案（例如，C：\\資料\\裝置\_Report .csv）。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="7e6d1-169">然後，您可以使用類似這些命令的一組命令來匯入。CSV 檔案至 Windows PowerShell，並傳回使用 Aastra 擷取裝置所進行的呼叫總數：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="7e6d1-170">這會傳回單一值，代表使用 Aastra 擷取裝置所進行的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="7e6d1-171">例如：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7e6d1-172">濾鏡</span><span class="sxs-lookup"><span data-stu-id="7e6d1-172">Filters</span></span>

<span data-ttu-id="7e6d1-173">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7e6d1-174">例如，裝置報告可讓您篩選呼叫類型（也就是呼叫用戶端通話）、電話會議或公用交換電話網絡（PSTN）呼叫等專案。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="7e6d1-175">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="7e6d1-176">在這種情況下，裝置會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7e6d1-177">下表列出可與裝置報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="7e6d1-178">裝置報表篩選</span><span class="sxs-lookup"><span data-stu-id="7e6d1-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e6d1-179">名稱</span><span class="sxs-lookup"><span data-stu-id="7e6d1-179">Name</span></span></th>
<th><span data-ttu-id="7e6d1-180">說明</span><span class="sxs-lookup"><span data-stu-id="7e6d1-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-181"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-182">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-182">Start date/time for the time range.</span></span> <span data-ttu-id="7e6d1-183">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-183">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7e6d1-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7e6d1-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e6d1-185">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-185">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7e6d1-186">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e6d1-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e6d1-187">7/7/2012</span></span></p>
<p><span data-ttu-id="7e6d1-188">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e6d1-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e6d1-189">7/3/2012</span></span></p>
<p><span data-ttu-id="7e6d1-190">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-191"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-192">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-192">End date/time for the time range.</span></span> <span data-ttu-id="7e6d1-193">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-193">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7e6d1-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7e6d1-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e6d1-195">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-195">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7e6d1-196">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-196">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e6d1-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e6d1-197">7/7/2012</span></span></p>
<p><span data-ttu-id="7e6d1-198">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e6d1-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e6d1-199">7/3/2012</span></span></p>
<p><span data-ttu-id="7e6d1-200">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-201"><strong>語音開關原因</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-202">為什麼必須將通話設為半雙工模式，才能避免回聲。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="7e6d1-203">在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="7e6d1-204">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-205">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-206">無</span><span class="sxs-lookup"><span data-stu-id="7e6d1-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-207">錯誤的時間戳記</span><span class="sxs-lookup"><span data-stu-id="7e6d1-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-208">回應</span><span class="sxs-lookup"><span data-stu-id="7e6d1-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-209">DNLP （動態非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-210">低複雜性</span><span class="sxs-lookup"><span data-stu-id="7e6d1-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-211">錯誤的裝置狀態</span><span class="sxs-lookup"><span data-stu-id="7e6d1-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-212">防 AEC 回應（聲音回聲取消）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-213"><strong>回顯原因</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-214">在通話中檢測到接受等級上方的迴響的原因。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="7e6d1-215">（在電訊中，echo 是音效的反射，當您向下 yell 到最下方時，您會聽到的相同現象。）選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-216">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-217">無</span><span class="sxs-lookup"><span data-stu-id="7e6d1-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-218">錯誤的時間戳記</span><span class="sxs-lookup"><span data-stu-id="7e6d1-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-219">防 AEC 回應（聲音回聲取消）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-220">ANLP （自我調整非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-221">DNLP （動態非線性處理器）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-222">麥克風剪輯</span><span class="sxs-lookup"><span data-stu-id="7e6d1-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-223"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-224">指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="7e6d1-225">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-226">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-227">用戶端通話</span><span class="sxs-lookup"><span data-stu-id="7e6d1-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-228">PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="7e6d1-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-229">電話會議</span><span class="sxs-lookup"><span data-stu-id="7e6d1-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-230"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-231">指出撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-231">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="7e6d1-232">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-232">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-233">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-234">內部</span><span class="sxs-lookup"><span data-stu-id="7e6d1-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-235">外來</span><span class="sxs-lookup"><span data-stu-id="7e6d1-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-236"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-237">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-237">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="7e6d1-238">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-238">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-239">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-240">有線</span><span class="sxs-lookup"><span data-stu-id="7e6d1-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-241">無線</span><span class="sxs-lookup"><span data-stu-id="7e6d1-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-242"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-243">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-243">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="7e6d1-244">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-244">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-245">同時</span><span class="sxs-lookup"><span data-stu-id="7e6d1-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-246">點對點</span><span class="sxs-lookup"><span data-stu-id="7e6d1-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-247">非 VPN</span><span class="sxs-lookup"><span data-stu-id="7e6d1-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-248"><strong>裝置類型</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-249">指出裝置類型。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-249">Indicates the type of device.</span></span> <span data-ttu-id="7e6d1-250">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-251">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-252">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="7e6d1-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7e6d1-253">捕獲/轉譯裝置配對</span><span class="sxs-lookup"><span data-stu-id="7e6d1-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-254"><strong>裝置名稱</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-255">捕獲或轉譯裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-255">Name of the capture or render device.</span></span> <span data-ttu-id="7e6d1-256">您可以輸入完整的裝置名稱或裝置名稱的任何部分。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="7e6d1-257">例如，若要尋找裝置麥克風（Microsoft LifeCam VX-1000），您可以輸入完整的裝置名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="7e6d1-258">麥克風（Microsoft LifeCam VX-1000.）</span><span class="sxs-lookup"><span data-stu-id="7e6d1-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="7e6d1-259">或者，您也可以只輸入部分名稱。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="7e6d1-260">例如：</span><span class="sxs-lookup"><span data-stu-id="7e6d1-260">For example:</span></span></p>
<p><span data-ttu-id="7e6d1-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="7e6d1-261">LifeCam</span></span></p>
<p><span data-ttu-id="7e6d1-262">請注意，前面的篩選會傳回任何在其名稱&quot;中&quot;的任何位置都包含字串 LifeCam 的裝置。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7e6d1-263">指標</span><span class="sxs-lookup"><span data-stu-id="7e6d1-263">Metrics</span></span>

<span data-ttu-id="7e6d1-264">下表列出裝置報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="7e6d1-265">裝置報表度量單位</span><span class="sxs-lookup"><span data-stu-id="7e6d1-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e6d1-266">名稱</span><span class="sxs-lookup"><span data-stu-id="7e6d1-266">Name</span></span></th>
<th><span data-ttu-id="7e6d1-267">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="7e6d1-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7e6d1-268">說明</span><span class="sxs-lookup"><span data-stu-id="7e6d1-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-269"><strong>捕獲裝置</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-270">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-271">用來傳送音訊的裝置（例如麥克風或網路攝像機）。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-272"><strong>轉譯裝置</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-273">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-274">用於接收音訊的裝置（例如，耳機或喇叭）。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-275"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-276">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-277">已發出的通話總次數。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-278"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-279">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-280">分類為&quot;不良的通話百分比。&quot;較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-281"><strong>唯一使用者</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-282">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-283">使用裝置的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-283">Unique users who used the device.</span></span> <span data-ttu-id="7e6d1-284">如果使用者使用的裝置13次，他或她要算作一個唯一的使用者，就與只使用裝置一次的使用者是一樣的。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-285"><strong>語音切換時間的比率</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-286">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-287">必須在半雙工模式下執行的通話百分比，才能防止回聲。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="7e6d1-288">在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-289"><strong>麥克風無法運作的比例</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-290">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-291">擷取裝置無法以可接受的層級運作的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="7e6d1-292">高值表示此通話的品質問題主要是由於擷取裝置無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-293"><strong>音箱無法運作的比例</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-294">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-295">在可接受的層級中，轉譯裝置無法運作的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="7e6d1-296">高值表示與通話的品質問題主要是由於轉譯裝置無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-297"><strong>使用語音開關進行通話（%）</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-298">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-299">必須放入半雙工模式的總通話百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="7e6d1-300">在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-301"><strong>回顯麥克風（%）</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-302">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-303">在麥克風捕獲資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="7e6d1-304">通常，耳機或話機的值較低，而喇叭或獨立喇叭的值則較高。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="7e6d1-305">對於支援板載音響回聲取消的裝置，高值表示迴響洩漏。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="7e6d1-306">對於其他裝置，此規格不應該用來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e6d1-307"><strong>迴響傳送（%）</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-308">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-309">傳送給其他使用者的迴響百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e6d1-310"><strong>使用迴響呼叫（%）</strong></span><span class="sxs-lookup"><span data-stu-id="7e6d1-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7e6d1-311">是</span><span class="sxs-lookup"><span data-stu-id="7e6d1-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="7e6d1-312">在迴響超過可接受的層級之呼叫總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

