---
title: 團隊語音 Contoso 案例研究
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
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785973"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="a5e8f-103">Contoso 案例研究：自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="a5e8f-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="a5e8f-104">Contoso 已熟悉自動語音應答及從其內部部署商務用 Skype 部署呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="a5e8f-105">若要瞭解如何設定雲端自動語音應答，他們[會複習什麼是雲端自動](what-are-phone-system-auto-attendants.md)語音應答？以及[小型企業範例-設定自動助理教學](tutorial-org-aa.yml)課程。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="a5e8f-106">若要瞭解設定通話佇列的可用選項，Contoso 已審閱 [[建立雲端通話佇列](create-a-phone-system-call-queue.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="a5e8f-107">根據網站類型而定的需求</span><span class="sxs-lookup"><span data-stu-id="a5e8f-107">Requirements depending on site type</span></span>

<span data-ttu-id="a5e8f-108">視網站類型而定，Contoso 有下列需求：</span><span class="sxs-lookup"><span data-stu-id="a5e8f-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="a5e8f-109">網站類型 A：傳統舊版電話系統</span><span class="sxs-lookup"><span data-stu-id="a5e8f-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="a5e8f-110">[網站類型] 您需要將與接待員相關聯的電話號碼保留為其自動語音應答的號碼。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="a5e8f-111">每個網站的主要部門都要有自己的通話佇列，以傳送給小組成員。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="a5e8f-112">有一個混合的網站，可將手機系統與直接路由與電話系統搭配通話方案使用。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="a5e8f-113">網站類型 B：商務用 Skype 企業語音</span><span class="sxs-lookup"><span data-stu-id="a5e8f-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="a5e8f-114">網站類型 B 有現有的自動語音應答及呼叫佇列，需要將它遷移至小組。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="a5e8f-115">Contoso 需要保留與自動語音助理相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="a5e8f-116">Contoso 已使用通話方案將大部分這些網站移至電話系統。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="a5e8f-117">不過，在幾個無法使用通話方案的位置，Contoso 會將這些網站移至直接路由設定。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="a5e8f-118">網站類型 C：商務用 Skype Enterprise Voice & 傳統舊版電話系統</span><span class="sxs-lookup"><span data-stu-id="a5e8f-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="a5e8f-119">網站類型 C 已有駐留在傳統舊版電話系統中的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="a5e8f-120">此網站的決定與設定與 [網站類型 A] 相同。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="a5e8f-121">針對所有網站類型，Contoso 提出下列問題：</span><span class="sxs-lookup"><span data-stu-id="a5e8f-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="a5e8f-122">問：我們會使用新的或現有的號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="a5e8f-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="a5e8f-123">A： Contoso 決定將現有的電話號碼指派給自動語音應答的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="a5e8f-124">問：自動語音應答會在何時可接受來電？</span><span class="sxs-lookup"><span data-stu-id="a5e8f-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="a5e8f-125">A： Contoso 決定要設定上班時間，並在上班時間已重新導向至「下班後」自動語音應答之後收到來電。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="a5e8f-126">問：如何將呼叫路由到通話佇列中的成員： [助理]、[串列] 或 [迴圈複用] 路由？</span><span class="sxs-lookup"><span data-stu-id="a5e8f-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="a5e8f-127">A： Contoso 決定使用助理路由，</span><span class="sxs-lookup"><span data-stu-id="a5e8f-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="a5e8f-128">問：我們如何判斷使用者應該何時或不應該撥打電話？</span><span class="sxs-lookup"><span data-stu-id="a5e8f-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="a5e8f-129">A： Contoso 決定使用 [呼叫處理] 選項來判斷是否有可用的代理程式：目前狀態路由。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="a5e8f-130">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5e8f-130">Configuration</span></span>

<span data-ttu-id="a5e8f-131">設定自動語音應答及呼叫佇列的步驟，包括以下在[管理資源帳戶](manage-resource-accounts.md)中所述的下列各項：</span><span class="sxs-lookup"><span data-stu-id="a5e8f-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="a5e8f-132">取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="a5e8f-133">取得免費的電話系統-虛擬使用者授權或付費電話系統授權，以與資源帳戶或電話系統授權搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="a5e8f-134">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-134">Create the resource account.</span></span> <span data-ttu-id="a5e8f-135">需要自動語音應答或通話佇列，才能擁有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="a5e8f-136">將電話系統或電話系統-虛擬使用者授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="a5e8f-137">如需詳細資訊，請參閱[Microsoft 365 電話系統-虛擬使用者授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="a5e8f-138">將服務電話號碼指派給您指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="a5e8f-139">建立電話系統通話佇列或自動語音應答</span><span class="sxs-lookup"><span data-stu-id="a5e8f-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="a5e8f-140">連結資源帳戶與通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="a5e8f-141">具有直接路由的手機系統網站</span><span class="sxs-lookup"><span data-stu-id="a5e8f-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="a5e8f-142">Contoso 必須將當地電信公司提供的電話號碼設定為 Office 365 中的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="a5e8f-143">若要設定透過直接路由提供的電話號碼，Contoso 按照 [[管理資源帳戶](manage-resource-accounts.md)] 中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="a5e8f-144">因為 Office 365 不知道內部部署的電話號碼，所以 Contoso 使用 PowerShell 來完成設定。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="a5e8f-145">若要設定雲端自動語音應答，Contoso 按照[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="a5e8f-146">若要設定雲端通話佇列，Contoso 按照[建立雲端通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="a5e8f-147">使用電話系統進行通話方案的網站</span><span class="sxs-lookup"><span data-stu-id="a5e8f-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="a5e8f-148">Contoso 必須為商務用 Skype Enterprise Voice 自動語音應答的電話號碼寄回 Office 365 Phone 系統。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="a5e8f-149">這允許將相同的號碼指派為作為自動語音應答使用的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="a5e8f-150">若要移植電話號碼，Contoso 按照將[電話號碼轉接至小組](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)的指示進行，並取得[管理組織電話號碼的](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)其他指導方針。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="a5e8f-151">若要設定雲端自動語音應答，Contoso 請按照[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="a5e8f-152">若要設定雲端通話佇列，Contoso 按照[建立雲端通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a5e8f-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 