---
title: 'Lync Server 2013: Gateways 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efb730e06d9ce74d8f4e7c3c3e1dbf507af2ba1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="b534c-102">Lync Server 2013 中的 gateways 表格</span><span class="sxs-lookup"><span data-stu-id="b534c-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b534c-103">_**主題上次修改日期：** 2010年-11-05_</span><span class="sxs-lookup"><span data-stu-id="b534c-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="b534c-104">Gateways 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="b534c-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="b534c-105">每一筆記錄在資料庫中擁有記錄的公用交換的電話網路 (PSTN) 通話中儲存一個閘道所涉及的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b534c-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b534c-106">欄</span><span class="sxs-lookup"><span data-stu-id="b534c-106">Column</span></span></th>
<th><span data-ttu-id="b534c-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="b534c-107">Data Type</span></span></th>
<th><span data-ttu-id="b534c-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="b534c-108">Key/Index</span></span></th>
<th><span data-ttu-id="b534c-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b534c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b534c-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b534c-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b534c-111">int</span><span class="sxs-lookup"><span data-stu-id="b534c-111">int</span></span></p></td>
<td><p><span data-ttu-id="b534c-112">主要</span><span class="sxs-lookup"><span data-stu-id="b534c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b534c-113">用於識別此閘道的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="b534c-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b534c-114"><strong>閘道</strong></span><span class="sxs-lookup"><span data-stu-id="b534c-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b534c-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b534c-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b534c-116">閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="b534c-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

