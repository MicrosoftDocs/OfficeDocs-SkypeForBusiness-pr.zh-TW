---
title: 'Lync Server 2013: MediationServers 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5d8e9b1538608609137f5bfd00b18ed0452fea7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="4f818-102">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="4f818-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f818-103">_**主題上次修改日期：** 2010年-11-06_</span><span class="sxs-lookup"><span data-stu-id="4f818-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="4f818-104">MediationServers 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="4f818-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="4f818-105">每一筆記錄資料庫中擁有記錄的通話中儲存的相關資訊的一部中繼伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4f818-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f818-106">欄</span><span class="sxs-lookup"><span data-stu-id="4f818-106">Column</span></span></th>
<th><span data-ttu-id="4f818-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="4f818-107">Data Type</span></span></th>
<th><span data-ttu-id="4f818-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="4f818-108">Key/Index</span></span></th>
<th><span data-ttu-id="4f818-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4f818-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f818-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4f818-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f818-111">int</span><span class="sxs-lookup"><span data-stu-id="4f818-111">int</span></span></p></td>
<td><p><span data-ttu-id="4f818-112">主要</span><span class="sxs-lookup"><span data-stu-id="4f818-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f818-113">用於識別此中繼伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4f818-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f818-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="4f818-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4f818-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f818-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f818-116">中繼伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="4f818-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

