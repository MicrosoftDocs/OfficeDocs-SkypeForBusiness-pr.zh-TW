---
title: 'Lync Server 2013: （選用） 驗證通話保留部署'
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
ms.openlocfilehash: 0e0389e729f91da7cb91dff9426e38c1dcf20024
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="53480-102">（選用）確認 Lync Server 2013 中的通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="53480-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53480-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="53480-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="53480-104">安裝並設定通話駐留之後，您需要確認若要確定駐留並擷取通話運作符合預期組態。</span><span class="sxs-lookup"><span data-stu-id="53480-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="53480-105">請至少確認下列項目：</span><span class="sxs-lookup"><span data-stu-id="53480-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="53480-106">呼叫具有已啟用的通話駐留的使用者，並讓使用者駐留通話。</span><span class="sxs-lookup"><span data-stu-id="53480-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53480-107">如果您啟用語音原則中的通話駐留之前執行這項測試，則駐留通話的使用者必須登出 Lync Server]，然後再重新登入，無法看到 [通話駐留] 選項在傳送呼叫清單。</span><span class="sxs-lookup"><span data-stu-id="53480-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="53480-108">撥打軌道號碼以擷取通話。</span><span class="sxs-lookup"><span data-stu-id="53480-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="53480-109">其他通話駐留，讓駐留的通話逾時，並不會收取回電。</span><span class="sxs-lookup"><span data-stu-id="53480-109">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="53480-110">確認逾時通話正確地路由傳送至指定的**OnTimeoutURI**後援目的地。</span><span class="sxs-lookup"><span data-stu-id="53480-110">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

