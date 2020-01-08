---
title: Lync Server 2013：Dialog 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="506f7-102">Lync Server 2013 中的 Dialog 表格</span><span class="sxs-lookup"><span data-stu-id="506f7-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="506f7-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="506f7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="506f7-104">對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定（SIP）] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="506f7-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="506f7-105"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="506f7-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="506f7-107"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="506f7-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="506f7-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="506f7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="506f7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="506f7-111">首選</span><span class="sxs-lookup"><span data-stu-id="506f7-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="506f7-112">優質（QoE）代理程式從來電者或被叫方接收到第一個報告的時間。</span><span class="sxs-lookup"><span data-stu-id="506f7-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="506f7-113">與 SessionSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="506f7-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506f7-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="506f7-115">int</span><span class="sxs-lookup"><span data-stu-id="506f7-115">int</span></span></p></td>
<td><p><span data-ttu-id="506f7-116">首選</span><span class="sxs-lookup"><span data-stu-id="506f7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="506f7-117">[順序編號] 可在有相同 ConferenceDateTime 的情況下區分會話。</span><span class="sxs-lookup"><span data-stu-id="506f7-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="506f7-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="506f7-119">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="506f7-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="506f7-120">全域唯一的對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="506f7-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506f7-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="506f7-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="506f7-122">int</span><span class="sxs-lookup"><span data-stu-id="506f7-122">int</span></span></p></td>
<td><p><span data-ttu-id="506f7-123">index</span><span class="sxs-lookup"><span data-stu-id="506f7-123">index</span></span></p></td>
<td><p><span data-ttu-id="506f7-124">對話方塊識別碼的校驗和。</span><span class="sxs-lookup"><span data-stu-id="506f7-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

