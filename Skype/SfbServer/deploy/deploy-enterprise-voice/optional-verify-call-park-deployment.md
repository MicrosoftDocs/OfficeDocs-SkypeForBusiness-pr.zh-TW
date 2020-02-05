---
title: 可選在商務用 Skype 中確認通話駐留部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在商務用 Skype Server Enterprise Voice 中驗證撥出電話寄存的部署。
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767336"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="0bef6-103">可選在商務用 Skype 中確認通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="0bef6-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="0bef6-104">在商務用 Skype Server Enterprise Voice 中驗證撥出電話寄存的部署。</span><span class="sxs-lookup"><span data-stu-id="0bef6-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="0bef6-105">安裝並設定 [通話駐留] 之後，您必須驗證設定，以確保停車場和檢索通話如期運作。</span><span class="sxs-lookup"><span data-stu-id="0bef6-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="0bef6-106">至少請確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="0bef6-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="0bef6-107">呼叫已啟用通話駐留且使用者寄存通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="0bef6-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0bef6-108">如果您在執行此測試前，在語音原則中啟用通話駐留，停用通話的使用者需要登出商務用 Skype，然後重新登入，才能在轉移通話清單中看到通話寄存選項。</span><span class="sxs-lookup"><span data-stu-id="0bef6-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="0bef6-109">撥打軌道數位以取得通話。</span><span class="sxs-lookup"><span data-stu-id="0bef6-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="0bef6-110">停用另一個通話，讓撥出通話超時，而且不要挑選 ringback。</span><span class="sxs-lookup"><span data-stu-id="0bef6-110">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="0bef6-111">確認超時通話正確地路由至指定給**OnTimeoutURI**的回退目的地。</span><span class="sxs-lookup"><span data-stu-id="0bef6-111">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

