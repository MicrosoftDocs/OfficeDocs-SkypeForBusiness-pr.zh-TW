---
title: 監視和疑難排解直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何監控和疑難排解直接路由組組，包括會話邊界控制器、直接路由元件和電信主幹。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121401"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="6d374-103">監視和疑難排解直接路由</span><span class="sxs-lookup"><span data-stu-id="6d374-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="6d374-104">本文將說明如何監控和疑難排解您的直接路由配置。</span><span class="sxs-lookup"><span data-stu-id="6d374-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="6d374-105">使用直接路由撥打和接聽電話的能力涉及下列元件：</span><span class="sxs-lookup"><span data-stu-id="6d374-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="6d374-106">會話邊界控制器 (SBC) </span><span class="sxs-lookup"><span data-stu-id="6d374-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="6d374-107">Microsoft Cloud 中的直接路由元件</span><span class="sxs-lookup"><span data-stu-id="6d374-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="6d374-108">電信主幹</span><span class="sxs-lookup"><span data-stu-id="6d374-108">Telecom trunks</span></span> 

<span data-ttu-id="6d374-109">如果您有疑難排解問題，您可以向 SBC 廠商或 Microsoft 開啟支援案例。</span><span class="sxs-lookup"><span data-stu-id="6d374-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="6d374-110">Microsoft 正在努力提供更多疑難排解和監控工具。</span><span class="sxs-lookup"><span data-stu-id="6d374-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="6d374-111">請定期檢查檔以尋找更新。</span><span class="sxs-lookup"><span data-stu-id="6d374-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="6d374-112">使用會話初始通訊協定監控會話邊界控制器的可用性 (SIP) 訊息</span><span class="sxs-lookup"><span data-stu-id="6d374-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="6d374-113">直接路由使用會話邊界控制器傳送的 SIP 選項來監控 SBC 健康情況。</span><span class="sxs-lookup"><span data-stu-id="6d374-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="6d374-114">租使用者系統管理員不需要執行任何動作來啟用 SIP 選項監控。</span><span class="sxs-lookup"><span data-stu-id="6d374-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="6d374-115">在做出路由決策時，會考慮收集的資訊。</span><span class="sxs-lookup"><span data-stu-id="6d374-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="6d374-116">例如，如果針對特定使用者，有幾個 SBC 可以路由通話，則直接路由會考慮從每個 SBC 收到的 SIP 選項資訊，以決定路由。</span><span class="sxs-lookup"><span data-stu-id="6d374-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="6d374-117">下圖顯示組組範例：</span><span class="sxs-lookup"><span data-stu-id="6d374-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 選項群組組範例](media/sip-options-config-example.png)

<span data-ttu-id="6d374-119">當使用者撥打號碼 +1 425 \<any seven digits> 時，直接路由會評估路由。</span><span class="sxs-lookup"><span data-stu-id="6d374-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="6d374-120">路由有兩個 SBC：sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6d374-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="6d374-121">這兩個 SBC 在路由中具有相等的優先順序。</span><span class="sxs-lookup"><span data-stu-id="6d374-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="6d374-122">挑選 SBC 之前，路由機制會根據 SBC 上次傳送 SIP 選項的時間，評估 SBC 的健康情況。</span><span class="sxs-lookup"><span data-stu-id="6d374-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="6d374-123">如果傳送通話時的統計資料顯示 SBC 每分鐘傳送選項，則 SBC 會視為健康狀態。</span><span class="sxs-lookup"><span data-stu-id="6d374-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="6d374-124">進行通話時，會採用下列邏輯：</span><span class="sxs-lookup"><span data-stu-id="6d374-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="6d374-125">SBC 在上午 11：00 配對。</span><span class="sxs-lookup"><span data-stu-id="6d374-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="6d374-126">SBC 會于上午 11：01、上午 11：02 等傳送選項。</span><span class="sxs-lookup"><span data-stu-id="6d374-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="6d374-127">在 11：15，使用者進行通話，而路由機制會選取此 SBC。</span><span class="sxs-lookup"><span data-stu-id="6d374-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="6d374-128">直接路由會採用三次定期間隔選項 (而一般間隔為一分鐘) 。</span><span class="sxs-lookup"><span data-stu-id="6d374-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="6d374-129">如果選項是在過去三分鐘內傳送的，則 SBC 會視為健康狀態。</span><span class="sxs-lookup"><span data-stu-id="6d374-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="6d374-130">如果範例中的 SBC 在上午 11：12 到上午 11：15 (通話時間) 之間，會被視為健康狀態。</span><span class="sxs-lookup"><span data-stu-id="6d374-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="6d374-131">如果沒有，SBC 將會從路由降級。</span><span class="sxs-lookup"><span data-stu-id="6d374-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="6d374-132">降級表示不會先嘗試 SBC。</span><span class="sxs-lookup"><span data-stu-id="6d374-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="6d374-133">例如，我們有一 sbc1.contoso.com sbc2.contoso.com 優先順序。</span><span class="sxs-lookup"><span data-stu-id="6d374-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="6d374-134">如果 sbc1.contoso.com 未如先前所述定期傳送 SIP 選項，系統即會降級。</span><span class="sxs-lookup"><span data-stu-id="6d374-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="6d374-135">接下來，sbc2.contoso.com 通話。</span><span class="sxs-lookup"><span data-stu-id="6d374-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="6d374-136">如果 sbc2.contoso.con 無法傳遞通話，系統 sbc1.contoso.com (降級) 再試一次，然後再產生失敗。</span><span class="sxs-lookup"><span data-stu-id="6d374-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="6d374-137">如果 (一個路由) 兩個或多個 SBCs 視為健康且相等，Fisher-Yates隨機播放會用於在 SBCs 之間分配通話。</span><span class="sxs-lookup"><span data-stu-id="6d374-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="6d374-138">監控通話品質分析儀表板和 SBC 記錄</span><span class="sxs-lookup"><span data-stu-id="6d374-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="6d374-139">在某些情況下，尤其是在初始配對期間，SBCs 或直接路由服務可能發生配置錯誤的問題。</span><span class="sxs-lookup"><span data-stu-id="6d374-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="6d374-140">您可以使用下列工具來監控您的組組：</span><span class="sxs-lookup"><span data-stu-id="6d374-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="6d374-141">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="6d374-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="6d374-142">SBC 記錄</span><span class="sxs-lookup"><span data-stu-id="6d374-142">SBC logs</span></span> 

<span data-ttu-id="6d374-143">直接路由服務有非常描述性的錯誤碼，會報告給通話分析或 SBC 記錄。</span><span class="sxs-lookup"><span data-stu-id="6d374-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="6d374-144">通話品質儀表板提供有關通話品質和可靠性的資訊。</span><span class="sxs-lookup"><span data-stu-id="6d374-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="6d374-145">若要深入瞭解如何使用通話分析疑難排解問題，請參閱開啟並使用 [Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) 和商務用 Skype Online 的通話品質儀表板，以及使用通話分析來疑難排解通話品質 [不佳的問題](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。</span><span class="sxs-lookup"><span data-stu-id="6d374-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="6d374-146">如果通話失敗，通話分析會提供標準 SIP 代碼，可協助進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="6d374-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![通話失敗範例 SIP 代碼](media/failed-response-code.png)

<span data-ttu-id="6d374-148">不過，通話分析只有在通話到達直接路由的內部元件並失敗時，才能有所説明。</span><span class="sxs-lookup"><span data-stu-id="6d374-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="6d374-149">如果 SBC 配對發生問題，或 SIP "Invite" 遭到拒絕的問題 (例如，主幹 FQDN 的名稱未正確) ，通話分析將無法解決問題。</span><span class="sxs-lookup"><span data-stu-id="6d374-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="6d374-150">在此案例中，請參閱 SBC 記錄。</span><span class="sxs-lookup"><span data-stu-id="6d374-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="6d374-151">直接路由會傳送問題的詳細描述給 SBC;這些問題可以從 SBC 記錄中讀取。</span><span class="sxs-lookup"><span data-stu-id="6d374-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>