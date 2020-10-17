---
title: Lync Server 2013： tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df687926940aa98f3bf803f9a991527f19fa58f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509440"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="567ce-102">Lync Server 2013 中的 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="567ce-102">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="567ce-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="567ce-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="567ce-104">tblComplianceFanout 包含處理符合性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="567ce-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="567ce-105">Columns</span><span class="sxs-lookup"><span data-stu-id="567ce-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="567ce-106">欄</span><span class="sxs-lookup"><span data-stu-id="567ce-106">Column</span></span></th>
<th><span data-ttu-id="567ce-107">類型</span><span class="sxs-lookup"><span data-stu-id="567ce-107">Type</span></span></th>
<th><span data-ttu-id="567ce-108">描述</span><span class="sxs-lookup"><span data-stu-id="567ce-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="567ce-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="567ce-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="567ce-110">int</span><span class="sxs-lookup"><span data-stu-id="567ce-110">int</span></span></p></td>
<td><p><span data-ttu-id="567ce-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="567ce-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="567ce-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="567ce-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="567ce-113">int</span><span class="sxs-lookup"><span data-stu-id="567ce-113">int</span></span></p></td>
<td><p><span data-ttu-id="567ce-114">與 tblServerIdentity.serverID table) 相對應的伺服器身分識別 (。</span><span class="sxs-lookup"><span data-stu-id="567ce-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="567ce-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="567ce-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="567ce-116">欄</span><span class="sxs-lookup"><span data-stu-id="567ce-116">Column</span></span></th>
<th><span data-ttu-id="567ce-117">描述</span><span class="sxs-lookup"><span data-stu-id="567ce-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="567ce-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="567ce-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="567ce-119">在 tblComplianceData.cmplEventID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="567ce-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

