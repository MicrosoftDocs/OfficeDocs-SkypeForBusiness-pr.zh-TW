---
title: Lync Server 2013： tblActivePeers
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
ms.openlocfilehash: c49ddc7a1355e7108f1bcb9c13394dd3305190c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509550"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="3eb64-102">Lync Server 2013 中的 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="3eb64-102">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb64-103">_**主題上次修改日期：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="3eb64-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="3eb64-104">tblActivePeers 包含聊天服務之間目前的對等連線。</span><span class="sxs-lookup"><span data-stu-id="3eb64-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="3eb64-105">Columns</span><span class="sxs-lookup"><span data-stu-id="3eb64-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb64-106">欄</span><span class="sxs-lookup"><span data-stu-id="3eb64-106">Column</span></span></th>
<th><span data-ttu-id="3eb64-107">類型</span><span class="sxs-lookup"><span data-stu-id="3eb64-107">Type</span></span></th>
<th><span data-ttu-id="3eb64-108">描述</span><span class="sxs-lookup"><span data-stu-id="3eb64-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb64-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="3eb64-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="3eb64-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="3eb64-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3eb64-111">張貼專案之伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3eb64-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb64-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="3eb64-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="3eb64-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="3eb64-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3eb64-114">過帳伺服器連線的對等識別碼。</span><span class="sxs-lookup"><span data-stu-id="3eb64-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3eb64-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="3eb64-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb64-116">欄</span><span class="sxs-lookup"><span data-stu-id="3eb64-116">Column</span></span></th>
<th><span data-ttu-id="3eb64-117">描述</span><span class="sxs-lookup"><span data-stu-id="3eb64-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb64-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="3eb64-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="3eb64-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="3eb64-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb64-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="3eb64-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="3eb64-121">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="3eb64-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb64-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="3eb64-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="3eb64-123">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="3eb64-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

