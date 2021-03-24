---
title: 在商務用 Skype Server 中查看主幹設定資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102989"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="f0446-103">在商務用 Skype Server 中查看主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="f0446-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="f0446-104">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。</span><span class="sxs-lookup"><span data-stu-id="f0446-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="f0446-105">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="f0446-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f0446-106">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="f0446-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f0446-107">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="f0446-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f0446-108">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="f0446-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f0446-109">此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="f0446-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="f0446-110">**使用商務用 Skype Server 控制台來查看 SIP 主幹設定資訊**</span><span class="sxs-lookup"><span data-stu-id="f0446-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="f0446-111">在商務用 Skype Server 控制台中，依序按一下 [ **語音路由**] 和 [ **主幹** 設定]。</span><span class="sxs-lookup"><span data-stu-id="f0446-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="f0446-112">在 [ **主幹** 設定] 索引標籤上，您將會看到所有主幹設定的集合，也就是針對每個集合，您會看到 **名稱**、 **範圍**、 **狀態** 及 **媒體旁路** 屬性的值，以及 **PSTN 使用** 的數目、 **呼叫號碼規則**，以及與集合關聯的 **呼叫編號規則** 。</span><span class="sxs-lookup"><span data-stu-id="f0446-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="f0446-113">若要查看主幹設定設定集合的其他詳細資料，請按一下相關集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f0446-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="f0446-114">請注意，您一次只能查看一個主幹設定設定集合的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f0446-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f0446-115">使用 Windows PowerShell Cmdlet 來查看 SIP 主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="f0446-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f0446-116">您可以使用商務用 Skype Server PowerShell 和 Get-CsTrunkConfiguration Cmdlet 來查看 SIP 主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="f0446-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="f0446-117">您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0446-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f0446-118">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at https://go.microsoft.com/fwlink/p/?linkId=255876 。</span><span class="sxs-lookup"><span data-stu-id="f0446-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="f0446-119">請取代或移除此連結。</span><span class="sxs-lookup"><span data-stu-id="f0446-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="f0446-120">**若要查看 SIP 主幹設定資訊**</span><span class="sxs-lookup"><span data-stu-id="f0446-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="f0446-121">若要查看所有 SIP 主幹設定設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="f0446-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="f0446-122">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f0446-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="f0446-123">如需詳細資訊，請參閱 [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="f0446-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>