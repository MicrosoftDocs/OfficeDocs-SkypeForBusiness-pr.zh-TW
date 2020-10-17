---
title: Lync Server 2013：設定群組呼叫收取號碼範圍
description: Lync Server 2013：設定群組呼叫收取號碼範圍。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f0594bd681a157b8ff479846b2f6f1964a09cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553279"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="40065-103">在 Lync Server 2013 中設定群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="40065-103">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40065-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="40065-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="40065-105">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="40065-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="40065-106">當您部署群組叫用裝貨時，請使用指定為呼叫收取群組號碼的電話號碼範圍，設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="40065-106">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="40065-107">這些群組號碼是使用者在撥打其他使用者所撥打之來電時所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="40065-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="40065-108">與通話駐留軌道號碼類似，來電收取群組數目必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="40065-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="40065-109">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="40065-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="40065-110">群組號碼範圍必須在 Lync Server 部署間具有全域唯一性。</span><span class="sxs-lookup"><span data-stu-id="40065-110">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="40065-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="40065-111">In This Section</span></span>

  - [<span data-ttu-id="40065-112">在 Lync Server 2013 中建立或修改群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="40065-112">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="40065-113">在 Lync Server 2013 中刪除群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="40065-113">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

