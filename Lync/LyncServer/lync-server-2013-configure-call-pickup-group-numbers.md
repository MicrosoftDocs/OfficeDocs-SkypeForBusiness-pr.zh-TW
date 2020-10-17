---
title: Lync Server 2013：設定呼叫收取群組號碼
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
ms.openlocfilehash: 586af96cccdc661855efb83aefdb0e7e534dc105
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521140"
---
# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="8e505-102">在 Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="8e505-102">Configure call pickup group numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e505-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8e505-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8e505-104">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="8e505-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="8e505-105">當您部署群組叫用裝貨時，請使用指定為呼叫收取群組號碼的電話號碼範圍，設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="8e505-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="8e505-106">這些群組號碼是使用者在撥打其他使用者所撥打之來電時所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="8e505-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="8e505-107">與通話駐留軌道號碼類似，來電收取群組數目必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="8e505-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="8e505-108">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="8e505-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="8e505-109">群組號碼範圍必須在 Lync Server 部署間具有全域唯一性。</span><span class="sxs-lookup"><span data-stu-id="8e505-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e505-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8e505-110">In This Section</span></span>

[<span data-ttu-id="8e505-111">在 Lync Server 2013 中建立或修改群組呼叫收取號碼範圍</span><span class="sxs-lookup"><span data-stu-id="8e505-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

