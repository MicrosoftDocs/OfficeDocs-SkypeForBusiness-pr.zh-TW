---
title: 'Lync Server 2013: ContentTypes 表格'
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
ms.openlocfilehash: 084a02c9add6b383d6099073992f27d8955a66d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="b7a8b-102">Lync Server 2013 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="b7a8b-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7a8b-103">_**主題上次修改日期：** 2010年-11-07_</span><span class="sxs-lookup"><span data-stu-id="b7a8b-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="b7a8b-104">ContentTypes 表格是一種支援資料表儲存的端對端工作階段和會議工作階段中所使用的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="b7a8b-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="b7a8b-105">在資料表中的每一筆記錄代表一種內容類型。</span><span class="sxs-lookup"><span data-stu-id="b7a8b-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7a8b-106">欄</span><span class="sxs-lookup"><span data-stu-id="b7a8b-106">Column</span></span></th>
<th><span data-ttu-id="b7a8b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="b7a8b-107">Data Type</span></span></th>
<th><span data-ttu-id="b7a8b-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="b7a8b-108">Key/Index</span></span></th>
<th><span data-ttu-id="b7a8b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b7a8b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7a8b-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="b7a8b-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b7a8b-111">int</span><span class="sxs-lookup"><span data-stu-id="b7a8b-111">int</span></span></p></td>
<td><p><span data-ttu-id="b7a8b-112">主要</span><span class="sxs-lookup"><span data-stu-id="b7a8b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b7a8b-113">識別內容類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="b7a8b-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7a8b-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b7a8b-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b7a8b-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7a8b-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="b7a8b-116">內容類型名稱。</span><span class="sxs-lookup"><span data-stu-id="b7a8b-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

