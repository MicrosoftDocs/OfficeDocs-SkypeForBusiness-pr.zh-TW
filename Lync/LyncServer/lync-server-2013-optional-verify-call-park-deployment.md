---
title: Lync Server 2013： (選用) 驗證通話駐留部署
description: Lync Server 2013： (選用) 驗證通話駐留部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541929"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="31464-103"> (選用) 在 Lync Server 2013 中驗證通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="31464-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31464-104">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="31464-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="31464-105">安裝及設定通話駐留後，您必須確認設定，以確定停車場和取回通話如預期般地運作。</span><span class="sxs-lookup"><span data-stu-id="31464-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="31464-106">請至少確認下列項目：</span><span class="sxs-lookup"><span data-stu-id="31464-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="31464-107">呼叫已啟用通話駐留且使用者寄存通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="31464-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31464-108">如果您在執行此測試之前，在語音原則中啟用通話駐留，則寄存通話的使用者需要登出 Lync Server，然後再重新登入，才能在轉接通話清單中看到通話駐留選項。</span><span class="sxs-lookup"><span data-stu-id="31464-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="31464-109">撥打軌道號碼以取得通話。</span><span class="sxs-lookup"><span data-stu-id="31464-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="31464-110">寄存另一次通話，讓寄存通話超時，但不要挑選回電。</span><span class="sxs-lookup"><span data-stu-id="31464-110">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="31464-111">確認已超時呼叫已正確路由傳送至 **OnTimeoutURI**所指定的回退目的地。</span><span class="sxs-lookup"><span data-stu-id="31464-111">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

