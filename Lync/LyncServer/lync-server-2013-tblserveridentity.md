---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d6de094f9786cc5d6bb3b25635cc54a290851e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="f587d-102">tblServerIdentity 在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f587d-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f587d-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="f587d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f587d-104">tblServerIdentity 包含 Persistent Chat Server 集區中的作用中的聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="f587d-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="f587d-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f587d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f587d-106">欄</span><span class="sxs-lookup"><span data-stu-id="f587d-106">Column</span></span></th>
<th><span data-ttu-id="f587d-107">類型	</span><span class="sxs-lookup"><span data-stu-id="f587d-107">Type</span></span></th>
<th><span data-ttu-id="f587d-108">描述</span><span class="sxs-lookup"><span data-stu-id="f587d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f587d-109">serverID</span><span class="sxs-lookup"><span data-stu-id="f587d-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="f587d-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f587d-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f587d-111">伺服器識別碼。</span><span class="sxs-lookup"><span data-stu-id="f587d-111">Server ID.</span></span> <span data-ttu-id="f587d-112">從中央管理存放區，會對應至執行個體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f587d-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f587d-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="f587d-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="f587d-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="f587d-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f587d-115">使用 Windows Communication Foundation 位址的伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="f587d-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f587d-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="f587d-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="f587d-117">datetime</span><span class="sxs-lookup"><span data-stu-id="f587d-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="f587d-118">通道伺服器更新此列以證明其為執行中的最新時間。</span><span class="sxs-lookup"><span data-stu-id="f587d-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f587d-119">索引鍵</span><span class="sxs-lookup"><span data-stu-id="f587d-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f587d-120">欄</span><span class="sxs-lookup"><span data-stu-id="f587d-120">Column</span></span></th>
<th><span data-ttu-id="f587d-121">描述</span><span class="sxs-lookup"><span data-stu-id="f587d-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f587d-122">serverID</span><span class="sxs-lookup"><span data-stu-id="f587d-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="f587d-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f587d-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

