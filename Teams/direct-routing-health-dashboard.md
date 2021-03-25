---
title: 直接路由的健康情況儀表板
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用健康情況儀表板監控會話邊界控制器與直接路由之間的連接。
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122227"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="0a662-103">直接路由的健康情況儀表板</span><span class="sxs-lookup"><span data-stu-id="0a662-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="0a662-104">直接路由健康情況儀表板可讓您監控會話邊界控制器 (SBC) 與直接路由介面之間的連接。</span><span class="sxs-lookup"><span data-stu-id="0a662-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="0a662-105">您可以使用健康情況儀表板監控 SBC、電話語音，以及 SBC 與直接路由介面之間的網路參數相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0a662-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="0a662-106">這項資訊可協助找出問題，包括通話中斷的原因。</span><span class="sxs-lookup"><span data-stu-id="0a662-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="0a662-107">例如，如果 SBC 上的憑證已過期或網路問題，SBC 可能會停止傳送通話。</span><span class="sxs-lookup"><span data-stu-id="0a662-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span> <span data-ttu-id="0a662-108">請參閱 [系統管理員角色](using-admin-roles.md) ，以瞭解誰可以存取健康狀態儀表板。</span><span class="sxs-lookup"><span data-stu-id="0a662-108">See the [admin roles](using-admin-roles.md) to learn who has access to the health dashboard.</span></span>

<span data-ttu-id="0a662-109">健康情況儀表板會監控兩層資訊：</span><span class="sxs-lookup"><span data-stu-id="0a662-109">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="0a662-110">已連接 SBC 的整體健康情況</span><span class="sxs-lookup"><span data-stu-id="0a662-110">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="0a662-111">已連接 SBC 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0a662-111">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="0a662-112">您可以在 Microsoft Teams 和商務用 Skype 系統管理中心中查看健康狀態儀表板。</span><span class="sxs-lookup"><span data-stu-id="0a662-112">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>

## <a name="overall-health"></a><span data-ttu-id="0a662-113">整體健康情況</span><span class="sxs-lookup"><span data-stu-id="0a662-113">Overall health</span></span>

<span data-ttu-id="0a662-114">健康情況儀表板提供與連結 SBCs 整體健康情況相關的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="0a662-114">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![顯示健康狀態儀表板統計資料](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="0a662-116">**直接路由摘要** - 顯示在系統中註冊的 SBCs 總數。</span><span class="sxs-lookup"><span data-stu-id="0a662-116">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="0a662-117">註冊表示租使用者系統管理員使用 New-CsOnlinePSTNGateway 新增 SBC。</span><span class="sxs-lookup"><span data-stu-id="0a662-117">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="0a662-118">如果 SBC 是在 PowerShell 中新增，但從未連結過，健康情況儀表板會顯示為不健康狀態。</span><span class="sxs-lookup"><span data-stu-id="0a662-118">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="0a662-119">**SBC** - 配對 SBC 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0a662-119">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="0a662-120">網路 **效能比 (NER**) - NER 會測量已傳送的通話數與傳送給收件者的通話數，以測量網路進行通話的能力。</span><span class="sxs-lookup"><span data-stu-id="0a662-120">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="0a662-121">NER 會測量網路將通話傳送至遠端終端機的能力，但不包括導致通話拒絕的使用者動作。</span><span class="sxs-lookup"><span data-stu-id="0a662-121">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="0a662-122">如果收件者拒絕通話或將通話傳送至語音信箱，則通話會視為成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="0a662-122">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="0a662-123">這表示接聽訊息、忙碌訊號或沒有接聽的鈴聲都被視為成功的通話。</span><span class="sxs-lookup"><span data-stu-id="0a662-123">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span>
  
   <span data-ttu-id="0a662-124">例如，假設直接路由傳送呼叫給 SBC，而 SBC 會返回 SIP 程式碼「504 Server Time out - 伺服器嘗試存取另一個伺服器以嘗試處理要求，而且沒有收到提示回應」。</span><span class="sxs-lookup"><span data-stu-id="0a662-124">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="0a662-125">此回應表示 SBC 端有問題，這將會減少此 SBC 的健康儀表板上的 NER。</span><span class="sxs-lookup"><span data-stu-id="0a662-125">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span>
  
   <span data-ttu-id="0a662-126">由於您採取的動作可能取決於受影響的通話數量，因此健康情況儀表板會顯示分析的通話數，以計算參數。</span><span class="sxs-lookup"><span data-stu-id="0a662-126">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="0a662-127">如果通話數小於 100，NER 可能相當低，但仍然正常。</span><span class="sxs-lookup"><span data-stu-id="0a662-127">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span>

   <span data-ttu-id="0a662-128">用來計算 NER 的公式為：</span><span class="sxs-lookup"><span data-stu-id="0a662-128">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="0a662-129">NER = 100 x (通話 + 使用者忙碌 + 響鈴沒有接聽 + 終端機拒絕) /通話總數</span><span class="sxs-lookup"><span data-stu-id="0a662-129">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

- <span data-ttu-id="0a662-130">**平均通話持續時間** - 關於平均通話持續時間的資訊可協助監控通話品質。</span><span class="sxs-lookup"><span data-stu-id="0a662-130">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="0a662-131">1：1 PSTN 通話的平均持續時間為 4 到 5 分鐘。</span><span class="sxs-lookup"><span data-stu-id="0a662-131">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="0a662-132">不過，每家公司的平均值可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0a662-132">However, for each company, this average can differ.</span></span>  <span data-ttu-id="0a662-133">Microsoft 建議為貴公司的平均通話持續時間建立比較基準。</span><span class="sxs-lookup"><span data-stu-id="0a662-133">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="0a662-134">如果此參數明顯低於比較基準，表示您的使用者有通話品質或可靠性問題，且掛斷時間早于平常。</span><span class="sxs-lookup"><span data-stu-id="0a662-134">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="0a662-135">如果您開始看到極低的平均通話持續時間 ，例如 15 秒，來電者可能會因為服務無法可靠地執行而掛斷電話。</span><span class="sxs-lookup"><span data-stu-id="0a662-135">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span>

   <span data-ttu-id="0a662-136">由於您採取的動作可能取決於受影響的通話數量，因此健康情況儀表板會顯示分析的通話數，以計算參數。</span><span class="sxs-lookup"><span data-stu-id="0a662-136">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="0a662-137">**TLS** 連接狀態 - TLS (傳輸層安全性) 連接會顯示直接路由與 SBC 之間的 TLS 連接狀態。</span><span class="sxs-lookup"><span data-stu-id="0a662-137">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="0a662-138">健康狀態儀表板也會分析憑證到期日，並警告憑證是否設定在 30 天內到期，以便系統管理員在服務中斷前更新憑證。</span><span class="sxs-lookup"><span data-stu-id="0a662-138">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="0a662-139">按一下警告訊息，即可在右邊的快顯視窗中查看詳細的問題描述，以及修正問題的建議。</span><span class="sxs-lookup"><span data-stu-id="0a662-139">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="0a662-140">**SIP 選項狀態** – 根據預設，SBC 會每分鐘傳送選項訊息。</span><span class="sxs-lookup"><span data-stu-id="0a662-140">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="0a662-141">此組配置可能會因不同的 SBC 廠商而異。</span><span class="sxs-lookup"><span data-stu-id="0a662-141">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="0a662-142">直接路由會警告未傳送或未進行配置的 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="0a662-142">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="0a662-143">有關 SIP 選項監控的詳細資訊，以及 SBC 可標示為無法運作的情況，請參閱監控和疑難排解 [直接路由](direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="0a662-143">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="0a662-144">**詳細的 SIP 選項狀態** - 除了顯示 SIP 選項流程有問題之外，健康情況儀表板也會提供錯誤的詳細描述。</span><span class="sxs-lookup"><span data-stu-id="0a662-144">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="0a662-145">您可以按一下 「警告」訊息來存取描述。</span><span class="sxs-lookup"><span data-stu-id="0a662-145">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="0a662-146">右側快顯視窗會顯示詳細的錯誤描述。</span><span class="sxs-lookup"><span data-stu-id="0a662-146">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="0a662-147">SIP 選項狀態訊息的可能值如下：</span><span class="sxs-lookup"><span data-stu-id="0a662-147">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="0a662-148">使用中 - SBC 為使用中--Microsoft Direct 路由服務會定期看到選項。</span><span class="sxs-lookup"><span data-stu-id="0a662-148">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="0a662-149">警告，沒有 SIP 選項 - 會話邊界控制器存在於資料庫中 (系統管理員使用 New-CsOnlinePSTNGateway 命令建立) 。</span><span class="sxs-lookup"><span data-stu-id="0a662-149">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="0a662-150">它已配置為傳送 SIP 選項，但直接路由服務從未看到從此 SBC 返回的 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="0a662-150">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="0a662-151">警告，未配置 SIP 訊息 - 未開啟使用 SIP 選項的主幹監控。</span><span class="sxs-lookup"><span data-stu-id="0a662-151">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="0a662-152">Microsoft 通話系統使用 SIP 選項和傳輸層安全性 (TLS) 握手監控，以在應用程式層級偵測連接的會話邊界控制器 (SBC) 健康情況。</span><span class="sxs-lookup"><span data-stu-id="0a662-152">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="0a662-153">如果這個主幹可以在網路層級 (ping) ，但憑證已過期或 SIP 堆疊無法工作，就會發生問題。</span><span class="sxs-lookup"><span data-stu-id="0a662-153">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="0a662-154">為了協助及早找出這類問題，Microsoft 建議啟用傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="0a662-154">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="0a662-155">檢查您的 SBC 製造商檔以設定傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="0a662-155">Check your SBC manufacturer documentation to configure sending SIP options.</span></span>

- <span data-ttu-id="0a662-156">**並行通話容量** - 您可以使用 -MaxConcurrentSessions 參數的 New 或 Set-CsOnlinePSTNGateway 命令，指定 SBC 可以處理的並行通話限制。</span><span class="sxs-lookup"><span data-stu-id="0a662-156">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="0a662-157">此參數會計算直接路由使用特定 SBC 傳送或接聽的通話數，並將它與限制集進行比較。</span><span class="sxs-lookup"><span data-stu-id="0a662-157">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="0a662-158">注意：如果 SBC 也處理不同 PBX 的通話，此號碼不會顯示實際的同時通話。</span><span class="sxs-lookup"><span data-stu-id="0a662-158">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>

## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="0a662-159">每個 SBC 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0a662-159">Detailed information for each SBC</span></span>

<span data-ttu-id="0a662-160">您也可以查看特定 SBC 的詳細資訊，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="0a662-160">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![健康情況儀表板 SBC 詳細資料](media/direct-routing-dashboard-SBC-detail1.png)

<span data-ttu-id="0a662-162">詳細視圖顯示下列其他參數：</span><span class="sxs-lookup"><span data-stu-id="0a662-162">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="0a662-163">**TLS 連接狀態** – 這是與 「整體健康情況」頁面上相同的度量;</span><span class="sxs-lookup"><span data-stu-id="0a662-163">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="0a662-164">**TLS Connectivity 上次狀態** ： 顯示 SBC 與直接路由服務建立 TLS 連接的時間;</span><span class="sxs-lookup"><span data-stu-id="0a662-164">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="0a662-165">**SIP 選項狀態** – 與 「整體健康情況」頁面上的相同度量單位。</span><span class="sxs-lookup"><span data-stu-id="0a662-165">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="0a662-166">**上次已檢查 SIP 選項** ： 上次收到 SIP 選項的時間。</span><span class="sxs-lookup"><span data-stu-id="0a662-166">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="0a662-167">**SBC 狀態** – SBC 的整體狀態，以所有受監控的參數為基礎。</span><span class="sxs-lookup"><span data-stu-id="0a662-167">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="0a662-168">**同時通話**- 顯示 SBC 已處理的並行通話數。</span><span class="sxs-lookup"><span data-stu-id="0a662-168">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="0a662-169">這項資訊很實用，可預測您需要的並行通道數目，並查看趨勢。</span><span class="sxs-lookup"><span data-stu-id="0a662-169">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="0a662-170">您可以根據天數滑動資料，以及輸入/ (/所有) 。</span><span class="sxs-lookup"><span data-stu-id="0a662-170">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="0a662-171">**網路參數** - 所有網路參數都是從直接路由介面到會話邊界控制器測量。</span><span class="sxs-lookup"><span data-stu-id="0a662-171">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="0a662-172">有關建議值的資訊，請參閱準備貴組織的 [Microsoft Teams](./prepare-network.md)網路，並查看客戶邊緣至 Microsoft Edge 的建議值。</span><span class="sxs-lookup"><span data-stu-id="0a662-172">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](./prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="0a662-173">抖動 – 是使用 RTCP 與 RTP 控制通訊協定 (計算兩個端點之間網路傳播延遲時間變化的毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="0a662-173">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="0a662-174">封包遺失 – 是未送達的封包量值;這是在兩個端點之間計算。</span><span class="sxs-lookup"><span data-stu-id="0a662-174">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="0a662-175">延遲 - (也稱為往返時間) 是訊號的接收時間長度，加上接收該訊號所花的時間長度。</span><span class="sxs-lookup"><span data-stu-id="0a662-175">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="0a662-176">此延遲時間是由訊號兩點之間的傳播時間所組成。</span><span class="sxs-lookup"><span data-stu-id="0a662-176">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="0a662-177">您可以根據天數滑動資料，以及輸入/ (/所有) 。</span><span class="sxs-lookup"><span data-stu-id="0a662-177">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="0a662-178">**網路效能比** - 這是出現在整體健康情況儀表板上的相同參數，但可以選擇以時間序列或通話方向來分割資料。</span><span class="sxs-lookup"><span data-stu-id="0a662-178">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>