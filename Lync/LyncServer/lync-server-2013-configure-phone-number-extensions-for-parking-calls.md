---
title: Lync Server 2013： 設定電話分機號碼駐留通話
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
ms.openlocfilehash: 39bd945f7e685965f892b3f3cab1be92bab73574
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="b426d-102">設定電話分機號碼的 Lync Server 2013 中駐留通話</span><span class="sxs-lookup"><span data-stu-id="b426d-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b426d-103">_**主題上次修改日期：** 2012年-09-10_</span><span class="sxs-lookup"><span data-stu-id="b426d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="b426d-104">通話駐留應用程式來駐留通話通話駐留軌道表中使用分機號碼。</span><span class="sxs-lookup"><span data-stu-id="b426d-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="b426d-105">您需要設定通話駐留軌道表與您的組織會保留駐留通話的分機號碼的範圍。</span><span class="sxs-lookup"><span data-stu-id="b426d-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="b426d-106">這些副檔名必須是虛擬分機擴充 （也就是沒有任何使用者或指派給他們的電話的功能）。</span><span class="sxs-lookup"><span data-stu-id="b426d-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="b426d-107">通話駐留應用程式已在其中部署及設定每個 Lync 伺服器集區可以有一或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="b426d-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="b426d-108">在 Lync Server 部署，軌道範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="b426d-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b426d-109">您必須語音原則中選取 [<STRONG>啟用通話駐留</STRONG>] 核取方塊，之後才能使用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="b426d-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="b426d-110">根據預設，不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="b426d-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b426d-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b426d-111">In This Section</span></span>

  - [<span data-ttu-id="b426d-112">建立或修改通話駐留軌道範圍在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b426d-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="b426d-113">刪除 Lync Server 2013 中的通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="b426d-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

