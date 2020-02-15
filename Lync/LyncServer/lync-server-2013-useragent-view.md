---
title: 'Lync Server 2013: UserAgent 檢視'
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
ms.openlocfilehash: 7b82d8a03f159aa1c99d53dd06a0811847f77b12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="dbb0e-102">Lync Server 2013 中的 UserAgent 檢視</span><span class="sxs-lookup"><span data-stu-id="dbb0e-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbb0e-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="dbb0e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="dbb0e-104">UserAgent 檢視儲存具有已在資料庫中擁有記錄的工作階段相關的使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="dbb0e-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbb0e-106">欄</span><span class="sxs-lookup"><span data-stu-id="dbb0e-106">Column</span></span></th>
<th><span data-ttu-id="dbb0e-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="dbb0e-107">Data Type</span></span></th>
<th><span data-ttu-id="dbb0e-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="dbb0e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbb0e-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="dbb0e-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-110">int</span><span class="sxs-lookup"><span data-stu-id="dbb0e-110">int</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-111">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb0e-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="dbb0e-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dbb0e-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-114">使用者代理字串。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb0e-115">UAType</span><span class="sxs-lookup"><span data-stu-id="dbb0e-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-116">smallint</span><span class="sxs-lookup"><span data-stu-id="dbb0e-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-117">使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-117">Type of user agent.</span></span> <span data-ttu-id="dbb0e-118">請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb0e-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="dbb0e-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-120">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="dbb0e-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dbb0e-121">使用者代理程式所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="dbb0e-122">例如，使用者代理程式 Conferencing_Attendant_1.0 屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="dbb0e-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

