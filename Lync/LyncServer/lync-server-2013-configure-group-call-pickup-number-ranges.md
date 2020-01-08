---
title: Lync Server 2013：設定群組呼叫挑選號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbcbf05fbb73e2023b48bdb1f7e74ecdee6a36bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="1eec0-102">在 Lync Server 2013 中設定群組呼叫挑選號碼範圍</span><span class="sxs-lookup"><span data-stu-id="1eec0-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eec0-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1eec0-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1eec0-104">[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="1eec0-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="1eec0-105">當您部署群組呼叫挑選時，請將 [通話公園軌道] 表格設定為指定為 [呼叫挑選] 群組號碼的電話號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="1eec0-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="1eec0-106">這些群組號碼是使用者撥打電話給另一個使用者所撥打的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1eec0-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="1eec0-107">如同通話公園軌道編號，呼叫挑選群組的號碼必須是沒有指派給他們的使用者或電話的虛擬延伸。</span><span class="sxs-lookup"><span data-stu-id="1eec0-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="1eec0-108">您在其中部署 [群組呼叫挑選] 的每個前端池都可以有一或多個呼叫挑選群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="1eec0-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="1eec0-109">群組編號範圍在 Lync Server 部署中必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="1eec0-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1eec0-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="1eec0-110">In This Section</span></span>

  - [<span data-ttu-id="1eec0-111">在 Lync Server 2013 中建立或修改群組呼叫挑選號碼範圍</span><span class="sxs-lookup"><span data-stu-id="1eec0-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="1eec0-112">刪除 Lync Server 2013 中的群組呼叫挑選號碼範圍</span><span class="sxs-lookup"><span data-stu-id="1eec0-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

