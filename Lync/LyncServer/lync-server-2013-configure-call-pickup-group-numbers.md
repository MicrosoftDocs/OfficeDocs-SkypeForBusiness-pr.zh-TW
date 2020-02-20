---
title: Lync Server 2013： 設定呼叫收取群組編號
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
ms.openlocfilehash: 5ddcd5ac7ac060a7ff1a295265f400ba3f95f0f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="4f644-102">Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="4f644-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f644-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="4f644-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4f644-104">群組來電接聽為基礎的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="4f644-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="4f644-105">當您部署群組來電接聽時，您可以設定通話駐留軌道表與範圍指定為呼叫收取群組號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4f644-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="4f644-106">這些群組數字是使用者来揀選響鈴另一位使用者的呼叫撥號對應表中的數字。</span><span class="sxs-lookup"><span data-stu-id="4f644-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="4f644-107">就像通話駐留軌道號碼，請呼叫收取群組號碼需要為虛擬分機，沒有任何使用者或指派給他們的電話。</span><span class="sxs-lookup"><span data-stu-id="4f644-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="4f644-108">您將部署群組來電接聽每個前端集區可以有一或多個範圍的通話收取群組數字。</span><span class="sxs-lookup"><span data-stu-id="4f644-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="4f644-109">在 Lync Server 部署，群組號碼範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="4f644-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f644-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4f644-110">In This Section</span></span>

[<span data-ttu-id="4f644-111">建立或修改 Lync Server 2013 中的群組來電接聽號碼範圍</span><span class="sxs-lookup"><span data-stu-id="4f644-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

