---
title: 在商務用 Skype Server 中查看幹線設定資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。
ms.openlocfilehash: 0ccbf86891d6265298411ad2f90988123529b614
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816902"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="35690-103">在商務用 Skype Server 中查看幹線設定資訊</span><span class="sxs-lookup"><span data-stu-id="35690-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="35690-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="35690-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="35690-105">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="35690-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="35690-106">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="35690-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="35690-107">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="35690-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="35690-108">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 中繼設定。</span><span class="sxs-lookup"><span data-stu-id="35690-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="35690-109">此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="35690-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="35690-110">**使用商務用 Skype Server 控制台來查看 SIP 幹線設定資訊**</span><span class="sxs-lookup"><span data-stu-id="35690-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="35690-111">在商務用 Skype Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="35690-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="35690-112">在 [**幹線**設定] 索引標籤上，您會看到所有中繼設定集合的清單;針對每個集合，您會看到**名稱**、**範圍**、**狀態**及**媒體旁路**屬性的值，以及**PSTN 使用量**數、**呼叫編號規則**，以及與集合相關聯的已**呼叫編號規則**。</span><span class="sxs-lookup"><span data-stu-id="35690-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="35690-113">若要查看主幹設定設定集合的其他詳細資料，請按一下感興趣的集合，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="35690-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="35690-114">請注意，您可以一次只查看一個主幹設定設定集合的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="35690-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="35690-115">使用 Windows PowerShell Cmdlet 來查看 SIP 幹線設定資訊</span><span class="sxs-lookup"><span data-stu-id="35690-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="35690-116">您可以使用商務用 Skype Server PowerShell 和 New-cstrunkconfiguration Cmdlet 來查看 SIP 幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="35690-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="35690-117">此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="35690-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="35690-118">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 http://go.microsoft.com/fwlink/p/?linkId=255876。</span><span class="sxs-lookup"><span data-stu-id="35690-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="35690-119">[取代] 或 [移除] 此連結。</span><span class="sxs-lookup"><span data-stu-id="35690-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="35690-120">**若要查看 SIP 中繼配置資訊**</span><span class="sxs-lookup"><span data-stu-id="35690-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="35690-121">若要查看所有 SIP 主幹設定設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="35690-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="35690-122">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="35690-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="35690-123">如需詳細資訊，請參閱[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="35690-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



