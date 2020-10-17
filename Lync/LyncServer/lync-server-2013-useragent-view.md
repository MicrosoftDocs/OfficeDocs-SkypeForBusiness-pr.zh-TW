---
title: Lync Server 2013： UserAgent view
description: Lync Server 2013： UserAgent view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc5ef2ec01b50f3714dca3690d0844286baaef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558859"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="74182-103">Lync Server 2013 中的 UserAgent 視圖</span><span class="sxs-lookup"><span data-stu-id="74182-103">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74182-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="74182-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="74182-105">UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。</span><span class="sxs-lookup"><span data-stu-id="74182-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="74182-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="74182-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74182-107">欄</span><span class="sxs-lookup"><span data-stu-id="74182-107">Column</span></span></th>
<th><span data-ttu-id="74182-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="74182-108">Data Type</span></span></th>
<th><span data-ttu-id="74182-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="74182-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74182-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="74182-110">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="74182-111">int</span><span class="sxs-lookup"><span data-stu-id="74182-111">int</span></span></p></td>
<td><p><span data-ttu-id="74182-112">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="74182-112">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74182-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="74182-113">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="74182-114">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="74182-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74182-115">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="74182-115">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74182-116">UAType</span><span class="sxs-lookup"><span data-stu-id="74182-116">UAType</span></span></p></td>
<td><p><span data-ttu-id="74182-117">Smallint</span><span class="sxs-lookup"><span data-stu-id="74182-117">smallint</span></span></p></td>
<td><p><span data-ttu-id="74182-118">使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="74182-118">Type of user agent.</span></span> <span data-ttu-id="74182-119">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="74182-119">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74182-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="74182-120">UACategory</span></span></p></td>
<td><p><span data-ttu-id="74182-121">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="74182-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74182-122">使用者代理所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="74182-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="74182-123">例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="74182-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

