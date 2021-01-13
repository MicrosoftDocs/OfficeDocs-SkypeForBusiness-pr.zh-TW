---
title: 設定商務用 Skype Server 中的 E9-1-1 語音路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 語音路由。
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804173"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="d1d03-103">設定商務用 Skype Server 中的 E9-1-1 語音路由</span><span class="sxs-lookup"><span data-stu-id="d1d03-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="d1d03-104">在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 語音路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d1d03-105">若要部署 E9-1-1，您需要先設定緊急電話語音路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="d1d03-106">如需建立語音路由的詳細資訊，請參閱 [在商務用 Skype 中建立或修改語音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d03-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="d1d03-107">例如，如果您的部署包括主要及次要 SIP 主幹，則可以定義多個路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d1d03-108">若要在 E9-1-1 INVITE 中包括位置資訊，則必須先設定連線至 E9-1-1 服務提供者的 SIP 主幹以透過閘道路由傳送緊急電話。</span><span class="sxs-lookup"><span data-stu-id="d1d03-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="d1d03-109">若要進行這項作業，請將 **Set-CsTrunkConfiguration** Cmdlet 上的 EnablePIDFLOSupport 旗標設定為 True。</span><span class="sxs-lookup"><span data-stu-id="d1d03-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="d1d03-110">EnablePIDFLOSupport 的預設值是 False。</span><span class="sxs-lookup"><span data-stu-id="d1d03-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="d1d03-111">例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 不需要為 fallback 公用交換電話網路 (PSTN) 閘道和緊急位置識別號碼 (ELIN) 閘道啟用接收位置。</span><span class="sxs-lookup"><span data-stu-id="d1d03-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="d1d03-112">設定 E9-1-1 語音路由</span><span class="sxs-lookup"><span data-stu-id="d1d03-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="d1d03-113">使用屬於 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d1d03-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="d1d03-114">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="d1d03-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d1d03-115">執行下列 Cmdlet 來建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="d1d03-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="d1d03-116">這必須是用於 [位置原則] 中 **PSTN** 設定的相同名稱。</span><span class="sxs-lookup"><span data-stu-id="d1d03-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="d1d03-117">雖然部署會有多筆電話使用方式記錄，下列範例會將「緊急使用方式」新增至目前可用的 PSTN 使用方式清單。</span><span class="sxs-lookup"><span data-stu-id="d1d03-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="d1d03-118">如需詳細資訊，請參閱 [在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由](voice-and-pstn.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d03-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="d1d03-119">執行下列 Cmdlet，使用上個步驟中所建立的 PSTN 使用方式記錄來建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="d1d03-120">數字模式必須是位置原則的 **緊急撥號字串** 設定中所使用的相同數字模式。</span><span class="sxs-lookup"><span data-stu-id="d1d03-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="d1d03-121">因為商務用 Skype 將 "+" 新增至緊急通話，所以需要 "+" 符號。</span><span class="sxs-lookup"><span data-stu-id="d1d03-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="d1d03-122">"Co1-pstngateway-1" 是 E9-1-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 主幹服務 ID。</span><span class="sxs-lookup"><span data-stu-id="d1d03-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="d1d03-123">下列範例會使用“EmergencyRoute”作為語音路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="d1d03-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="d1d03-124">（選用）若為 SIP 主幹連線，我們建議您執行下列 Cmdlet，為未由 E9-1-1 服務提供者的 SIP 主幹處理的呼叫建立本機路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="d1d03-125">如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。</span><span class="sxs-lookup"><span data-stu-id="d1d03-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="d1d03-126">下列範例假設使用者的語音原則有「本機」使用方式。</span><span class="sxs-lookup"><span data-stu-id="d1d03-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


