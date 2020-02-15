---
title: Lync Server 2013： 設定群組來電接聽的號碼範圍
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
ms.openlocfilehash: 47639ea1e158ce5cb4e6463b1fb953fc50412c79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="0154c-102">在 Lync Server 2013 中設定群組來電接聽的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="0154c-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0154c-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="0154c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0154c-104">群組來電接聽為基礎的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="0154c-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="0154c-105">當您部署群組來電接聽時，您可以設定通話駐留軌道表與範圍指定為呼叫收取群組號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0154c-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="0154c-106">這些群組數字是使用者来揀選響鈴另一位使用者的呼叫撥號對應表中的數字。</span><span class="sxs-lookup"><span data-stu-id="0154c-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="0154c-107">就像通話駐留軌道號碼，請呼叫收取群組號碼需要為虛擬分機，沒有任何使用者或指派給他們的電話。</span><span class="sxs-lookup"><span data-stu-id="0154c-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="0154c-108">您將部署群組來電接聽每個前端集區可以有一或多個範圍的通話收取群組數字。</span><span class="sxs-lookup"><span data-stu-id="0154c-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="0154c-109">在 Lync Server 部署，群組號碼範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="0154c-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0154c-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0154c-110">In This Section</span></span>

  - [<span data-ttu-id="0154c-111">建立或修改 Lync Server 2013 中的群組來電接聽號碼範圍</span><span class="sxs-lookup"><span data-stu-id="0154c-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="0154c-112">刪除 Lync Server 2013 中的群組來電接聽號碼範圍</span><span class="sxs-lookup"><span data-stu-id="0154c-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

