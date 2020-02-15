---
title: Lync Server 2013： 伺服器表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Servers table
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398223(v=OCS.15)
ms:contentKeyID: 48183487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a11c909ab64b8e93c01376df05e64bc694385c4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="servers-table-in-lync-server-2013"></a><span data-ttu-id="db1db-102">Lync Server 2013 中的伺服器表格</span><span class="sxs-lookup"><span data-stu-id="db1db-102">Servers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db1db-103">_**主題上次修改日期：** 2010年-11-05_</span><span class="sxs-lookup"><span data-stu-id="db1db-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="db1db-104">伺服器表格是一種支援資料表儲存的各種伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db1db-104">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="db1db-105">在資料表中的每一筆記錄代表一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="db1db-105">Each record in the table represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db1db-106">欄</span><span class="sxs-lookup"><span data-stu-id="db1db-106">Column</span></span></th>
<th><span data-ttu-id="db1db-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="db1db-107">Data Type</span></span></th>
<th><span data-ttu-id="db1db-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="db1db-108">Key/Index</span></span></th>
<th><span data-ttu-id="db1db-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="db1db-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db1db-110"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="db1db-110"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="db1db-111">int</span><span class="sxs-lookup"><span data-stu-id="db1db-111">int</span></span></p></td>
<td><p><span data-ttu-id="db1db-112">主要</span><span class="sxs-lookup"><span data-stu-id="db1db-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="db1db-113">用於識別此伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="db1db-113">Unique number identifying this server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db1db-114"><strong>ServerFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="db1db-114"><strong>ServerFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="db1db-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db1db-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="db1db-116">伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="db1db-116">Server FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

