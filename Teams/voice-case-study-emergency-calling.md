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
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785977"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="1c892-103">Contoso 案例研究：緊急電話</span><span class="sxs-lookup"><span data-stu-id="1c892-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="1c892-104">若要瞭解緊急電話與緊急通話相關術語的可用性，Contoso 已審查管理緊急電話和規劃及設定動態緊急電話 &mdash; &mdash; 。 [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="1c892-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="1c892-105">在 Office 365，系統會自動啟用通話方案使用者進行緊急通話。</span><span class="sxs-lookup"><span data-stu-id="1c892-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="1c892-106">但只有美國的通話方案使用者可以使用動態位置路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="1c892-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="1c892-107">對於直接路由，Contoso 瞭解路由緊急電話時，可能需要其他組組，並可能還需要合作夥伴連接。</span><span class="sxs-lookup"><span data-stu-id="1c892-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="1c892-108">系統管理員必須為緊急位置識別號碼 (ELIN) 應用程式設定與緊急路由服務提供者 (ERSP)  () 或設定會話邊界控制器 (SBC) 的連接。</span><span class="sxs-lookup"><span data-stu-id="1c892-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="1c892-109">Contoso 在美國及美國以外地區設有辦公室：</span><span class="sxs-lookup"><span data-stu-id="1c892-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="1c892-110">在美國，Contoso 通話方案使用者可以使用動態位置路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="1c892-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="1c892-111">在美國以外，Contoso 有一些使用通話方案的網站，以及透過直接路由電話系統連結至其他網站。</span><span class="sxs-lookup"><span data-stu-id="1c892-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="1c892-112">緊急通話使用案例</span><span class="sxs-lookup"><span data-stu-id="1c892-112">Emergency calling use cases</span></span>

<span data-ttu-id="1c892-113">決定 Contoso 如何連接到電話後，Contoso 識別出下列緊急電話使用案例：</span><span class="sxs-lookup"><span data-stu-id="1c892-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="1c892-114">美國的通話方案使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="1c892-115">美國以外的通話方案使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="1c892-116">透過直接路由電話系統使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="1c892-117">美國的通話方案使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="1c892-118">當電話號碼需要與緊急位置相關聯時，有一些需求。</span><span class="sxs-lookup"><span data-stu-id="1c892-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="1c892-119">為了瞭解這些要求，Contoso 已審查 [通話方案考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="1c892-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="1c892-120">根據這些需求，Contoso 決定在將號碼指派給美國使用者時，將位置與電話號碼關聯。</span><span class="sxs-lookup"><span data-stu-id="1c892-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="1c892-121">美國以外的通話方案使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="1c892-122">為了瞭解電話號碼何時需要與緊急位置相關聯，Contoso 已審查通話  [方案考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="1c892-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="1c892-123">根據需求，Contoso 決定下列專案：</span><span class="sxs-lookup"><span data-stu-id="1c892-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="1c892-124">當號碼指派給加拿大的使用者時，Contoso 會將位置與電話號碼關聯。</span><span class="sxs-lookup"><span data-stu-id="1c892-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="1c892-125">當電話號碼從 Office 365或從另一個服務提供者或電信公司移轉時，Contoso 會指派緊急位置。</span><span class="sxs-lookup"><span data-stu-id="1c892-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="1c892-126">透過直接路由電話系統使用者</span><span class="sxs-lookup"><span data-stu-id="1c892-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="1c892-127">為了針對此使用案例規劃緊急路由，Contoso 已審查 [直接路由的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="1c892-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="1c892-128">由於直接路由使用者不會以與通話方案使用者相同的方式接收緊急電話，因此 Contoso 必須決定如何提供緊急電話。</span><span class="sxs-lookup"><span data-stu-id="1c892-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="1c892-129">直接路由可以連接到緊急路由服務提供者 (ERSP) 。</span><span class="sxs-lookup"><span data-stu-id="1c892-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="1c892-130">直接路由也可以有包含緊急位置識別號碼的 SBC (ELIN) 。</span><span class="sxs-lookup"><span data-stu-id="1c892-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="1c892-131">緊急路由服務提供者 (ERSP) 考慮</span><span class="sxs-lookup"><span data-stu-id="1c892-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="1c892-132">緊急路由服務提供者 (ERSP) 根據來電者的位置自動路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="1c892-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="1c892-133">如果緊急路由服務提供者已整合至直接路由部署，具有動態取得位置的緊急電話會自動路由至服務該位置的公用安全應答點 (PSAP) 點。</span><span class="sxs-lookup"><span data-stu-id="1c892-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="1c892-134">沒有動態取得位置的緊急電話會先經過篩選，以決定使用者的目前位置，然後再根據更新的位置將通話連接到適當的調度中心。</span><span class="sxs-lookup"><span data-stu-id="1c892-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="1c892-135">ELIN 考慮事項</span><span class="sxs-lookup"><span data-stu-id="1c892-135">ELIN considerations</span></span>

<span data-ttu-id="1c892-136">如果 SBC ELIN 應用程式已整合至直接路由部署，則需要執行其他組組步驟，將緊急位址與電話號碼建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1c892-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="1c892-137">Contoso 決定使用會話邊界控制器，其中包括 ELIN (緊急) 號碼。</span><span class="sxs-lookup"><span data-stu-id="1c892-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="1c892-138">安全電話台通知</span><span class="sxs-lookup"><span data-stu-id="1c892-138">Security desk notification</span></span>

<span data-ttu-id="1c892-139">Microsoft 通話方案及直接路由功能都提供在緊急通話時通知電話系統功能。</span><span class="sxs-lookup"><span data-stu-id="1c892-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="1c892-140">Contoso 已查看安全性中心通知中的詳細資料，以判斷這是否應在其辦公室進行配置</span><span class="sxs-lookup"><span data-stu-id="1c892-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="1c892-141">Contoso 決定使用安全電話台通知。</span><span class="sxs-lookup"><span data-stu-id="1c892-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="1c892-142">配置</span><span class="sxs-lookup"><span data-stu-id="1c892-142">Configuration</span></span> 

<span data-ttu-id="1c892-143">Contoso 遵循設定動態緊急 [電話的步驟](configure-dynamic-emergency-calling.md) 進行：</span><span class="sxs-lookup"><span data-stu-id="1c892-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="1c892-144">指派緊急位址</span><span class="sxs-lookup"><span data-stu-id="1c892-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="1c892-145">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="1c892-145">Configure network settings</span></span> 

- <span data-ttu-id="1c892-146">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="1c892-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="1c892-147">設定緊急政策</span><span class="sxs-lookup"><span data-stu-id="1c892-147">Configure emergency policies</span></span> 

- <span data-ttu-id="1c892-148">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="1c892-148">Enable users and sites</span></span> 

- <span data-ttu-id="1c892-149">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="1c892-149">Test emergency calling</span></span> 

<span data-ttu-id="1c892-150">在動態緊急電話配置完成之後，Contoso 需要將位置指派給適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="1c892-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="1c892-151">若要新增、變更或移除貴組織的緊急位置，Contoso 會遵循新增、變更或移除貴組織的緊急位置 [中的步驟](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="1c892-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="1c892-152">若要建立建築物、樓層和辦公室的位置，Contoso 遵循新增、變更或移除緊急位置位置 [中的步驟](add-change-remove-emergency-place-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="1c892-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="1c892-153">若要指派緊急位置，Contoso 遵循指派或變更使用者的緊急 [位置中的步驟](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1c892-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 