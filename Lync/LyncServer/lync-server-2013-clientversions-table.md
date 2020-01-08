---
title: Lync Server 2013：ClientVersions 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba578209ca6c22360da73c2317334ecf77da569
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="13b50-102">Lync Server 2013 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="13b50-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b50-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="13b50-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="13b50-104">ClientVersions 資料表是一個支援資料表，可儲存已參與在資料庫中記錄的會話的各種用戶端類型和版本清單。</span><span class="sxs-lookup"><span data-stu-id="13b50-104">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="13b50-105">資料表中的每一筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="13b50-105">Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13b50-106">左欄</span><span class="sxs-lookup"><span data-stu-id="13b50-106">Column</span></span></th>
<th><span data-ttu-id="13b50-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="13b50-107">Data Type</span></span></th>
<th><span data-ttu-id="13b50-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="13b50-108">Key/Index</span></span></th>
<th><span data-ttu-id="13b50-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="13b50-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13b50-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="13b50-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="13b50-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="13b50-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="13b50-112">首選</span><span class="sxs-lookup"><span data-stu-id="13b50-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="13b50-113">標識此用戶端類型與版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="13b50-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13b50-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="13b50-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="13b50-115"><strong>Nvarchar （256）</strong></span><span class="sxs-lookup"><span data-stu-id="13b50-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13b50-116">版本名稱。</span><span class="sxs-lookup"><span data-stu-id="13b50-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13b50-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="13b50-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="13b50-118">int</span><span class="sxs-lookup"><span data-stu-id="13b50-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13b50-119">指定會話中使用的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="13b50-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="13b50-120">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="13b50-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="13b50-121">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="13b50-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

