---
title: Lync Server 2013： ConferenceMessageCount view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0324c9913a607057c4e1cd161a9040b83d6bd29b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="7ff13-102">Lync Server 2013 中的 [ConferenceMessageCount] 視圖</span><span class="sxs-lookup"><span data-stu-id="7ff13-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ff13-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7ff13-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7ff13-104">[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7ff13-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="7ff13-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="7ff13-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ff13-106">[ConferenceMessageCount] 視圖會包含 [ <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013</A> ] 的 [ConferenceSessionDetails] 視圖中的所有資料行，以及下列所列的欄。</span><span class="sxs-lookup"><span data-stu-id="7ff13-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ff13-107">左欄</span><span class="sxs-lookup"><span data-stu-id="7ff13-107">Column</span></span></th>
<th><span data-ttu-id="7ff13-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="7ff13-108">Data Type</span></span></th>
<th><span data-ttu-id="7ff13-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="7ff13-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ff13-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7ff13-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff13-111">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="7ff13-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7ff13-112">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="7ff13-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff13-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7ff13-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff13-114">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7ff13-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7ff13-115">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="7ff13-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="7ff13-116">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="7ff13-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff13-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7ff13-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff13-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7ff13-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7ff13-119">傳送訊息的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="7ff13-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="7ff13-120">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="7ff13-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff13-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7ff13-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff13-122">Smallint</span><span class="sxs-lookup"><span data-stu-id="7ff13-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="7ff13-123">使用者在會議會話期間傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="7ff13-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

