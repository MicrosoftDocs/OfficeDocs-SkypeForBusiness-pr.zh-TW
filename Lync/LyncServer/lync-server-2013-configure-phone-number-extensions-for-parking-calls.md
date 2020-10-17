---
title: Lync Server 2013：設定停用通話的電話號碼分機號碼
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
ms.openlocfilehash: 97a8871454ed95b955558c441d567f68dd0974bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520430"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="323da-102">在 Lync Server 2013 中設定休止通話的電話號碼分機號碼</span><span class="sxs-lookup"><span data-stu-id="323da-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="323da-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="323da-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="323da-104">通話駐留應用程式會在通話駐留軌道表格中使用分機號碼，以寄存通話。</span><span class="sxs-lookup"><span data-stu-id="323da-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="323da-105">您必須使用組織為寄存通話所保留的分機號碼範圍，設定通話駐留軌道表格。</span><span class="sxs-lookup"><span data-stu-id="323da-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="323da-106">這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。</span><span class="sxs-lookup"><span data-stu-id="323da-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="323da-107">在其中部署和設定通話駐留應用程式的每個 Lync 伺服器集區，都可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="323da-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="323da-108">軌道範圍在 Lync Server 部署中必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="323da-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="323da-109">您必須先選取語音原則中的 [ <STRONG>啟用通話駐留</STRONG> ] 核取方塊，才能使用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="323da-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="323da-110">根據預設，不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="323da-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="323da-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="323da-111">In This Section</span></span>

  - [<span data-ttu-id="323da-112">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="323da-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="323da-113">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="323da-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

