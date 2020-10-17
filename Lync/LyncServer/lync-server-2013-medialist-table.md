---
title: Lync Server 2013： MediaList 表格
description: Lync Server 2013： MediaList 表格。
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
ms.openlocfilehash: 4e54535cd4a081657e7dcd59446cf65aaa3af7cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572069"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="01f3c-103">Lync Server 2013 中的 MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="01f3c-103">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f3c-104">_**主題上次修改日期：** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="01f3c-104">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="01f3c-105">MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。</span><span class="sxs-lookup"><span data-stu-id="01f3c-105">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f3c-106">欄</span><span class="sxs-lookup"><span data-stu-id="01f3c-106">Column</span></span></th>
<th><span data-ttu-id="01f3c-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="01f3c-107">Data Type</span></span></th>
<th><span data-ttu-id="01f3c-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="01f3c-108">Key/Index</span></span></th>
<th><span data-ttu-id="01f3c-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="01f3c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f3c-110"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="01f3c-110"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="01f3c-111">Tinyint</span><span class="sxs-lookup"><span data-stu-id="01f3c-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="01f3c-112">主要</span><span class="sxs-lookup"><span data-stu-id="01f3c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="01f3c-113">值：1-7</span><span class="sxs-lookup"><span data-stu-id="01f3c-113">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f3c-114"><strong>媒體</strong></span><span class="sxs-lookup"><span data-stu-id="01f3c-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="01f3c-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="01f3c-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01f3c-116">MediaID 和媒體值的靜態對應：</span><span class="sxs-lookup"><span data-stu-id="01f3c-116">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="01f3c-117">1– IM</span><span class="sxs-lookup"><span data-stu-id="01f3c-117">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="01f3c-118">2 – 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="01f3c-118">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="01f3c-119">3 – 遠端協助</span><span class="sxs-lookup"><span data-stu-id="01f3c-119">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="01f3c-120">4 – 應用程式共用</span><span class="sxs-lookup"><span data-stu-id="01f3c-120">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="01f3c-121">5–音訊</span><span class="sxs-lookup"><span data-stu-id="01f3c-121">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="01f3c-122">6–影片</span><span class="sxs-lookup"><span data-stu-id="01f3c-122">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="01f3c-123">7 – 應用程式邀請</span><span class="sxs-lookup"><span data-stu-id="01f3c-123">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="01f3c-124">若要嘗試判斷 SessionDetailsView LcsCDR 中的值的模態類型，您必須使用下列的聯接程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="01f3c-124">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

