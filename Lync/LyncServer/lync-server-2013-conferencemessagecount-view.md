---
title: 'Lync Server 2013: ConferenceMessageCount 檢視'
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
ms.openlocfilehash: f94e824b18cab71fe1329ffcad1c836df6d46ebd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="7dd80-102">Lync Server 2013 中的 ConferenceMessageCount 檢視</span><span class="sxs-lookup"><span data-stu-id="7dd80-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd80-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="7dd80-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7dd80-104">ConferenceMessageCount 檢視儲存多少郵件傳送使用者所至會議的資訊。</span><span class="sxs-lookup"><span data-stu-id="7dd80-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="7dd80-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="7dd80-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7dd80-106">ConferenceMessageCount 檢視包含<A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails 檢視在 Lync Server 2013</A>中的欄的所有除了以下所列的欄。</span><span class="sxs-lookup"><span data-stu-id="7dd80-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7dd80-107">欄</span><span class="sxs-lookup"><span data-stu-id="7dd80-107">Column</span></span></th>
<th><span data-ttu-id="7dd80-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="7dd80-108">Data Type</span></span></th>
<th><span data-ttu-id="7dd80-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="7dd80-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7dd80-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7dd80-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd80-111">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7dd80-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7dd80-112">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="7dd80-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd80-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7dd80-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd80-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7dd80-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7dd80-115">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="7dd80-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="7dd80-116">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7dd80-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7dd80-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7dd80-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd80-118">唯一</span><span class="sxs-lookup"><span data-stu-id="7dd80-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7dd80-119">租用戶的使用者傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="7dd80-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="7dd80-120">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7dd80-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7dd80-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7dd80-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7dd80-122">smallint</span><span class="sxs-lookup"><span data-stu-id="7dd80-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="7dd80-123">會議工作階段期間使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="7dd80-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

