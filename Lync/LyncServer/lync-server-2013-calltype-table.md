---
title: Lync Server 2013： CallType 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d369243bd8083191d4956896acbdbc1c7e575bf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512910"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="2ee2e-102">Lync Server 2013 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="2ee2e-102">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee2e-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2ee2e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2ee2e-104">CallType 表格是儲存可能通話類型清單的靜態表格。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ee2e-105">欄</span><span class="sxs-lookup"><span data-stu-id="2ee2e-105">Column</span></span></th>
<th><span data-ttu-id="2ee2e-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="2ee2e-106">Data Type</span></span></th>
<th><span data-ttu-id="2ee2e-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="2ee2e-107">Key/Index</span></span></th>
<th><span data-ttu-id="2ee2e-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2ee2e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ee2e-109"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2ee2e-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ee2e-110">int</span><span class="sxs-lookup"><span data-stu-id="2ee2e-110">int</span></span></p></td>
<td><p><span data-ttu-id="2ee2e-111">主要</span><span class="sxs-lookup"><span data-stu-id="2ee2e-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ee2e-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="2ee2e-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ee2e-113">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="2ee2e-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ee2e-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="2ee2e-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ee2e-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="2ee2e-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="2ee2e-116">1–立即訊息</span><span class="sxs-lookup"><span data-stu-id="2ee2e-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="2ee2e-117">2--應用程式共用</span><span class="sxs-lookup"><span data-stu-id="2ee2e-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="2ee2e-118">3--音訊</span><span class="sxs-lookup"><span data-stu-id="2ee2e-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="2ee2e-119">4–音訊和影片</span><span class="sxs-lookup"><span data-stu-id="2ee2e-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="2ee2e-120">5–檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="2ee2e-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

