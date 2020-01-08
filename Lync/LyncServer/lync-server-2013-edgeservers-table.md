---
title: Lync Server 2013：EdgeServers 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca947d710693590d6121242e79a6d29088432e0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="49ba5-102">Lync Server 2013 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="49ba5-102">EdgeServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ba5-103">_**主題上次修改日期：** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="49ba5-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="49ba5-104">EdgeServers 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="49ba5-104">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="49ba5-105">每個記錄都儲存在資料庫中有記錄的通話中所涉及之一台邊緣伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="49ba5-105">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49ba5-106">左欄</span><span class="sxs-lookup"><span data-stu-id="49ba5-106">Column</span></span></th>
<th><span data-ttu-id="49ba5-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="49ba5-107">Data Type</span></span></th>
<th><span data-ttu-id="49ba5-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="49ba5-108">Key/Index</span></span></th>
<th><span data-ttu-id="49ba5-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="49ba5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49ba5-110"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="49ba5-110"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="49ba5-111">int</span><span class="sxs-lookup"><span data-stu-id="49ba5-111">int</span></span></p></td>
<td><p><span data-ttu-id="49ba5-112">首選</span><span class="sxs-lookup"><span data-stu-id="49ba5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="49ba5-113">標識此 Edge 伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="49ba5-113">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ba5-114"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="49ba5-114"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="49ba5-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="49ba5-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="49ba5-116">Edge 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="49ba5-116">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

