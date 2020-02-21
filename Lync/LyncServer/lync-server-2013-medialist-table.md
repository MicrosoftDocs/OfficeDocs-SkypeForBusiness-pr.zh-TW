---
title: 'Lync Server 2013: MediaList 表格'
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
ms.openlocfilehash: 66a0e59d979c3356d244bb341fcdfabae5b7addc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="7de6a-102">Lync Server 2013 中的 mediaList 表格</span><span class="sxs-lookup"><span data-stu-id="7de6a-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7de6a-103">_**主題上次修改日期：** 2016年-07-12_</span><span class="sxs-lookup"><span data-stu-id="7de6a-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="7de6a-104">MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。</span><span class="sxs-lookup"><span data-stu-id="7de6a-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7de6a-105">欄</span><span class="sxs-lookup"><span data-stu-id="7de6a-105">Column</span></span></th>
<th><span data-ttu-id="7de6a-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="7de6a-106">Data Type</span></span></th>
<th><span data-ttu-id="7de6a-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="7de6a-107">Key/Index</span></span></th>
<th><span data-ttu-id="7de6a-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="7de6a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7de6a-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="7de6a-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="7de6a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7de6a-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7de6a-111">主要</span><span class="sxs-lookup"><span data-stu-id="7de6a-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="7de6a-112">值： 1-7</span><span class="sxs-lookup"><span data-stu-id="7de6a-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7de6a-113"><strong>媒體業</strong></span><span class="sxs-lookup"><span data-stu-id="7de6a-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="7de6a-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7de6a-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7de6a-115">靜態 MediaID 和媒體值的對應：</span><span class="sxs-lookup"><span data-stu-id="7de6a-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="7de6a-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="7de6a-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="7de6a-117">2 – 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="7de6a-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="7de6a-118">3 – 遠端協助</span><span class="sxs-lookup"><span data-stu-id="7de6a-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="7de6a-119">4 – 應用程式共用</span><span class="sxs-lookup"><span data-stu-id="7de6a-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="7de6a-120">5 – 音訊</span><span class="sxs-lookup"><span data-stu-id="7de6a-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="7de6a-121">6 – 影片</span><span class="sxs-lookup"><span data-stu-id="7de6a-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="7de6a-122">7 – 應用程式邀請</span><span class="sxs-lookup"><span data-stu-id="7de6a-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7de6a-123">如果您嘗試判斷 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式類型，您需要使用下列加入程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="7de6a-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

