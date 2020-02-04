---
title: Lync Server 2013：MediaList 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="bea79-102">Lync Server 2013 中的 MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="bea79-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bea79-103">_**主題上次修改日期：** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="bea79-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="bea79-104">MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。</span><span class="sxs-lookup"><span data-stu-id="bea79-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bea79-105">左欄</span><span class="sxs-lookup"><span data-stu-id="bea79-105">Column</span></span></th>
<th><span data-ttu-id="bea79-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="bea79-106">Data Type</span></span></th>
<th><span data-ttu-id="bea79-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="bea79-107">Key/Index</span></span></th>
<th><span data-ttu-id="bea79-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="bea79-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bea79-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="bea79-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="bea79-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="bea79-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bea79-111">首選</span><span class="sxs-lookup"><span data-stu-id="bea79-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="bea79-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="bea79-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bea79-113"><strong>媒體</strong></span><span class="sxs-lookup"><span data-stu-id="bea79-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="bea79-114">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bea79-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bea79-115">MediaID 和媒體值的靜態對應：</span><span class="sxs-lookup"><span data-stu-id="bea79-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="bea79-116">1-IM</span><span class="sxs-lookup"><span data-stu-id="bea79-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="bea79-117">2-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="bea79-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="bea79-118">3-遠端協助</span><span class="sxs-lookup"><span data-stu-id="bea79-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="bea79-119">4–應用程式共用</span><span class="sxs-lookup"><span data-stu-id="bea79-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="bea79-120">5–音訊</span><span class="sxs-lookup"><span data-stu-id="bea79-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="bea79-121">6–影片</span><span class="sxs-lookup"><span data-stu-id="bea79-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="bea79-122">7– App 邀請</span><span class="sxs-lookup"><span data-stu-id="bea79-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bea79-123">如果您要嘗試判斷 LcsCDR 中的值的模態類型，則需要使用下列聯結程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="bea79-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

