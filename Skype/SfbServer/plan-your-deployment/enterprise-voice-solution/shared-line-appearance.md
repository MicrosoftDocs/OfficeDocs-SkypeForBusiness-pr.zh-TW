---
title: 在商務用 Skype Server 2015 中規劃共用線外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 請閱讀本主題，瞭解如何在商務用 Skype Server 2015 （2015年11月累計更新）中規劃共用線外觀（SLA）。
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802433"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="939fd-103">在商務用 Skype Server 2015 中規劃共用線外觀</span><span class="sxs-lookup"><span data-stu-id="939fd-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="939fd-104">請閱讀本主題，瞭解如何在商務用 Skype Server 2015 （2015年11月累計更新）中規劃共用線外觀（SLA）。</span><span class="sxs-lookup"><span data-stu-id="939fd-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="939fd-105">共用線外觀是商務用 Skype 中的一項功能，可在稱為共用電話號碼的特定號碼上處理多個通話。</span><span class="sxs-lookup"><span data-stu-id="939fd-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="939fd-106">SLA 可以設定任何已啟用企業語音功能的商務用 Skype 使用者作為含多個線路的共用號碼，以回應多個通話。</span><span class="sxs-lookup"><span data-stu-id="939fd-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="939fd-107">通話不會在共用電話號碼上實際接收，而是將其轉寄給充當共用號碼代理人的使用者。</span><span class="sxs-lookup"><span data-stu-id="939fd-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="939fd-108">任何一個代理人都可以接聽通話，而其餘的代理人會在他們的電話上收到通知，告知他們接聽通話的人，以及哪個線路變得占線。</span><span class="sxs-lookup"><span data-stu-id="939fd-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="939fd-109">您可以在 SLA 中，將行數和代理人都設定為共用的號碼。</span><span class="sxs-lookup"><span data-stu-id="939fd-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="939fd-110">此外，高級選項（例如 BusyOption （所有線路都忙的情況下會發生什麼情況）和 MissedCallOption （沒有任何代理人都能接聽通話的情況），也可以設定共用的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="939fd-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="939fd-111">只有下列電話裝置支援 SLA （電腦、行動電話或其他裝置上的商務用 Skype 用戶端不支援此功能）：</span><span class="sxs-lookup"><span data-stu-id="939fd-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="939fd-112">含固件更新5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="939fd-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="939fd-113">含固件更新5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="939fd-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="939fd-114">含固件更新5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="939fd-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="939fd-115">含固件更新5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="939fd-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="939fd-116">SLA 是商務用 Skype Server 中的新功能，2015年11月累計更新。</span><span class="sxs-lookup"><span data-stu-id="939fd-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="939fd-117">如需有關部署 SLA 的資訊，請參閱[在商務用 Skype Server 2015 中部署共用行外觀](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="939fd-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="939fd-118">功能清單</span><span class="sxs-lookup"><span data-stu-id="939fd-118">Feature List</span></span>

<span data-ttu-id="939fd-119">設定 SLA 群組可啟用下列功能：</span><span class="sxs-lookup"><span data-stu-id="939fd-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="939fd-120">群組中的所有代理人都可以將來電應答給相同的共用號碼。</span><span class="sxs-lookup"><span data-stu-id="939fd-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="939fd-121">通話可以是 PSTN 或以 SIP 為基礎。</span><span class="sxs-lookup"><span data-stu-id="939fd-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="939fd-122">代理人可以保留並挑選通話。</span><span class="sxs-lookup"><span data-stu-id="939fd-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="939fd-123">代理人可以將來電轉接到 SLA 群組以外的號碼。</span><span class="sxs-lookup"><span data-stu-id="939fd-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="939fd-124">代理人可以查看共用電話號碼目前有多少來電，以及每個通話的狀態。</span><span class="sxs-lookup"><span data-stu-id="939fd-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="939fd-125">您可以設定共用電話號碼的最大併發通話數。</span><span class="sxs-lookup"><span data-stu-id="939fd-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="939fd-126">您也可以設定在達到此上限之後，您想要處理其他通話的方式。</span><span class="sxs-lookup"><span data-stu-id="939fd-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="939fd-127">過多的通話可能會受到占線、轉寄至備用號碼，或轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="939fd-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="939fd-128">您可以設定要處理的未接來電（在某個時間之後未拾取來電）。</span><span class="sxs-lookup"><span data-stu-id="939fd-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="939fd-129">如果您啟用 [群組身分識別] 的語音信箱，未接來電會自動移至 [語音信箱]。</span><span class="sxs-lookup"><span data-stu-id="939fd-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="939fd-130">如果您沒有為群組身分識別（共用電話號碼）啟用語音信箱，您可以選擇讓未接來電遭到使用占線信號，轉寄到備用號碼或中斷連線。</span><span class="sxs-lookup"><span data-stu-id="939fd-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

