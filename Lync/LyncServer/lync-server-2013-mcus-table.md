---
title: Lync Server 2013：Mcus 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 522c7babbda63c550679dab1eb8eb03114417169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="48658-102">Lync Server 2013 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="48658-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48658-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="48658-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="48658-104">Mcus 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="48658-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="48658-105">每筆記錄儲存一個會議服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="48658-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="48658-106">這些可能包括 IM 會議服務和電話會議服務（在前端伺服器上以進程的方式執行），以及網路會議服務和 A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="48658-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48658-107">左欄</span><span class="sxs-lookup"><span data-stu-id="48658-107">Column</span></span></th>
<th><span data-ttu-id="48658-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="48658-108">Data Type</span></span></th>
<th><span data-ttu-id="48658-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="48658-109">Key/Index</span></span></th>
<th><span data-ttu-id="48658-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="48658-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48658-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="48658-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="48658-112">int</span><span class="sxs-lookup"><span data-stu-id="48658-112">int</span></span></p></td>
<td><p><span data-ttu-id="48658-113">首選</span><span class="sxs-lookup"><span data-stu-id="48658-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="48658-114">標識此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="48658-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48658-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="48658-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="48658-116">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="48658-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48658-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="48658-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="48658-118">inyint</span><span class="sxs-lookup"><span data-stu-id="48658-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="48658-119"> 外</span><span class="sxs-lookup"><span data-stu-id="48658-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="48658-120">會議服務器類型，例如會議：聊天（適用于 Im）或會議：音訊影片。</span><span class="sxs-lookup"><span data-stu-id="48658-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="48658-121">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="48658-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

