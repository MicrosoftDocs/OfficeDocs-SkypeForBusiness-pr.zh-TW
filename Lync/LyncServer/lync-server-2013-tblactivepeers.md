---
title: Lync Server 2013： tblActivePeers
description: Lync Server 2013： tblActivePeers。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f274f82a280883e38e8e02409305982b64c18e4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573739"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="84c43-103">Lync Server 2013 中的 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="84c43-103">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84c43-104">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="84c43-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="84c43-105">tblActivePeers 包含聊天服務之間目前的對等連線。</span><span class="sxs-lookup"><span data-stu-id="84c43-105">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="84c43-106">Columns</span><span class="sxs-lookup"><span data-stu-id="84c43-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84c43-107">欄</span><span class="sxs-lookup"><span data-stu-id="84c43-107">Column</span></span></th>
<th><span data-ttu-id="84c43-108">類型</span><span class="sxs-lookup"><span data-stu-id="84c43-108">Type</span></span></th>
<th><span data-ttu-id="84c43-109">描述</span><span class="sxs-lookup"><span data-stu-id="84c43-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84c43-110">aplServerID</span><span class="sxs-lookup"><span data-stu-id="84c43-110">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="84c43-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="84c43-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="84c43-112">張貼專案之伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="84c43-112">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84c43-113">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="84c43-113">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="84c43-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="84c43-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="84c43-115">過帳伺服器連線的對等識別碼。</span><span class="sxs-lookup"><span data-stu-id="84c43-115">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="84c43-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="84c43-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84c43-117">欄</span><span class="sxs-lookup"><span data-stu-id="84c43-117">Column</span></span></th>
<th><span data-ttu-id="84c43-118">描述</span><span class="sxs-lookup"><span data-stu-id="84c43-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84c43-119">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="84c43-119">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="84c43-120">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="84c43-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84c43-121">aplServerID</span><span class="sxs-lookup"><span data-stu-id="84c43-121">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="84c43-122">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="84c43-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84c43-123">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="84c43-123">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="84c43-124">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="84c43-124">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

