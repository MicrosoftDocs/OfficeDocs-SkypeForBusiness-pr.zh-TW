---
title: Lync Server 2013： ConferenceMessageCount view
description: Lync Server 2013： ConferenceMessageCount view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561609"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="ab6e3-103">Lync Server 2013 中的 ConferenceMessageCount 視圖</span><span class="sxs-lookup"><span data-stu-id="ab6e3-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab6e3-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ab6e3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ab6e3-105">ConferenceMessageCount view 儲存使用者傳送給會議的郵件數目資訊。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="ab6e3-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab6e3-107">ConferenceMessageCount view 包含在 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab6e3-108">欄</span><span class="sxs-lookup"><span data-stu-id="ab6e3-108">Column</span></span></th>
<th><span data-ttu-id="ab6e3-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="ab6e3-109">Data Type</span></span></th>
<th><span data-ttu-id="ab6e3-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ab6e3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab6e3-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ab6e3-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ab6e3-112">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="ab6e3-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ab6e3-113">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab6e3-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ab6e3-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab6e3-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ab6e3-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab6e3-116">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="ab6e3-117">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab6e3-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ab6e3-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ab6e3-119">唯一</span><span class="sxs-lookup"><span data-stu-id="ab6e3-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ab6e3-120">傳送訊息之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="ab6e3-121">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab6e3-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ab6e3-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ab6e3-123">Smallint</span><span class="sxs-lookup"><span data-stu-id="ab6e3-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="ab6e3-124">在會議會話期間使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ab6e3-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

