---
title: Lync Server 2013：設定停用通話的電話號碼分機號碼
description: Lync Server 2013：設定停用通話的電話號碼分機號碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548829"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="d79b8-103">在 Lync Server 2013 中設定休止通話的電話號碼分機號碼</span><span class="sxs-lookup"><span data-stu-id="d79b8-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d79b8-104">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d79b8-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d79b8-105">通話駐留應用程式會在通話駐留軌道表格中使用分機號碼，以寄存通話。</span><span class="sxs-lookup"><span data-stu-id="d79b8-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="d79b8-106">您必須使用組織為寄存通話所保留的分機號碼範圍，設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="d79b8-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="d79b8-107">這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。</span><span class="sxs-lookup"><span data-stu-id="d79b8-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="d79b8-108">在其中部署和設定通話駐留應用程式的每個 Lync 伺服器集區，都可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="d79b8-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d79b8-109">軌道範圍在 Lync Server 部署中必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="d79b8-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d79b8-110">您必須先選取語音原則中的 [ <STRONG>啟用通話駐留</STRONG> ] 核取方塊，才能使用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="d79b8-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="d79b8-111">根據預設，不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="d79b8-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d79b8-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d79b8-112">In This Section</span></span>

  - [<span data-ttu-id="d79b8-113">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="d79b8-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="d79b8-114">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="d79b8-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

