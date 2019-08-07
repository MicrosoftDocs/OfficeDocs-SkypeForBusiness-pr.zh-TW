---
title: 呼出通話的幹線容錯移轉
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 請閱讀本主題, 瞭解如何處理來自團隊的呼出通話的中繼容錯移轉至會話邊界控制器 (SBC)。
ms.openlocfilehash: 5c456aab52159859112b44c19c1b15fe81bc6293
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183738"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="53b88-103">呼出通話的幹線容錯移轉</span><span class="sxs-lookup"><span data-stu-id="53b88-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="53b88-104">本主題說明如何避免呼出通話的幹線容錯移轉--從團隊到會話邊界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="53b88-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="53b88-105">網路錯誤的容錯移轉</span><span class="sxs-lookup"><span data-stu-id="53b88-105">Failover on network errors</span></span>

<span data-ttu-id="53b88-106">如果乾線由於任何原因而無法連線, 則會從不同的 Microsoft Datacenter 嘗試連線到相同主幹。</span><span class="sxs-lookup"><span data-stu-id="53b88-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="53b88-107">例如, 如果某個連線遭到拒絕、TLS 超時, 或有任何其他的網路層級問題, 可能就無法連接主幹。</span><span class="sxs-lookup"><span data-stu-id="53b88-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="53b88-108">例如, 如果系統管理員僅從已知 IP 位址限制存取 SBC, 但忘記將所有 Microsoft Direct 路由資料中心的 IP 位址放在 SBC 的存取控制清單 (ACL) 中, 則連接可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="53b88-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="53b88-109">從會話邊界控制器 (SBC) 收到的特定 SIP 代碼的容錯移轉</span><span class="sxs-lookup"><span data-stu-id="53b88-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="53b88-110">如果直接路由收到任何用於回應傳出邀請的4xx 或 6xx SIP 錯誤代碼, 則預設會認為已完成該通話。</span><span class="sxs-lookup"><span data-stu-id="53b88-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="53b88-111">[外寄] 表示來自團隊用戶端的呼叫與下列流量流程的公用交換電話網絡 (PSTN): 團隊用戶端-> 直接路由-> SBC > 電話網絡。</span><span class="sxs-lookup"><span data-stu-id="53b88-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="53b88-112">您可以在[會話初始通訊協定 (SIP) RFC](https://tools.ietf.org/html/rfc3261)中找到 SIP 代碼清單。</span><span class="sxs-lookup"><span data-stu-id="53b88-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="53b88-113">假設某個 SBC 以程式碼 "408 要求超時] 的傳入邀請回復, 例如, 伺服器無法在適當的時間內產生回應, 例如, 如果無法判斷使用者的時間位置。</span><span class="sxs-lookup"><span data-stu-id="53b88-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="53b88-114">用戶端可在任何時間重複要求, 而不需修改。」</span><span class="sxs-lookup"><span data-stu-id="53b88-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="53b88-115">這個特定的 SBC 可能會在連線至被呼叫者時遇到問題, 可能是因為網路錯誤配置或其他錯誤。</span><span class="sxs-lookup"><span data-stu-id="53b88-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="53b88-116">不過, 路由中有一個以上的 SBC, 可能可以達到被呼叫者的能力。</span><span class="sxs-lookup"><span data-stu-id="53b88-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="53b88-117">在下圖中, 當使用者撥打電話號碼時, 路線中有兩個 SBCs 可提供此通話。</span><span class="sxs-lookup"><span data-stu-id="53b88-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="53b88-118">最初已針對通話選取 [SBC1.contoso.com], 但由於網路問題, SBC1.contoso.com 無法達到 PTSN 網路。</span><span class="sxs-lookup"><span data-stu-id="53b88-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="53b88-119">根據預設, 會在目前完成通話。</span><span class="sxs-lookup"><span data-stu-id="53b88-119">By default, the call will be completed at this moment.</span></span> 
 
![顯示 SBC 由於網路問題而無法到達 PSTN 的圖表](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="53b88-121">但在路由中可能會有一個以上的 SBC 可以傳送通話。</span><span class="sxs-lookup"><span data-stu-id="53b88-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="53b88-122">如果您設定參數`Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, 則會在下列圖表中嘗試 SBC2.contoso.com 第二個 SBC:</span><span class="sxs-lookup"><span data-stu-id="53b88-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![顯示 [與第二個 SBC 路由] 的圖表](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="53b88-124">設定參數 FailoverResponseCodes 並指定程式碼可協助您微調路由, 並避免當 SBC 由於網路或其他問題而無法撥打電話時可能發生的問題。</span><span class="sxs-lookup"><span data-stu-id="53b88-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="53b88-125">預設值: 408、503、504</span><span class="sxs-lookup"><span data-stu-id="53b88-125">Default values:  408, 503, 504</span></span>

