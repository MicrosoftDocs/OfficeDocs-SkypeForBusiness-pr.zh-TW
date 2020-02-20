---
title: 'Lync Server 2013: Dialog 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fb3fd81eb9128dea5479868617bb429b271719
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="df681-102">Lync Server 2013 中的 dialog 表格</span><span class="sxs-lookup"><span data-stu-id="df681-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df681-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="df681-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="df681-104">Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="df681-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df681-105"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="df681-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="df681-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="df681-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="df681-107"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="df681-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="df681-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="df681-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df681-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="df681-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df681-110">datetime</span><span class="sxs-lookup"><span data-stu-id="df681-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="df681-111">主要</span><span class="sxs-lookup"><span data-stu-id="df681-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="df681-p101">卓越品質 (Quality of Excellence, QoE) 代理程式從發話者或受話者收到第一份報告的時間。其會與 SessionSeq 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="df681-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df681-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="df681-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="df681-115">int</span><span class="sxs-lookup"><span data-stu-id="df681-115">int</span></span></p></td>
<td><p><span data-ttu-id="df681-116">主要</span><span class="sxs-lookup"><span data-stu-id="df681-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="df681-117">當工作階段的 ConferenceDateTime 相同時，用來區分工作階段的序號。</span><span class="sxs-lookup"><span data-stu-id="df681-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df681-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="df681-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="df681-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="df681-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df681-120">全域唯一的對話方塊 ID。</span><span class="sxs-lookup"><span data-stu-id="df681-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df681-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="df681-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="df681-122">int</span><span class="sxs-lookup"><span data-stu-id="df681-122">int</span></span></p></td>
<td><p><span data-ttu-id="df681-123">index</span><span class="sxs-lookup"><span data-stu-id="df681-123">index</span></span></p></td>
<td><p><span data-ttu-id="df681-124">對話方塊 ID 的總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="df681-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

