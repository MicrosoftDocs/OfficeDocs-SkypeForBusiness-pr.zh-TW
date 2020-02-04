---
title: Lync Server 2013：ContentTypes 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf7ba9c9fb267e8c65c3ba672850c04eb95a459
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="41d5f-102">Lync Server 2013 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="41d5f-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d5f-103">_**主題上次修改日期：** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="41d5f-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="41d5f-104">主控資料表是一種支援表格，可儲存點對點工作階段和會議會話中所使用的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="41d5f-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="41d5f-105">資料表中的每一筆記錄代表一種內容類型。</span><span class="sxs-lookup"><span data-stu-id="41d5f-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d5f-106">左欄</span><span class="sxs-lookup"><span data-stu-id="41d5f-106">Column</span></span></th>
<th><span data-ttu-id="41d5f-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="41d5f-107">Data Type</span></span></th>
<th><span data-ttu-id="41d5f-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="41d5f-108">Key/Index</span></span></th>
<th><span data-ttu-id="41d5f-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="41d5f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d5f-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="41d5f-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="41d5f-111">int</span><span class="sxs-lookup"><span data-stu-id="41d5f-111">int</span></span></p></td>
<td><p><span data-ttu-id="41d5f-112">首選</span><span class="sxs-lookup"><span data-stu-id="41d5f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="41d5f-113">識別內容類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="41d5f-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d5f-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="41d5f-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="41d5f-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="41d5f-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="41d5f-116">內容類型名稱。</span><span class="sxs-lookup"><span data-stu-id="41d5f-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

