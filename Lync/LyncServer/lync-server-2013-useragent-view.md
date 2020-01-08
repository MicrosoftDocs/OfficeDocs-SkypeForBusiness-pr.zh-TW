---
title: Lync Server 2013： UserAgent view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="1336a-102">Lync Server 2013 中的 [UserAgent] 視圖</span><span class="sxs-lookup"><span data-stu-id="1336a-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1336a-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1336a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1336a-104">[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1336a-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="1336a-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="1336a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1336a-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1336a-106">Column</span></span></th>
<th><span data-ttu-id="1336a-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="1336a-107">Data Type</span></span></th>
<th><span data-ttu-id="1336a-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1336a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1336a-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="1336a-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="1336a-110">int</span><span class="sxs-lookup"><span data-stu-id="1336a-110">int</span></span></p></td>
<td><p><span data-ttu-id="1336a-111">標識此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="1336a-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1336a-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="1336a-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="1336a-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1336a-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1336a-114">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="1336a-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1336a-115">UAType</span><span class="sxs-lookup"><span data-stu-id="1336a-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="1336a-116">Smallint</span><span class="sxs-lookup"><span data-stu-id="1336a-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="1336a-117">使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="1336a-117">Type of user agent.</span></span> <span data-ttu-id="1336a-118">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="1336a-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1336a-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="1336a-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="1336a-120">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="1336a-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1336a-121">使用者代理所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="1336a-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="1336a-122">例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="1336a-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

