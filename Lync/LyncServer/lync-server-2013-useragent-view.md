---
title: Lync Server 2013： UserAgent view
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
ms.openlocfilehash: 828e81d028fb476362a91c4fa0ab83c5e2c34c20
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="755fb-102">Lync Server 2013 中的 [UserAgent] 視圖</span><span class="sxs-lookup"><span data-stu-id="755fb-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="755fb-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="755fb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="755fb-104">[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="755fb-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="755fb-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="755fb-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="755fb-106">左欄</span><span class="sxs-lookup"><span data-stu-id="755fb-106">Column</span></span></th>
<th><span data-ttu-id="755fb-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="755fb-107">Data Type</span></span></th>
<th><span data-ttu-id="755fb-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="755fb-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="755fb-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="755fb-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="755fb-110">int</span><span class="sxs-lookup"><span data-stu-id="755fb-110">int</span></span></p></td>
<td><p><span data-ttu-id="755fb-111">標識此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="755fb-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="755fb-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="755fb-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="755fb-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="755fb-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="755fb-114">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="755fb-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="755fb-115">UAType</span><span class="sxs-lookup"><span data-stu-id="755fb-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="755fb-116">Smallint</span><span class="sxs-lookup"><span data-stu-id="755fb-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="755fb-117">使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="755fb-117">Type of user agent.</span></span> <span data-ttu-id="755fb-118">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="755fb-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="755fb-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="755fb-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="755fb-120">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="755fb-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="755fb-121">使用者代理所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="755fb-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="755fb-122">例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="755fb-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

