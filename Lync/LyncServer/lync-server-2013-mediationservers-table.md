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
ms.openlocfilehash: 6e932163610b88a51352c1f97e2d0b8d9c773d2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="03315-102">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="03315-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03315-103">_**主題上次修改日期：** 2010年-11-06_</span><span class="sxs-lookup"><span data-stu-id="03315-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="03315-104">MediationServers 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="03315-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="03315-105">每一筆記錄資料庫中擁有記錄的通話中儲存的相關資訊的一部中繼伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="03315-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03315-106">欄</span><span class="sxs-lookup"><span data-stu-id="03315-106">Column</span></span></th>
<th><span data-ttu-id="03315-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="03315-107">Data Type</span></span></th>
<th><span data-ttu-id="03315-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="03315-108">Key/Index</span></span></th>
<th><span data-ttu-id="03315-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="03315-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03315-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="03315-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="03315-111">int</span><span class="sxs-lookup"><span data-stu-id="03315-111">int</span></span></p></td>
<td><p><span data-ttu-id="03315-112">主要</span><span class="sxs-lookup"><span data-stu-id="03315-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="03315-113">用於識別此中繼伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="03315-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03315-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="03315-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="03315-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03315-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="03315-116">中繼伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="03315-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

