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
ms.openlocfilehash: 06e250528a56c10a573c19181fddb1d9acee494d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499160"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="6fc1a-102">Lync Server 2013 中的 ClientVersions 視圖</span><span class="sxs-lookup"><span data-stu-id="6fc1a-102">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fc1a-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6fc1a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6fc1a-104">ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="6fc1a-105">視圖中的每一筆記錄都代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="6fc1a-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fc1a-107">某些欄可能會有多筆記錄。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fc1a-108">欄</span><span class="sxs-lookup"><span data-stu-id="6fc1a-108">Column</span></span></th>
<th><span data-ttu-id="6fc1a-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="6fc1a-109">Data Type</span></span></th>
<th><span data-ttu-id="6fc1a-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6fc1a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fc1a-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="6fc1a-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="6fc1a-112">int</span><span class="sxs-lookup"><span data-stu-id="6fc1a-112">int</span></span></p></td>
<td><p><span data-ttu-id="6fc1a-113">用於識別此用戶端類型及版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fc1a-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="6fc1a-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="6fc1a-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="6fc1a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6fc1a-116">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fc1a-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="6fc1a-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6fc1a-118">int</span><span class="sxs-lookup"><span data-stu-id="6fc1a-118">int</span></span></p></td>
<td><p><span data-ttu-id="6fc1a-119">用戶端的類型。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fc1a-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6fc1a-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6fc1a-121">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="6fc1a-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6fc1a-122">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-122">Category that the client belongs to.</span></span> <span data-ttu-id="6fc1a-123">例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="6fc1a-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

