---
title: 'Lync Server 2013: Mcus 表格'
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
ms.openlocfilehash: ad3037f81ccfe2b54f464a3e84d34a97366a3bb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="2d18e-102">Lync Server 2013 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="2d18e-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d18e-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="2d18e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2d18e-104">Mcus 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="2d18e-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="2d18e-105">每一筆記錄會儲存一個會議服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2d18e-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="2d18e-106">這些可包括 IM 會議服務和電話語音會議服務 （前端伺服器執行為程序），和 Web 會議服務和 A / V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="2d18e-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d18e-107">欄</span><span class="sxs-lookup"><span data-stu-id="2d18e-107">Column</span></span></th>
<th><span data-ttu-id="2d18e-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="2d18e-108">Data Type</span></span></th>
<th><span data-ttu-id="2d18e-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="2d18e-109">Key/Index</span></span></th>
<th><span data-ttu-id="2d18e-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2d18e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d18e-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="2d18e-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="2d18e-112">int</span><span class="sxs-lookup"><span data-stu-id="2d18e-112">int</span></span></p></td>
<td><p><span data-ttu-id="2d18e-113">主要</span><span class="sxs-lookup"><span data-stu-id="2d18e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d18e-114">用於識別此會議伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2d18e-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d18e-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="2d18e-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2d18e-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2d18e-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d18e-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2d18e-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2d18e-118">inyint</span><span class="sxs-lookup"><span data-stu-id="2d18e-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="2d18e-119"> 外部</span><span class="sxs-lookup"><span data-stu-id="2d18e-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="2d18e-120">會議伺服器類型，例如 conf:chat （適用於 Im) 或 conf:audio-視訊。</span><span class="sxs-lookup"><span data-stu-id="2d18e-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="2d18e-121">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2d18e-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

