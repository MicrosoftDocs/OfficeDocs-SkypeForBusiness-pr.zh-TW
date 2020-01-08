---
title: Lync Server 2013：設定停用通話的電話號碼延長線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a0fd55b851715fe8aef238797392af6317dff0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="86172-102">在 Lync Server 2013 中設定停用通話的電話號碼延伸</span><span class="sxs-lookup"><span data-stu-id="86172-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86172-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="86172-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="86172-104">通話公園應用程式使用 [通話駐留軌道] 表格中的分機號碼來寄存來電。</span><span class="sxs-lookup"><span data-stu-id="86172-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="86172-105">您需要將 [通話公園軌道] 表格設定為您的組織為寄存通話保留的分機號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="86172-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="86172-106">這些分機必須是虛擬分機 (也就是，沒有為分機指派任何使用者或電話)。</span><span class="sxs-lookup"><span data-stu-id="86172-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="86172-107">已部署並設定通話駐留應用程式的每個 Lync 伺服器池都可以有一個或多個軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="86172-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="86172-108">在 Lync Server 部署中，軌道範圍必須全域唯一。</span><span class="sxs-lookup"><span data-stu-id="86172-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86172-109">您必須先選取語音原則中的 [<STRONG>啟用電話寄存</STRONG>] 核取方塊，然後才能使用通話寄存。</span><span class="sxs-lookup"><span data-stu-id="86172-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="86172-110">根據預設，不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="86172-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86172-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="86172-111">In This Section</span></span>

  - [<span data-ttu-id="86172-112">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="86172-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="86172-113">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="86172-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

