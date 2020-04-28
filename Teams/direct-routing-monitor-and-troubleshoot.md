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
description: 瞭解如何監視和疑難排解直接路由設定，包括會話邊界控制器、直接路由元件，以及電信 trunks。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901908"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="be0e9-103">監視和疑難排解直接路由</span><span class="sxs-lookup"><span data-stu-id="be0e9-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="be0e9-104">本文說明如何監視和疑難排解直接路由設定。</span><span class="sxs-lookup"><span data-stu-id="be0e9-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="be0e9-105">使用直接路由撥打及接聽電話的功能，包括下列元件：</span><span class="sxs-lookup"><span data-stu-id="be0e9-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="be0e9-106">會話邊界控制器（SBCs）</span><span class="sxs-lookup"><span data-stu-id="be0e9-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="be0e9-107">Microsoft 雲端中的直接路由元件</span><span class="sxs-lookup"><span data-stu-id="be0e9-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="be0e9-108">電信 trunks</span><span class="sxs-lookup"><span data-stu-id="be0e9-108">Telecom trunks</span></span> 

<span data-ttu-id="be0e9-109">如果您遇到疑難排解問題，您可以在您的 SBC 轉銷商或 Microsoft 開啟支援案例。</span><span class="sxs-lookup"><span data-stu-id="be0e9-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="be0e9-110">Microsoft 正在努力提供更多工具以進行疑難排解及監視。</span><span class="sxs-lookup"><span data-stu-id="be0e9-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="be0e9-111">請定期查看檔以取得更新。</span><span class="sxs-lookup"><span data-stu-id="be0e9-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="be0e9-112">使用會話初始通訊協定（SIP）選項訊息監視會話邊界控制器的可用性</span><span class="sxs-lookup"><span data-stu-id="be0e9-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="be0e9-113">[直接路由]：使用由會話邊界控制器傳送的 SIP 選項來監視 SBC 健康情況。</span><span class="sxs-lookup"><span data-stu-id="be0e9-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="be0e9-114">租使用者管理員無需執行任何動作，即可啟用 SIP 選項監視。</span><span class="sxs-lookup"><span data-stu-id="be0e9-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="be0e9-115">建立路由決定時，會考慮收集的資訊。</span><span class="sxs-lookup"><span data-stu-id="be0e9-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="be0e9-116">例如，如果您針對特定使用者提供數種可路由通話的 SBCs，直向路由會考慮從每個 SBC 接收的 SIP 選項資訊來判斷路由。</span><span class="sxs-lookup"><span data-stu-id="be0e9-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="be0e9-117">下圖顯示配置範例：</span><span class="sxs-lookup"><span data-stu-id="be0e9-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 選項配置範例](media/sip-options-config-example.png)

<span data-ttu-id="be0e9-119">當使用者撥打電話給 number + 1 425 \<時，任何七位數>，直向路由會評估路由。</span><span class="sxs-lookup"><span data-stu-id="be0e9-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="be0e9-120">路由中有兩個 SBCs： sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="be0e9-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="be0e9-121">兩個 SBCs 在路由中都有相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="be0e9-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="be0e9-122">在挑選 SBC 前，路由機制會根據 SBC 每次傳送 SIP 選項的時間來評估 SBCs 的健康情況。</span><span class="sxs-lookup"><span data-stu-id="be0e9-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="be0e9-123">如果傳送通話時的統計資料顯示 SBC 每分鐘傳送選項，則會被視為健康情況。</span><span class="sxs-lookup"><span data-stu-id="be0e9-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="be0e9-124">撥打電話時，會套用下列邏輯：</span><span class="sxs-lookup"><span data-stu-id="be0e9-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="be0e9-125">SBC 已成對 11:00 AM。</span><span class="sxs-lookup"><span data-stu-id="be0e9-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="be0e9-126">SBC 會在 11:01 AM、11:02 AM 等的時間傳送選項。</span><span class="sxs-lookup"><span data-stu-id="be0e9-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="be0e9-127">在11:15，使用者撥打電話，而路由機制則會選取這個 SBC。</span><span class="sxs-lookup"><span data-stu-id="be0e9-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="be0e9-128">[直接傳送] 會將週期性間隔選項分為三次（定期間隔為1分鐘）。</span><span class="sxs-lookup"><span data-stu-id="be0e9-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="be0e9-129">如果在過去三分鐘內傳送選項，則會認為 SBC 健康。</span><span class="sxs-lookup"><span data-stu-id="be0e9-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="be0e9-130">如果範例中的 SBC 在 11:12 AM 和 11:15 AM 之間（撥打的時間），則會被視為健康情況。</span><span class="sxs-lookup"><span data-stu-id="be0e9-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="be0e9-131">如果不是，則 SBC 將會從路由中降級。</span><span class="sxs-lookup"><span data-stu-id="be0e9-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="be0e9-132">[降級] 表示不會先嘗試使用 SBC。</span><span class="sxs-lookup"><span data-stu-id="be0e9-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="be0e9-133">例如，我們有同等優先順序的 sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="be0e9-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="be0e9-134">如果 sbc1.contoso.com 未依先前所述的定期間隔傳送 SIP 選項，則會將它降級。</span><span class="sxs-lookup"><span data-stu-id="be0e9-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="be0e9-135">接著，sbc2.contoso.com 通話的嘗試。</span><span class="sxs-lookup"><span data-stu-id="be0e9-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="be0e9-136">如果 sbc2 無法傳送通話，則會在產生失敗前再次嘗試 sbc1.contoso.com （降級）。</span><span class="sxs-lookup"><span data-stu-id="be0e9-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="be0e9-137">如果在一個路線中有兩個（或多個） SBCs 是正常且相等的，則會套用 Fisher Yates 隨機播放，在 SBCs 間散佈通話。</span><span class="sxs-lookup"><span data-stu-id="be0e9-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="be0e9-138">監控通話品質分析儀表板和 SBC 記錄</span><span class="sxs-lookup"><span data-stu-id="be0e9-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="be0e9-139">在某些情況下，特別是在初次配對期間，可能會發生有關 SBCs 或直接路由服務的錯誤配置問題。</span><span class="sxs-lookup"><span data-stu-id="be0e9-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="be0e9-140">您可以使用下列工具來監視您的設定：</span><span class="sxs-lookup"><span data-stu-id="be0e9-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="be0e9-141">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="be0e9-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="be0e9-142">SBC 記錄</span><span class="sxs-lookup"><span data-stu-id="be0e9-142">SBC logs</span></span> 

<span data-ttu-id="be0e9-143">直連路由服務會有一個描述為呼叫分析或 SBC 記錄的明顯的錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="be0e9-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="be0e9-144">通話品質儀表板提供通話品質與可靠性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be0e9-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="be0e9-145">若要進一步瞭解如何使用通話分析進行疑難排解，請參閱[開啟與使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)，並[使用呼叫分析來排查不佳的通話品質](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)問題。</span><span class="sxs-lookup"><span data-stu-id="be0e9-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="be0e9-146">如果通話失敗，通話分析提供標準 SIP 代碼，協助您進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="be0e9-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![通話失敗的 SIP 代碼範例](media/failed-response-code.png)

<span data-ttu-id="be0e9-148">不過，通話分析只會在來電到達直接路由的內部元件並失敗時加以協助。</span><span class="sxs-lookup"><span data-stu-id="be0e9-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="be0e9-149">如果 SBC 配對發生問題，或 SIP 「Invite」遭到拒絕的問題（例如，幹線 FQDN 的名稱未正確設定），通話分析將無法提供協助。</span><span class="sxs-lookup"><span data-stu-id="be0e9-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="be0e9-150">在這種情況下，請參閱 SBC 記錄。</span><span class="sxs-lookup"><span data-stu-id="be0e9-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="be0e9-151">直接路由會將問題的詳細描述傳送到 SBCs;您可以從 SBC 記錄中讀取這些問題。</span><span class="sxs-lookup"><span data-stu-id="be0e9-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
