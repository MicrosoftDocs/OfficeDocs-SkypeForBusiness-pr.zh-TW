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
description: 瞭解如何使用健康情況儀表板監視會話邊界控制器與直接路由之間的連接。
ms.openlocfilehash: 0424f24e323928f487e8b43ce72e51602f9eab52
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572198"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="9b19c-103">直接路由的健康情況儀表板</span><span class="sxs-lookup"><span data-stu-id="9b19c-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="9b19c-104">[健康] 儀表板的 [直接路由] 可讓您監視會話邊界控制器（SBC）與直接路由介面之間的連接。</span><span class="sxs-lookup"><span data-stu-id="9b19c-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="9b19c-105">使用 Health 儀表板，您可以監視您的 SBC、電話語音的相關資訊，以及您的 SBC 與直接路由介面之間的網路參數。</span><span class="sxs-lookup"><span data-stu-id="9b19c-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="9b19c-106">此資訊可協助您找出問題，包括中斷通話的原因。</span><span class="sxs-lookup"><span data-stu-id="9b19c-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="9b19c-107">例如，如果 SBC 上的憑證已過期或網路有問題，SBC 可能會停止傳送通話。</span><span class="sxs-lookup"><span data-stu-id="9b19c-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span>  

<span data-ttu-id="9b19c-108">健康情況儀表板會監視兩層的資訊：</span><span class="sxs-lookup"><span data-stu-id="9b19c-108">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="9b19c-109">連線半形的整體健康情況</span><span class="sxs-lookup"><span data-stu-id="9b19c-109">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="9b19c-110">連線的 SBCs 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9b19c-110">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="9b19c-111">您可以在 Microsoft [團隊] 和 [商務用 Skype 系統管理中心] 中查看健康情況儀表板。</span><span class="sxs-lookup"><span data-stu-id="9b19c-111">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>


## <a name="overall-health"></a><span data-ttu-id="9b19c-112">整體健康情況</span><span class="sxs-lookup"><span data-stu-id="9b19c-112">Overall health</span></span>

<span data-ttu-id="9b19c-113">健康情況儀表板提供下列與連接的 SBCs 整體健康情況相關的資訊：</span><span class="sxs-lookup"><span data-stu-id="9b19c-113">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![顯示健康情況儀表板統計資料](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="9b19c-115">**直接路由摘要**-顯示在系統中註冊的 SBCs 總數。</span><span class="sxs-lookup"><span data-stu-id="9b19c-115">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="9b19c-116">[註冊] 表示租使用者管理員使用 [New-CsOnlinePSTNGateway] 命令新增一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="9b19c-116">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="9b19c-117">如果 SBC 是在 PowerShell 中新增，但從未連線，健康情況儀表板會以不正常的狀態顯示它。</span><span class="sxs-lookup"><span data-stu-id="9b19c-117">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="9b19c-118">**Sbc** -成對式 SBC 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9b19c-118">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="9b19c-119">**網路效能比率（NER）** -NER 利用傳送給收件者的通話次數，來衡量網路的傳送呼叫能力。</span><span class="sxs-lookup"><span data-stu-id="9b19c-119">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="9b19c-120">NER 會測量網路將呼叫傳送到最遠端終端的能力，不包括導致呼叫拒絕的使用者動作。</span><span class="sxs-lookup"><span data-stu-id="9b19c-120">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="9b19c-121">如果收件者拒絕通話或將來電傳送至語音信箱，通話會算作成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="9b19c-121">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="9b19c-122">這表示答案訊息、占線信號或沒有應答的鈴聲全都被認為是成功的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b19c-122">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span> 
  
   <span data-ttu-id="9b19c-123">例如，假設直接路由傳送給 SBC，且 SBC 傳回 SIP 代碼 "504 伺服器超時-伺服器嘗試存取另一個伺服器，以嘗試處理要求且沒有收到提示回應"。</span><span class="sxs-lookup"><span data-stu-id="9b19c-123">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="9b19c-124">此回應表示 SBC 端出現問題，這會減少此 SBC 的健康情況儀表板上的 NER。</span><span class="sxs-lookup"><span data-stu-id="9b19c-124">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span> 
  
   <span data-ttu-id="9b19c-125">因為您所採取的動作可能會視受影響的通話數量而定，所以健康情況儀表板會顯示已分析多少通話來計算參數。</span><span class="sxs-lookup"><span data-stu-id="9b19c-125">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="9b19c-126">如果通話數量小於100，則 NER 可能相當低，但仍正常運作。</span><span class="sxs-lookup"><span data-stu-id="9b19c-126">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span> 

   <span data-ttu-id="9b19c-127">用來計算 NER 的公式是：</span><span class="sxs-lookup"><span data-stu-id="9b19c-127">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="9b19c-128">NER = 接聽電話 + 使用者忙碌 + 環沒有應答 + 終端拒絕 Seizures x 100</span><span class="sxs-lookup"><span data-stu-id="9b19c-128">NER = Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures x 100</span></span>

 
- <span data-ttu-id="9b19c-129">**平均通話持續時間**-有關平均通話持續時間的資訊可協助您監控通話品質。</span><span class="sxs-lookup"><span data-stu-id="9b19c-129">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="9b19c-130">1:1 PSTN 通話的平均持續時間是四到五分鐘。</span><span class="sxs-lookup"><span data-stu-id="9b19c-130">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="9b19c-131">不過，對於每個公司而言，這個平均值可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="9b19c-131">However, for each company, this average can differ.</span></span>  <span data-ttu-id="9b19c-132">Microsoft 建議為您的公司建立平均通話持續時間的比較基準。</span><span class="sxs-lookup"><span data-stu-id="9b19c-132">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="9b19c-133">如果此參數明顯在比較基準下方，可能表示您的使用者遇到通話品質或可靠性的問題，且即將掛斷。</span><span class="sxs-lookup"><span data-stu-id="9b19c-133">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="9b19c-134">如果您開始查看極低的平均通話持續時間（例如15秒），呼叫者可能會掛斷，因為您的服務無法可靠執行。</span><span class="sxs-lookup"><span data-stu-id="9b19c-134">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span> 

   <span data-ttu-id="9b19c-135">因為您所採取的動作可能會視受影響的通話數量而定，所以健康情況儀表板會顯示已分析多少通話來計算參數。</span><span class="sxs-lookup"><span data-stu-id="9b19c-135">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="9b19c-136">**Tls 線上狀態**-TLS （傳輸層安全性）連線顯示直接路由與 SBC 之間 TLS 連接的狀態。</span><span class="sxs-lookup"><span data-stu-id="9b19c-136">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="9b19c-137">[健康情況儀表板] 也會分析憑證到期日，並在30天內將憑證設定為過期，讓系統管理員在服務中斷前就能續約憑證。</span><span class="sxs-lookup"><span data-stu-id="9b19c-137">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="9b19c-138">按一下警告訊息時，您可以在右側的快顯視窗中看到詳細的問題描述，以及如何修正問題的建議。</span><span class="sxs-lookup"><span data-stu-id="9b19c-138">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="9b19c-139">**SIP 選項狀態**–根據預設，SBC 會每分鐘傳送一次選項訊息。</span><span class="sxs-lookup"><span data-stu-id="9b19c-139">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="9b19c-140">這個設定可能會因不同的 SBC 廠商而有所不同。</span><span class="sxs-lookup"><span data-stu-id="9b19c-140">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="9b19c-141">如果 SIP 選項未傳送或未設定，直接傳送就會發出警告。</span><span class="sxs-lookup"><span data-stu-id="9b19c-141">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="9b19c-142">如需有關 SIP 選項監控的詳細資訊，以及當 SBC 可以標示為無法正常運作時的情況，請參閱[直接路由的監視與疑難排解](direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="9b19c-142">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="9b19c-143">[**詳細 SIP 選項] 狀態**-除了顯示 [SIP 選項] 流程有問題之外，健康情況儀表板也提供錯誤的詳細描述。</span><span class="sxs-lookup"><span data-stu-id="9b19c-143">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="9b19c-144">您可以按一下 [警告] 訊息來存取描述。</span><span class="sxs-lookup"><span data-stu-id="9b19c-144">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="9b19c-145">右側的快顯視窗會顯示詳細的錯誤描述。</span><span class="sxs-lookup"><span data-stu-id="9b19c-145">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="9b19c-146">SIP 選項狀態訊息的可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9b19c-146">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="9b19c-147">[作用中]-SBC 是使用中的--Microsoft Direct 路由服務會看到定期流入的選項。</span><span class="sxs-lookup"><span data-stu-id="9b19c-147">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="9b19c-148">警告，無 SIP 選項-資料庫中存在會話邊界控制器（由您的系統管理員使用命令 New CsOnlinePSTNGateway）。</span><span class="sxs-lookup"><span data-stu-id="9b19c-148">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="9b19c-149">它被設定為傳送 SIP 選項，但直接路由服務從未看到從這個 SBC 傳回的 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="9b19c-149">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="9b19c-150">警告，SIP 訊息沒有設定-沒有開啟 [使用 SIP 選項進行中繼監視]。</span><span class="sxs-lookup"><span data-stu-id="9b19c-150">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="9b19c-151">Microsoft 通話系統會使用 SIP 選項和傳輸層安全性（TLS）握手，在應用程式層級偵測連接會話框線控制器（SBCs）的健康情況。</span><span class="sxs-lookup"><span data-stu-id="9b19c-151">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="9b19c-152">如果您無法在網路層級（透過 ping）達到這個幹線，但憑證已過期或 SIP 堆疊無法運作，就會發生問題。</span><span class="sxs-lookup"><span data-stu-id="9b19c-152">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="9b19c-153">為了協助儘早找出這類問題，Microsoft 建議您啟用傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="9b19c-153">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="9b19c-154">請查看您的 SBC 製造商檔，以設定傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="9b19c-154">Check your SBC manufacturer documentation to configure sending SIP options.</span></span> 

- <span data-ttu-id="9b19c-155">**併發通話容量**-您可以使用新的 CsOnlinePSTNGateway 命令（含-MaxConcurrentSessions 參數）來指定 SBC 可以處理的併發通話限制。</span><span class="sxs-lookup"><span data-stu-id="9b19c-155">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="9b19c-156">這個參數會計算使用特定的 SBC 直接路由來傳送或接收的通話數，並將它與設定的限制進行比較。</span><span class="sxs-lookup"><span data-stu-id="9b19c-156">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="9b19c-157">注意：如果 SBC 也處理不同 Pbx 的呼叫，這個數位不會顯示實際的併發通話。</span><span class="sxs-lookup"><span data-stu-id="9b19c-157">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>


## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="9b19c-158">每個 SBC 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9b19c-158">Detailed information for each SBC</span></span>

<span data-ttu-id="9b19c-159">您也可以查看特定 SBC 的詳細資訊，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="9b19c-159">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![健康儀表板 SBC 詳細資料](media/direct-routing-dashboard-SBC-detail1.png)


<span data-ttu-id="9b19c-161">[詳細] 視圖會顯示下列其他參數：</span><span class="sxs-lookup"><span data-stu-id="9b19c-161">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="9b19c-162">**TLS 線上狀態**-這與「整體健康情況」頁面上的規格相同;</span><span class="sxs-lookup"><span data-stu-id="9b19c-162">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="9b19c-163">**TLS 連線上次狀態**–顯示 SBC 與直接路由服務進行 TLS 連線的時間;</span><span class="sxs-lookup"><span data-stu-id="9b19c-163">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="9b19c-164">**SIP 選項狀態**–與「整體健康情況」頁面上的相同指標。</span><span class="sxs-lookup"><span data-stu-id="9b19c-164">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="9b19c-165">**Sip 選項 [上次檢查**]-上次接收 sip 選項的時間。</span><span class="sxs-lookup"><span data-stu-id="9b19c-165">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="9b19c-166">**Sbc 狀態**–根據所有受監視的參數，sbc 的整體狀態。</span><span class="sxs-lookup"><span data-stu-id="9b19c-166">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="9b19c-167">**同時通話**-顯示已處理 SBC 的併發呼叫數。</span><span class="sxs-lookup"><span data-stu-id="9b19c-167">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="9b19c-168">此資訊對預測您所需的併發通道數量很有用，而且會看到趨勢。</span><span class="sxs-lookup"><span data-stu-id="9b19c-168">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="9b19c-169">您可以依天數和通話方向（入站/輸出/所有資料流程）來滑動資料。</span><span class="sxs-lookup"><span data-stu-id="9b19c-169">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="9b19c-170">**網路參數**-所有的網路參數都是從直接路由介面到會話邊界控制器的測量。</span><span class="sxs-lookup"><span data-stu-id="9b19c-170">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="9b19c-171">如需建議值的相關資訊，請參閱為[Microsoft 團隊準備貴組織的網路](https://docs.microsoft.com/en-us/microsoftteams/prepare-network)，並查看客戶邊緣至 microsoft Edge 的建議值。</span><span class="sxs-lookup"><span data-stu-id="9b19c-171">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="9b19c-172">抖動：是在使用 RTCP （RTP 控制通訊協定）的兩個端點之間計算之網路傳播延遲時間變化的毫秒測量。</span><span class="sxs-lookup"><span data-stu-id="9b19c-172">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="9b19c-173">資料包遺失-是一種無法送達資料包的量度，它是在兩個端點之間計算。</span><span class="sxs-lookup"><span data-stu-id="9b19c-173">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="9b19c-174">延隔時間（也稱為往返行程時間）是傳送信號所需的時間長度，加上接收該信號所需的確認時間長度。</span><span class="sxs-lookup"><span data-stu-id="9b19c-174">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="9b19c-175">此時間延遲是由兩個信號點之間的傳播時間所組成。</span><span class="sxs-lookup"><span data-stu-id="9b19c-175">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="9b19c-176">您可以依天數和通話方向（入站/輸出/所有資料流程）來滑動資料。</span><span class="sxs-lookup"><span data-stu-id="9b19c-176">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="9b19c-177">**網路效能比率**-此參數與整體健康情況儀表板上顯示的參數相同，但透過時序或呼叫方向來切分資料的選項。</span><span class="sxs-lookup"><span data-stu-id="9b19c-177">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>




