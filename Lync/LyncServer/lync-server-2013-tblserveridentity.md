---
title: Lync Server 2013： tblServerIdentity
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
ms.openlocfilehash: 206efe412712d2acb311b951bd0554bed3c9f650
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536230"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="5d882-102">Lync Server 2013 中的 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="5d882-102">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d882-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5d882-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5d882-104">tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="5d882-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="5d882-105">Columns</span><span class="sxs-lookup"><span data-stu-id="5d882-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d882-106">欄</span><span class="sxs-lookup"><span data-stu-id="5d882-106">Column</span></span></th>
<th><span data-ttu-id="5d882-107">類型</span><span class="sxs-lookup"><span data-stu-id="5d882-107">Type</span></span></th>
<th><span data-ttu-id="5d882-108">描述</span><span class="sxs-lookup"><span data-stu-id="5d882-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d882-109">serverID</span><span class="sxs-lookup"><span data-stu-id="5d882-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="5d882-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="5d882-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5d882-111">伺服器識別碼。</span><span class="sxs-lookup"><span data-stu-id="5d882-111">Server ID.</span></span> <span data-ttu-id="5d882-112">對應至中央管理存放區的實例識別碼。</span><span class="sxs-lookup"><span data-stu-id="5d882-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d882-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="5d882-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="5d882-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="5d882-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5d882-115">使用 Windows Communication Foundation 位址的伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="5d882-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d882-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="5d882-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="5d882-117">datetime</span><span class="sxs-lookup"><span data-stu-id="5d882-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="5d882-118">通道伺服器更新此列以證明其為執行中的最新時間。</span><span class="sxs-lookup"><span data-stu-id="5d882-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5d882-119">索引鍵</span><span class="sxs-lookup"><span data-stu-id="5d882-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d882-120">欄</span><span class="sxs-lookup"><span data-stu-id="5d882-120">Column</span></span></th>
<th><span data-ttu-id="5d882-121">描述</span><span class="sxs-lookup"><span data-stu-id="5d882-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d882-122">serverID</span><span class="sxs-lookup"><span data-stu-id="5d882-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="5d882-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5d882-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

