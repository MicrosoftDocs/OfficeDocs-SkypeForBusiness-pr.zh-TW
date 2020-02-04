---
title: Lync Server 2013：（選用）驗證通話駐留部署
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
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="50d8e-102">可選在 Lync Server 2013 中確認通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="50d8e-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50d8e-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="50d8e-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="50d8e-104">安裝並設定 [通話駐留] 之後，您必須驗證設定，以確保停車場和檢索通話如期運作。</span><span class="sxs-lookup"><span data-stu-id="50d8e-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="50d8e-105">至少請確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="50d8e-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="50d8e-106">呼叫已啟用通話駐留且使用者寄存通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="50d8e-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50d8e-107">如果您在執行此測試前，在語音原則中啟用通話駐留，停用通話的使用者需要登出 Lync Server，然後重新登入，才能在轉移通話清單中看到通話寄存選項。</span><span class="sxs-lookup"><span data-stu-id="50d8e-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="50d8e-108">撥打軌道數位以取得通話。</span><span class="sxs-lookup"><span data-stu-id="50d8e-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="50d8e-109">停用另一個通話，讓撥出通話超時，而且不要挑選 ringback。</span><span class="sxs-lookup"><span data-stu-id="50d8e-109">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="50d8e-110">確認超時通話正確地路由至指定給**OnTimeoutURI**的回退目的地。</span><span class="sxs-lookup"><span data-stu-id="50d8e-110">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

