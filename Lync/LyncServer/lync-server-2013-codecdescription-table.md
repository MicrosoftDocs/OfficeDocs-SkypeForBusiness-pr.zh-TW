---
title: Lync Server 2013： CodecDescription 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a407d8eeb1ad9e318ff2f960f8cb7d62b1e3a9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="8a543-102">Lync Server 2013 中的 CodecDescription 表格</span><span class="sxs-lookup"><span data-stu-id="8a543-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a543-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="8a543-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="8a543-104">CodecDescription 表格會將唯一的編解碼器識別碼對應至其相對應的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="8a543-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="8a543-105">編解碼器是用來編碼傳輸和廣播的數位信號，然後解碼這些信號以進行播放。</span><span class="sxs-lookup"><span data-stu-id="8a543-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="8a543-106">此表格是在 Microsoft Lync Server 2013 中推出</span><span class="sxs-lookup"><span data-stu-id="8a543-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a543-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8a543-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8a543-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8a543-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a543-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8a543-112">Smallint</span><span class="sxs-lookup"><span data-stu-id="8a543-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="8a543-113">首選</span><span class="sxs-lookup"><span data-stu-id="8a543-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8a543-114">指派給編解碼器的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="8a543-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a543-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="8a543-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="8a543-116">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="8a543-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a543-117">唯一</span><span class="sxs-lookup"><span data-stu-id="8a543-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="8a543-118">對應至 CodecDescriptionKey 的編解碼器的唯一描述。</span><span class="sxs-lookup"><span data-stu-id="8a543-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

