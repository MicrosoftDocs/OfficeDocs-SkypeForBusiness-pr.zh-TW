---
title: Teams Contoso 案例研究
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
description: Teams多國公司的語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121291"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="cad83-103">Contoso 案例研究：自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="cad83-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="cad83-104">Contoso 熟悉內部部署和部署中的自動商務用 Skype佇列。</span><span class="sxs-lookup"><span data-stu-id="cad83-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="cad83-105">為了瞭解如何設定雲端自動電話機和通話佇列，他們檢閱了自動Teams[和通話佇列的規劃](plan-auto-attendant-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="cad83-106">根據網站類型的需求</span><span class="sxs-lookup"><span data-stu-id="cad83-106">Requirements depending on site type</span></span>

<span data-ttu-id="cad83-107">根據網站類型，Contoso 有下列需求：</span><span class="sxs-lookup"><span data-stu-id="cad83-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="cad83-108">網站類型 A：傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="cad83-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="cad83-109">網站類型 A 需要保留與接待員相關聯的電話號碼，與自動電話機的號碼相同。</span><span class="sxs-lookup"><span data-stu-id="cad83-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="cad83-110">每個網站的重要部門都會擁有自己的通話佇列，以路由給小組成員。</span><span class="sxs-lookup"><span data-stu-id="cad83-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="cad83-111">網站混合使用直接路由電話系統直接路由電話系統通話方案。</span><span class="sxs-lookup"><span data-stu-id="cad83-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="cad83-112">網站類型 B：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="cad83-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="cad83-113">網站類型 B 現有的自動電話機和通話佇列需要遷移到Teams。</span><span class="sxs-lookup"><span data-stu-id="cad83-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="cad83-114">Contoso 需要保留與自動總機相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cad83-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="cad83-115">Contoso 將大部分的網站移至 電話系統通話方案。</span><span class="sxs-lookup"><span data-stu-id="cad83-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="cad83-116">不過，在少數沒有通話方案的位置，Contoso 將這些網站移至直接路由組。</span><span class="sxs-lookup"><span data-stu-id="cad83-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="cad83-117">網站類型 C：商務用 Skype 企業語音 &傳統傳統電話系統</span><span class="sxs-lookup"><span data-stu-id="cad83-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="cad83-118">Site Type C 有現有的自動語音機，這些自動語音機位於傳統的傳統電話系統中。</span><span class="sxs-lookup"><span data-stu-id="cad83-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="cad83-119">此網站的決策和組組與網站類型 A 相同。</span><span class="sxs-lookup"><span data-stu-id="cad83-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="cad83-120">針對所有網站類型，Contoso 詢問下列問題：</span><span class="sxs-lookup"><span data-stu-id="cad83-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="cad83-121">問：我們會使用新號碼或現有號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="cad83-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="cad83-122">答：Contoso 決定使用現有電話號碼指派給自動總機的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="cad83-123">問：何時可以使用自動電話機接聽來電？</span><span class="sxs-lookup"><span data-stu-id="cad83-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="cad83-124">答：Contoso 決定設定上班時間，並且將上班時間之後收到的來電重新導向到「工作時間後」自動總機。</span><span class="sxs-lookup"><span data-stu-id="cad83-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="cad83-125">問：如何將通話路由至通話佇列中的成員：電話機、串串或迴圈路由？</span><span class="sxs-lookup"><span data-stu-id="cad83-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="cad83-126">答：Contoso 決定使用 Attendant 路由，</span><span class="sxs-lookup"><span data-stu-id="cad83-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="cad83-127">問：我們會如何判斷使用者何時應該或不應該接到來電？</span><span class="sxs-lookup"><span data-stu-id="cad83-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="cad83-128">答：Contoso 決定使用通話處理選項來判斷代理人是否可用：目前狀態路由。</span><span class="sxs-lookup"><span data-stu-id="cad83-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="cad83-129">配置</span><span class="sxs-lookup"><span data-stu-id="cad83-129">Configuration</span></span>

<span data-ttu-id="cad83-130">設定自動電話機和通話佇列的步驟包括管理資源帳戶 [中概述的下列步驟](manage-resource-accounts.md)：</span><span class="sxs-lookup"><span data-stu-id="cad83-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="cad83-131">取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="cad83-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="cad83-132">取得免費電話系統 - 虛擬使用者授權或付費電話系統授權，以用於資源帳戶或電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="cad83-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="cad83-133">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-133">Create the resource account.</span></span> <span data-ttu-id="cad83-134">需要自動電話機或通話佇列才能有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="cad83-135">將電話系統或電話系統虛擬使用者授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="cad83-136">如要詳細資訊，請參閱Microsoft 365 電話系統[– 虛擬使用者授權](./teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="cad83-137">將服務電話號碼指派給您指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="cad83-138">建立電話系統通話佇列或自動電話機</span><span class="sxs-lookup"><span data-stu-id="cad83-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="cad83-139">使用通話佇列或自動話務員連結資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="cad83-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="cad83-140">具有直接電話系統的網站</span><span class="sxs-lookup"><span data-stu-id="cad83-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="cad83-141">Contoso 必須設定當地電信公司提供的電話號碼，做為 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cad83-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="cad83-142">若要設定透過直接路由提供的電話號碼，Contoso 會遵循管理資源帳戶 [中的指示](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="cad83-143">由於Office 365不知道內部部署電話號碼，Contoso 使用 PowerShell 來完成設定。</span><span class="sxs-lookup"><span data-stu-id="cad83-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="cad83-144">若要設定雲端自動話務員，Contoso 會遵循設定雲端自動話務員中概述 [的步驟](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="cad83-145">若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中 [概述的步驟](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="cad83-146">具有通話電話系統的網站</span><span class="sxs-lookup"><span data-stu-id="cad83-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="cad83-147">Contoso 必須將用於自動商務用 Skype 企業語音的電話號碼Office 365 電話系統。</span><span class="sxs-lookup"><span data-stu-id="cad83-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="cad83-148">這允許將相同的號碼指派為服務號碼，做為自動總機使用。</span><span class="sxs-lookup"><span data-stu-id="cad83-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="cad83-149">若要移轉電話號碼，Contoso 遵循將電話號碼移[](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)轉至Teams中的指示，並取得管理貴組織電話號碼[的其他指示](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="cad83-150">若要設定雲端自動話務員，Contoso 會遵循設定雲端自動話務員中概述 [的步驟](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="cad83-151">若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中 [概述的步驟](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="cad83-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

