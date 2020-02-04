---
title: Lync Server 2013： ClientVersions view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fd25da49e8a3b6ad7838ff27a4472e711b97421
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="4ddbf-102">Lync Server 2013 中的 [ClientVersions] 視圖</span><span class="sxs-lookup"><span data-stu-id="4ddbf-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ddbf-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4ddbf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4ddbf-104">ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4ddbf-105">該視圖中的每一筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="4ddbf-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ddbf-107">某些欄可能有多個記錄。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ddbf-108">左欄</span><span class="sxs-lookup"><span data-stu-id="4ddbf-108">Column</span></span></th>
<th><span data-ttu-id="4ddbf-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="4ddbf-109">Data Type</span></span></th>
<th><span data-ttu-id="4ddbf-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4ddbf-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ddbf-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4ddbf-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddbf-112">int</span><span class="sxs-lookup"><span data-stu-id="4ddbf-112">int</span></span></p></td>
<td><p><span data-ttu-id="4ddbf-113">標識此用戶端類型與版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddbf-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="4ddbf-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddbf-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="4ddbf-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4ddbf-116">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ddbf-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="4ddbf-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddbf-118">int</span><span class="sxs-lookup"><span data-stu-id="4ddbf-118">int</span></span></p></td>
<td><p><span data-ttu-id="4ddbf-119">用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ddbf-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4ddbf-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4ddbf-121">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="4ddbf-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4ddbf-122">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-122">Category that the client belongs to.</span></span> <span data-ttu-id="4ddbf-123">例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="4ddbf-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

