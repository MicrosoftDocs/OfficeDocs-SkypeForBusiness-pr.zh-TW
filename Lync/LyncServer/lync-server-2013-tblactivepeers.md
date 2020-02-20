---
title: 'Lync Server 2013: tblActivePeers'
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
ms.openlocfilehash: 2ad7e0cff95cde5be9f869c59305c05a657f799f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="9ffad-102">Lync Server 2013 中的 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="9ffad-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ffad-103">_**主題上次修改日期：** 2012年-06-29_</span><span class="sxs-lookup"><span data-stu-id="9ffad-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="9ffad-104">tblActivePeers 包含聊天服務之間的目前端對端連線。</span><span class="sxs-lookup"><span data-stu-id="9ffad-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="9ffad-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9ffad-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ffad-106">欄</span><span class="sxs-lookup"><span data-stu-id="9ffad-106">Column</span></span></th>
<th><span data-ttu-id="9ffad-107">類型	</span><span class="sxs-lookup"><span data-stu-id="9ffad-107">Type</span></span></th>
<th><span data-ttu-id="9ffad-108">描述</span><span class="sxs-lookup"><span data-stu-id="9ffad-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ffad-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9ffad-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9ffad-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9ffad-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9ffad-111">張貼項目之伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9ffad-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ffad-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9ffad-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9ffad-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9ffad-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9ffad-114">張貼伺服器連線到對等的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9ffad-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9ffad-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="9ffad-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ffad-116">欄</span><span class="sxs-lookup"><span data-stu-id="9ffad-116">Column</span></span></th>
<th><span data-ttu-id="9ffad-117">描述</span><span class="sxs-lookup"><span data-stu-id="9ffad-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ffad-118">&lt;aplServerID aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="9ffad-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9ffad-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9ffad-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ffad-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9ffad-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9ffad-121">在 tblServerIdentity.serverID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9ffad-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ffad-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9ffad-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9ffad-123">在 tblServerIdentity.serverID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9ffad-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

