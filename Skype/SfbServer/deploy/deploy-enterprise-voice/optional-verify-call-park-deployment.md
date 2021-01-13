---
title: " (選用) 在商務用 Skype 中驗證通話駐留部署"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在商務用 Skype Server Enterprise Voice 中驗證通話駐留的部署。
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830893"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="6e0d8-103"> (選用) 在商務用 Skype 中驗證通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="6e0d8-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="6e0d8-104">在商務用 Skype Server Enterprise Voice 中驗證通話駐留的部署。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6e0d8-105">安裝及設定通話駐留後，您必須確認設定，以確定停車場和取回通話如預期般地運作。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="6e0d8-106">請至少確認下列項目：</span><span class="sxs-lookup"><span data-stu-id="6e0d8-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="6e0d8-107">呼叫已啟用通話駐留且使用者寄存通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e0d8-108">如果您在執行此測試之前，已在語音原則中啟用通話駐留，則寄存通話的使用者需要登出商務用 Skype，然後重新登入，才能在轉接通話清單中看到通話駐留選項。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="6e0d8-109">撥打軌道號碼以取得通話。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="6e0d8-110">寄存另一次通話，讓寄存通話超時，但不要挑選回電。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-110">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="6e0d8-111">確認已超時呼叫已正確路由傳送至 **OnTimeoutURI** 所指定的回退目的地。</span><span class="sxs-lookup"><span data-stu-id="6e0d8-111">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

