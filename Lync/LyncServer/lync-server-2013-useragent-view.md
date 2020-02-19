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
ms.openlocfilehash: c30b8e227b55207efe33abb4b6294082660c1f07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="4088f-102">Lync Server 2013 中的 UserAgent 檢視</span><span class="sxs-lookup"><span data-stu-id="4088f-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4088f-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="4088f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4088f-104">UserAgent 檢視儲存具有已在資料庫中擁有記錄的工作階段相關的使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4088f-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="4088f-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="4088f-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4088f-106">欄</span><span class="sxs-lookup"><span data-stu-id="4088f-106">Column</span></span></th>
<th><span data-ttu-id="4088f-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="4088f-107">Data Type</span></span></th>
<th><span data-ttu-id="4088f-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4088f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4088f-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="4088f-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="4088f-110">int</span><span class="sxs-lookup"><span data-stu-id="4088f-110">int</span></span></p></td>
<td><p><span data-ttu-id="4088f-111">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4088f-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4088f-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="4088f-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="4088f-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4088f-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4088f-114">使用者代理字串。</span><span class="sxs-lookup"><span data-stu-id="4088f-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4088f-115">UAType</span><span class="sxs-lookup"><span data-stu-id="4088f-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="4088f-116">smallint</span><span class="sxs-lookup"><span data-stu-id="4088f-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="4088f-117">使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="4088f-117">Type of user agent.</span></span> <span data-ttu-id="4088f-118">請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4088f-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4088f-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="4088f-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="4088f-120">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="4088f-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4088f-121">使用者代理程式所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="4088f-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="4088f-122">例如，使用者代理程式 Conferencing_Attendant_1.0 屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="4088f-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

