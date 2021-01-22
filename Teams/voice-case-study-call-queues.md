---
title: Teams Voice Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 適用于多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918729"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="5f201-103">Contoso 案例研究：自動撥打和通話佇列</span><span class="sxs-lookup"><span data-stu-id="5f201-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="5f201-104">Contoso 已熟悉從內部部署商務用 Skype 部署中的自動撥打和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="5f201-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="5f201-105">若要瞭解如何設定雲端自動撥打和通話佇列，他們檢閱了 Teams 自動撥打和 [通話佇列的規劃](plan-auto-attendant-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="5f201-106">依網站類型顯示的需求</span><span class="sxs-lookup"><span data-stu-id="5f201-106">Requirements depending on site type</span></span>

<span data-ttu-id="5f201-107">根據網站類型，Contoso 的需求如下：</span><span class="sxs-lookup"><span data-stu-id="5f201-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="5f201-108">網站類型 A：傳統舊版電話系統</span><span class="sxs-lookup"><span data-stu-id="5f201-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="5f201-109">需要網站類型 A，以保留與總機相關聯的電話號碼與其自動接聽電話的號碼。</span><span class="sxs-lookup"><span data-stu-id="5f201-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="5f201-110">每個網站的重要部門都會有自己的通話佇列，以路由給小組成員。</span><span class="sxs-lookup"><span data-stu-id="5f201-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="5f201-111">有一個網站混合使用電話系統與直接路由和電話系統以及通話方案。</span><span class="sxs-lookup"><span data-stu-id="5f201-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="5f201-112">網站類型 B：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="5f201-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="5f201-113">網站類型 B 有現有的自動 Attendant 和通話佇列，需要將其遷移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="5f201-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="5f201-114">Contoso 需要保留與自動 Attendant 相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5f201-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="5f201-115">Contoso 將大部分的網站移至有通話方案的電話系統。</span><span class="sxs-lookup"><span data-stu-id="5f201-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="5f201-116">不過，在通話方案無法提供的少數幾個位置，Contoso 將這些網站移至直接路由組案。</span><span class="sxs-lookup"><span data-stu-id="5f201-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="5f201-117">網站類型 C：商務用 Skype 企業語音&傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="5f201-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="5f201-118">網站類型 C 的現有自動語音語音人員，是位於傳統的舊版電話系統。</span><span class="sxs-lookup"><span data-stu-id="5f201-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="5f201-119">此網站的決策和組組與網站類型 A 相同。</span><span class="sxs-lookup"><span data-stu-id="5f201-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="5f201-120">針對所有網站類型，Contoso 詢問下列問題：</span><span class="sxs-lookup"><span data-stu-id="5f201-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="5f201-121">問：我們會使用新號碼或現有號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="5f201-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="5f201-122">答：Contoso 決定使用現有電話號碼指派給自動 Attendant 的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="5f201-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="5f201-123">問：系統何時可以使用自動撥打接聽來電？</span><span class="sxs-lookup"><span data-stu-id="5f201-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="5f201-124">答：Contoso 決定設定上班時間，將上班時間之後接到的電話重新導向到「上班時間」自動接聽。</span><span class="sxs-lookup"><span data-stu-id="5f201-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="5f201-125">問：如何將通話路由至通話佇列的成員：Attendant、循序或圓形路由？</span><span class="sxs-lookup"><span data-stu-id="5f201-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="5f201-126">答：Contoso 決定使用 Attendant 路由，</span><span class="sxs-lookup"><span data-stu-id="5f201-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="5f201-127">問：我們會如何判斷使用者何時應該或不應接到來電？</span><span class="sxs-lookup"><span data-stu-id="5f201-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="5f201-128">答：Contoso 決定使用通話處理選項來判斷代理人是否可用：以目前狀態為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="5f201-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="5f201-129">配置</span><span class="sxs-lookup"><span data-stu-id="5f201-129">Configuration</span></span>

<span data-ttu-id="5f201-130">設定自動參與和通話佇列的步驟包括管理資源帳戶 [中概述的下列步驟](manage-resource-accounts.md)：</span><span class="sxs-lookup"><span data-stu-id="5f201-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="5f201-131">取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="5f201-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="5f201-132">取得免費的電話系統 - 虛擬使用者授權或付費電話系統授權，以與資源帳戶或電話系統授權一同使用。</span><span class="sxs-lookup"><span data-stu-id="5f201-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="5f201-133">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="5f201-133">Create the resource account.</span></span> <span data-ttu-id="5f201-134">需要自動撥打或通話佇列，才能有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="5f201-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="5f201-135">指派電話系統或電話系統 - 虛擬使用者授權給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="5f201-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="5f201-136">詳細資訊請參閱 Microsoft [365 電話系統 – 虛擬使用者授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。</span><span class="sxs-lookup"><span data-stu-id="5f201-136">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="5f201-137">將服務電話號碼指派給您指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="5f201-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="5f201-138">建立電話系統通話佇列或自動接聽</span><span class="sxs-lookup"><span data-stu-id="5f201-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="5f201-139">將資源帳戶與通話佇列或自動 attendant 連結。</span><span class="sxs-lookup"><span data-stu-id="5f201-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="5f201-140">使用電話系統直接路由的網站</span><span class="sxs-lookup"><span data-stu-id="5f201-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="5f201-141">Contoso 必須設定本地電信公司所提供的電話號碼，做為 Office 365 中的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="5f201-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="5f201-142">若要設定透過直接路由提供的電話號碼，Contoso 請按照管理資源帳戶 [中的指示進行](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="5f201-143">由於 Office 365 不知道內部部署電話號碼，因此 Contoso 使用 PowerShell 完成設定。</span><span class="sxs-lookup"><span data-stu-id="5f201-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="5f201-144">若要設定 Cloud 自動參與，Contoso 按照設定雲端自動 Attendant 中 [概述的步驟進行](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="5f201-145">若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中列出的 [步驟](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="5f201-146">使用電話系統與通話方案的網站</span><span class="sxs-lookup"><span data-stu-id="5f201-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="5f201-147">Contoso 必須針對商務用 Skype 企業語音自動語音語音，將電話號碼埠到 Office 365 電話系統。</span><span class="sxs-lookup"><span data-stu-id="5f201-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="5f201-148">這允許將相同的號碼指派為服務號碼，以做為自動 Attendant 使用。</span><span class="sxs-lookup"><span data-stu-id="5f201-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="5f201-149">若要移轉電話號碼，Contoso 遵循將電話號碼移轉至 [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 中的指示，並取得有關管理組織電話號碼 [的其他指引](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="5f201-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="5f201-150">若要設定雲端自動參與，Contoso 按照設定雲端自動 Attendant 中概述 [的步驟進行](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="5f201-151">若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中列出的 [步驟](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="5f201-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 