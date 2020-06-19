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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785977"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="d2520-103">Contoso 案例研究：緊急通話</span><span class="sxs-lookup"><span data-stu-id="d2520-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="d2520-104">若要瞭解緊急通話的可用性，以及緊急通話 &mdash; 緊急位址、地點、緊急位置及登入位址的相關術語，請 &mdash; 查看[管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)並[規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="d2520-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="d2520-105">在 Office 365 中，通話方案使用者會自動啟用緊急通話。</span><span class="sxs-lookup"><span data-stu-id="d2520-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="d2520-106">但只有美國地區的通話方案使用者可以使用動態位置來路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="d2520-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="d2520-107">針對直接路由，Contoso 發現路由緊急通話需要額外設定，而且可能是合作夥伴連線性。</span><span class="sxs-lookup"><span data-stu-id="d2520-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="d2520-108">系統管理員必須設定與緊急路由服務提供者（ERSP）（美國）的連線，或針對緊急位置識別號碼（ELIN）應用程式設定會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="d2520-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="d2520-109">Contoso 在美國擁有辦事處，且在美國以外地區：</span><span class="sxs-lookup"><span data-stu-id="d2520-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="d2520-110">在美國，Contoso 通話方案使用者可以使用動態位置來路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="d2520-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="d2520-111">在美國以外，Contoso 擁有一些使用通話方案的網站，以及透過直接路由連接至手機系統的部分網站。</span><span class="sxs-lookup"><span data-stu-id="d2520-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="d2520-112">緊急通話使用案例</span><span class="sxs-lookup"><span data-stu-id="d2520-112">Emergency calling use cases</span></span>

<span data-ttu-id="d2520-113">決定 Contoso 將如何連接至電話系統之後，Contoso 已識別下列緊急通話使用案例：</span><span class="sxs-lookup"><span data-stu-id="d2520-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="d2520-114">在美國撥打電話方案使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="d2520-115">美國以外的通話計畫使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="d2520-116">透過直接路由連接至手機系統的使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="d2520-117">在美國撥打電話方案使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="d2520-118">需要將電話號碼與緊急位置相關聯的需求。</span><span class="sxs-lookup"><span data-stu-id="d2520-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="d2520-119">若要瞭解這些需求，Contoso 已檢查[通話方案的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="d2520-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="d2520-120">根據這些需求，當您將號碼指派給美國的使用者時，Contoso 決定要將位置與電話號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d2520-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="d2520-121">美國以外的通話計畫使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="d2520-122">若要瞭解電話號碼需要與緊急位置相關聯的時間，Contoso 已檢查[通話方案的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="d2520-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="d2520-123">根據需求，Contoso 決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="d2520-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="d2520-124">當您將數位指派給加拿大中的使用者時，Contoso 會將該位置與電話號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d2520-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="d2520-125">當您從 Office 365 取得電話號碼，或從其他服務提供者或承運人傳送號碼時，Contoso 會指派緊急地點。</span><span class="sxs-lookup"><span data-stu-id="d2520-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="d2520-126">透過直接路由連接至手機系統的使用者</span><span class="sxs-lookup"><span data-stu-id="d2520-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="d2520-127">若要針對此使用案例規劃緊急路由，Contoso 已審查[直接路由的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="d2520-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="d2520-128">因為直接路由使用者沒有像呼叫方案使用者一樣接收緊急通話，所以 Contoso 必須決定如何提供緊急通話。</span><span class="sxs-lookup"><span data-stu-id="d2520-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="d2520-129">直接路由可以連線到緊急路由服務提供者（ERSP）。</span><span class="sxs-lookup"><span data-stu-id="d2520-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="d2520-130">直接路由也可以有包含緊急位置識別號碼（ELIN）的 SBC。</span><span class="sxs-lookup"><span data-stu-id="d2520-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="d2520-131">緊急路由服務提供者（ERSP）考慮</span><span class="sxs-lookup"><span data-stu-id="d2520-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="d2520-132">緊急路由服務提供者（ERSPs）可以根據來電者的位置，自動路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="d2520-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="d2520-133">如果緊急路由服務提供者已整合至直接路由部署，則使用動態取得位置的緊急呼叫會自動路由到該位置的公用安全應答點（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="d2520-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="d2520-134">在沒有動態取得位置的緊急通話是先進行篩選，以便在根據更新的位置將呼叫連線至適當的派遣中心之前，決定使用者的目前位置。</span><span class="sxs-lookup"><span data-stu-id="d2520-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="d2520-135">ELIN 考慮</span><span class="sxs-lookup"><span data-stu-id="d2520-135">ELIN considerations</span></span>

<span data-ttu-id="d2520-136">如果 SBC ELIN 應用程式已整合至直接路由部署，則需要執行額外的設定步驟，才能將緊急位址與電話號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d2520-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="d2520-137">Contoso 決定使用包含緊急位置身分識別號碼（ELIN）應用程式的會話框線控制器。</span><span class="sxs-lookup"><span data-stu-id="d2520-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="d2520-138">Security 辦公桌通知</span><span class="sxs-lookup"><span data-stu-id="d2520-138">Security desk notification</span></span>

<span data-ttu-id="d2520-139">在 Microsoft 通話方案和電話系統直接路由中，都提供緊急通話時通知安全服務台的功能。</span><span class="sxs-lookup"><span data-stu-id="d2520-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="d2520-140">Contoso 已審查安全服務台通知中的詳細資料，以判斷是否應該在其辦公室進行設定</span><span class="sxs-lookup"><span data-stu-id="d2520-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="d2520-141">Contoso 決定要使用安全服務台通知。</span><span class="sxs-lookup"><span data-stu-id="d2520-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="d2520-142">Configuration</span><span class="sxs-lookup"><span data-stu-id="d2520-142">Configuration</span></span> 

<span data-ttu-id="d2520-143">Contoso 按照[設定動態緊急呼叫](configure-dynamic-emergency-calling.md)的步驟進行：</span><span class="sxs-lookup"><span data-stu-id="d2520-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="d2520-144">指派緊急位址</span><span class="sxs-lookup"><span data-stu-id="d2520-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="d2520-145">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="d2520-145">Configure network settings</span></span> 

- <span data-ttu-id="d2520-146">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="d2520-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="d2520-147">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="d2520-147">Configure emergency policies</span></span> 

- <span data-ttu-id="d2520-148">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="d2520-148">Enable users and sites</span></span> 

- <span data-ttu-id="d2520-149">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="d2520-149">Test emergency calling</span></span> 

<span data-ttu-id="d2520-150">設定動態緊急通話之後，Contoso 需要將位置指派給適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="d2520-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="d2520-151">若要新增、變更或移除組織的緊急位置，Contoso 按照[新增、變更或移除組織的緊急位置](add-change-remove-emergency-location-organization.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d2520-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="d2520-152">若要為建築物、地面和辦事處建立位置，Contoso 請按照[新增、變更或移除緊急位置](add-change-remove-emergency-place-organization.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d2520-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="d2520-153">若要指派緊急地點，Contoso 按照[指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d2520-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 