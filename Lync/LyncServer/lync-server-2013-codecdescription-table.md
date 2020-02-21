---
title: 'Lync Server 2013: CodecDescription 表'
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
ms.openlocfilehash: c45300800ad83bbeee0d71abd1a38879f41c903d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="44370-102">Lync Server 2013 中的 CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="44370-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44370-103">_**主題上次修改日期：** 2012年-10-17_</span><span class="sxs-lookup"><span data-stu-id="44370-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="44370-104">CodecDescription 表格會將唯一的轉碼器識別碼對應至它們對應的轉碼器。</span><span class="sxs-lookup"><span data-stu-id="44370-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="44370-105">轉碼器可用來為數位訊號編碼以利傳輸與廣播，然後將它們解碼以進行播放。</span><span class="sxs-lookup"><span data-stu-id="44370-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="44370-106">Microsoft Lync Server 2013 中已導入此表格</span><span class="sxs-lookup"><span data-stu-id="44370-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44370-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="44370-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="44370-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="44370-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="44370-109"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="44370-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="44370-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="44370-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44370-111"><strong>Codecdescriptionkey 之</strong></span><span class="sxs-lookup"><span data-stu-id="44370-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="44370-112">smallint</span><span class="sxs-lookup"><span data-stu-id="44370-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="44370-113">主要</span><span class="sxs-lookup"><span data-stu-id="44370-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="44370-114">指派給轉碼器的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="44370-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44370-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="44370-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="44370-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="44370-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="44370-117">Unique</span><span class="sxs-lookup"><span data-stu-id="44370-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="44370-118">對應至 CodecDescriptionKey 之轉碼器的唯一說明。</span><span class="sxs-lookup"><span data-stu-id="44370-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

