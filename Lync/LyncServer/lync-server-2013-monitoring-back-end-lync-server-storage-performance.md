---
title: Lync Server 2013： 監控端 Lync Server 儲存體效能
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
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="0bbd2-102">監視後端 Lync Server 2013 儲存體效能</span><span class="sxs-lookup"><span data-stu-id="0bbd2-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bbd2-103">_**上次修改主題：** 2014年-05-02_</span><span class="sxs-lookup"><span data-stu-id="0bbd2-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="0bbd2-104">Lync Server 2013 後端資料庫是非常重要的 Lync Server 2013 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="0bbd2-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="0bbd2-105">我們建議您持續監控資料庫和各自的交易記錄，以協助確定 Lync Server 2013 back end 最佳狀態執行。</span><span class="sxs-lookup"><span data-stu-id="0bbd2-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="0bbd2-106">下表列出應監視以了解儲存效能的相關資訊的效能計數器。</span><span class="sxs-lookup"><span data-stu-id="0bbd2-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="0bbd2-107">這些計數器的基準值必須判斷第一次 （當系統在其正常負載） 若要了解效能變更，當負荷系統。</span><span class="sxs-lookup"><span data-stu-id="0bbd2-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="0bbd2-108">要監視的效能計數器</span><span class="sxs-lookup"><span data-stu-id="0bbd2-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bbd2-109">效能計數器</span><span class="sxs-lookup"><span data-stu-id="0bbd2-109">Performance Counter</span></span></th>
<th><span data-ttu-id="0bbd2-110">[比較基準臨界值</span><span class="sxs-lookup"><span data-stu-id="0bbd2-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bbd2-111">交易/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bbd2-112">交易/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bbd2-113">交易/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bbd2-114">記錄清除/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bbd2-115">記錄清除/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bbd2-116">記錄清除/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bbd2-117">磁碟傳輸/秒 （讀取 + 寫入）-RTC db</span><span class="sxs-lookup"><span data-stu-id="0bbd2-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bbd2-118">磁碟傳輸/秒-RTC 記錄檔</span><span class="sxs-lookup"><span data-stu-id="0bbd2-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bbd2-119">磁碟傳輸/秒-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="0bbd2-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bbd2-120">磁碟傳輸/秒-rtcdyn 記錄檔</span><span class="sxs-lookup"><span data-stu-id="0bbd2-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

