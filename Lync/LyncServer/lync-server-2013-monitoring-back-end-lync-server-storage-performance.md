---
title: Lync Server 2013：監控後端 Lync Server 儲存效能
description: Lync Server 2013：監控後端 Lync 伺服器儲存效能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7501418d3589b941b7e92d2b414492c1d27a3ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562069"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="23213-103">監視後端 Lync Server 2013 儲存效能</span><span class="sxs-lookup"><span data-stu-id="23213-103">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23213-104">_**主題上次修改日期：** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="23213-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="23213-105">Lync Server 2013 後端資料庫是 Lync Server 2013 部署中非常重要的部分。</span><span class="sxs-lookup"><span data-stu-id="23213-105">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="23213-106">我們建議您不斷監控資料庫和各自的交易記錄，以協助確保 Lync Server 2013 後端的執行效果最佳。</span><span class="sxs-lookup"><span data-stu-id="23213-106">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="23213-107">下表識別應監控的效能計數器，以瞭解儲存效能的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="23213-107">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="23213-108">當系統處於其正常的負載) 時，必須先判斷這些計數器的比較基準值，以瞭解系統負載壓力下的效能變更時 (。</span><span class="sxs-lookup"><span data-stu-id="23213-108">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="23213-109">要監視的效能計數器</span><span class="sxs-lookup"><span data-stu-id="23213-109">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23213-110">效能計數器</span><span class="sxs-lookup"><span data-stu-id="23213-110">Performance Counter</span></span></th>
<th><span data-ttu-id="23213-111">基準閾值</span><span class="sxs-lookup"><span data-stu-id="23213-111">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23213-112">每秒交易 (RTC) </span><span class="sxs-lookup"><span data-stu-id="23213-112">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23213-113">每秒交易 (rtcdyn) </span><span class="sxs-lookup"><span data-stu-id="23213-113">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23213-114">每秒交易 (tempdb) </span><span class="sxs-lookup"><span data-stu-id="23213-114">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23213-115"> (RTC) 的記錄檔刷新次數/秒</span><span class="sxs-lookup"><span data-stu-id="23213-115">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23213-116">記錄檔刷新次數/秒 (rtcdyn) </span><span class="sxs-lookup"><span data-stu-id="23213-116">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23213-117">記錄檔刷新次數/秒 (tempdb) </span><span class="sxs-lookup"><span data-stu-id="23213-117">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23213-118">磁片傳輸/秒 (讀取 + 寫入) RTC db</span><span class="sxs-lookup"><span data-stu-id="23213-118">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23213-119">磁片傳輸/秒-RTC 記錄</span><span class="sxs-lookup"><span data-stu-id="23213-119">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23213-120">磁片傳輸/秒-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="23213-120">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23213-121">磁片傳輸/秒-rtcdyn 記錄</span><span class="sxs-lookup"><span data-stu-id="23213-121">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

