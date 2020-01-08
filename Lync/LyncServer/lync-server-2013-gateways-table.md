---
title: Lync Server 2013：Gateways 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f26a45d992d716b94cb7353f813c038272b132
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="b82de-102">Lync Server 2013 中的 Gateways 表格</span><span class="sxs-lookup"><span data-stu-id="b82de-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b82de-103">_**主題上次修改日期：** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="b82de-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="b82de-104">[閘道] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="b82de-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="b82de-105">每個記錄都儲存一個閘道的相關資訊，這些資訊包含在資料庫中有記錄的公用交換電話網絡（PSTN）通話中。</span><span class="sxs-lookup"><span data-stu-id="b82de-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b82de-106">左欄</span><span class="sxs-lookup"><span data-stu-id="b82de-106">Column</span></span></th>
<th><span data-ttu-id="b82de-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="b82de-107">Data Type</span></span></th>
<th><span data-ttu-id="b82de-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="b82de-108">Key/Index</span></span></th>
<th><span data-ttu-id="b82de-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b82de-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b82de-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b82de-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b82de-111">int</span><span class="sxs-lookup"><span data-stu-id="b82de-111">int</span></span></p></td>
<td><p><span data-ttu-id="b82de-112">首選</span><span class="sxs-lookup"><span data-stu-id="b82de-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b82de-113">識別此閘道的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="b82de-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b82de-114"><strong>關</strong></span><span class="sxs-lookup"><span data-stu-id="b82de-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b82de-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="b82de-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b82de-116">閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="b82de-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

