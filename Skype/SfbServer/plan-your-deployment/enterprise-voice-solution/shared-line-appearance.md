---
title: 在商務用 Skype Server 2015 中規劃共用行外觀
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 閱讀此主題以瞭解如何在商務用 Skype Server 2015，2015累計更新中規劃共用線外觀 (SLA) 。
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813343"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="c55f8-103">在商務用 Skype Server 2015 中規劃共用行外觀</span><span class="sxs-lookup"><span data-stu-id="c55f8-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c55f8-104">閱讀此主題以瞭解如何在商務用 Skype Server 2015，2015累計更新中規劃共用線外觀 (SLA) 。</span><span class="sxs-lookup"><span data-stu-id="c55f8-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="c55f8-105">共用線外觀是商務用 Skype 中的一項功能，用來處理特定號碼（稱為共用號碼）上的多個通話。</span><span class="sxs-lookup"><span data-stu-id="c55f8-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="c55f8-106">SLA 可將任何已啟用企業語音的商務用 Skype 使用者設定為具有多行的共用號碼，以回應多個通話。</span><span class="sxs-lookup"><span data-stu-id="c55f8-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="c55f8-107">呼叫並未實際接收共用號碼，而是轉寄給充當共用號碼代理人的使用者。</span><span class="sxs-lookup"><span data-stu-id="c55f8-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="c55f8-108">任何一位代理人都可以接聽來電，而其餘的代理人會在他們的電話上取得通知，告知已收取通話的人員，以及哪些線路已變得忙碌的結果。</span><span class="sxs-lookup"><span data-stu-id="c55f8-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="c55f8-109">您可以設定 SLA 中共用號碼的行數和代理人。</span><span class="sxs-lookup"><span data-stu-id="c55f8-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="c55f8-110">此外，高級選項（例如 BusyOption (所有線路忙碌) 和 MissedCallOption 時，會發生什麼情況）。 (所有代理人都不會拾取來電) 的情況，也可以設定共用號碼。</span><span class="sxs-lookup"><span data-stu-id="c55f8-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="c55f8-111">僅在下列電話裝置上支援 SLA (電腦、行動電話或其他裝置上的商務用 Skype 用戶端不支援此項功能) ：</span><span class="sxs-lookup"><span data-stu-id="c55f8-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="c55f8-112">含固件更新5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="c55f8-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c55f8-113">含固件更新5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="c55f8-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c55f8-114">含固件更新5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="c55f8-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c55f8-115">含固件更新5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="c55f8-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="c55f8-116">SLA 是商務用 Skype Server 中的新功能（2015年11月累積更新）。</span><span class="sxs-lookup"><span data-stu-id="c55f8-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="c55f8-117">如需部署 SLA 的詳細資訊，請參閱 [在商務用 Skype Server 2015 中部署共用行外觀](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="c55f8-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="c55f8-118">功能清單</span><span class="sxs-lookup"><span data-stu-id="c55f8-118">Feature List</span></span>

<span data-ttu-id="c55f8-119">設定 SLA 群組可啟用下列專案：</span><span class="sxs-lookup"><span data-stu-id="c55f8-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="c55f8-120">群組中的所有代理人都可以接聽撥入呼叫相同共用號碼。</span><span class="sxs-lookup"><span data-stu-id="c55f8-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="c55f8-121">通話可以是以 PSTN 為基礎或以 SIP 為基礎。</span><span class="sxs-lookup"><span data-stu-id="c55f8-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="c55f8-122">代理人可以保留及挑選通話。</span><span class="sxs-lookup"><span data-stu-id="c55f8-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="c55f8-123">代理人可將來電轉接至 SLA 群組以外的號碼。</span><span class="sxs-lookup"><span data-stu-id="c55f8-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="c55f8-124">代理人可以查看共用號碼目前有多少通話，並查看每個通話的狀態。</span><span class="sxs-lookup"><span data-stu-id="c55f8-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="c55f8-125">您可以設定共用號碼的並行通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="c55f8-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="c55f8-126">您也可以設定達到上限之後，要如何處理其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="c55f8-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="c55f8-127">過度通話可能會遭到忙碌，但會轉接至備用號碼，或轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c55f8-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="c55f8-128">您可以設定在特定時間) 進行處理時，要如何撥打未接來電 (通話的方式。</span><span class="sxs-lookup"><span data-stu-id="c55f8-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="c55f8-129">如果您為群組識別碼啟用語音信箱，未接來電會自動移至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c55f8-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="c55f8-130">如果您未啟用群組身分識別的「 (共用號碼」) 的語音信箱，您可以選擇將未接來電拒絕為繁忙的信號、轉寄至備用號碼，或中斷連線。</span><span class="sxs-lookup"><span data-stu-id="c55f8-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

