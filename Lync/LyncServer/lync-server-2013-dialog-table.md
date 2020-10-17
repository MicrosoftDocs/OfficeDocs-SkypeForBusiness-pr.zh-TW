---
title: Lync Server 2013： Dialog 表格
description: Lync Server 2013： Dialog 表格。
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
ms.openlocfilehash: 7ae93b8ca9f1146b7dc164803f27cbeeadc66777
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559719"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="be89a-103">Lync Server 2013 中的對話方塊表格</span><span class="sxs-lookup"><span data-stu-id="be89a-103">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be89a-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="be89a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="be89a-105">Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="be89a-105">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be89a-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="be89a-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="be89a-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="be89a-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be89a-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="be89a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="be89a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="be89a-112">主要</span><span class="sxs-lookup"><span data-stu-id="be89a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="be89a-p101">卓越品質 (Quality of Excellence, QoE) 代理程式從發話者或受話者收到第一份報告的時間。其會與 SessionSeq 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="be89a-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be89a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="be89a-116">int</span><span class="sxs-lookup"><span data-stu-id="be89a-116">int</span></span></p></td>
<td><p><span data-ttu-id="be89a-117">主要</span><span class="sxs-lookup"><span data-stu-id="be89a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="be89a-118">當工作階段的 ConferenceDateTime 相同時，用來區分工作階段的序號。</span><span class="sxs-lookup"><span data-stu-id="be89a-118">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be89a-119"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-119"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="be89a-120">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="be89a-120">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="be89a-121">全域唯一的對話方塊 ID。</span><span class="sxs-lookup"><span data-stu-id="be89a-121">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be89a-122"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="be89a-122"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="be89a-123">int</span><span class="sxs-lookup"><span data-stu-id="be89a-123">int</span></span></p></td>
<td><p><span data-ttu-id="be89a-124">index</span><span class="sxs-lookup"><span data-stu-id="be89a-124">index</span></span></p></td>
<td><p><span data-ttu-id="be89a-125">對話方塊 ID 的總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="be89a-125">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

