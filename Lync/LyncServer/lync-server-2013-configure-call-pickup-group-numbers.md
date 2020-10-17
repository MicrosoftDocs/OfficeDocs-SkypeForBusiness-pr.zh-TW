---
title: Lync Server 2013：設定呼叫收取群組號碼
description: Lync Server 2013：設定呼叫收取群組號碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ddffae2e385ce6c3fd7a700a9b94a89b1b6679f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565089"
---
# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="5d657-103">在 Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="5d657-103">Configure call pickup group numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d657-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5d657-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5d657-105">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="5d657-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="5d657-106">當您部署群組叫用裝貨時，請使用指定為呼叫收取群組號碼的電話號碼範圍，設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="5d657-106">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="5d657-107">這些群組號碼是使用者在撥打其他使用者所撥打之來電時所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="5d657-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="5d657-108">與通話駐留軌道號碼類似，來電收取群組數目必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="5d657-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="5d657-109">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="5d657-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="5d657-110">群組號碼範圍必須在 Lync Server 部署間具有全域唯一性。</span><span class="sxs-lookup"><span data-stu-id="5d657-110">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d657-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5d657-111">In This Section</span></span>

[<span data-ttu-id="5d657-112">在 Lync Server 2013 中建立或修改群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="5d657-112">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

