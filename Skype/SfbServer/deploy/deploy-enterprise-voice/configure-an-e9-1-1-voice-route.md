---
title: 在商務用 Skype Server 中設定 E9-1-1 的語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 個語音路由。
ms.openlocfilehash: c835aa2ab2b20f7877aa6a0deeb70c7459bcd8cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001393"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="1eeb4-103">在商務用 Skype Server 中設定 E9-1-1 的語音路由</span><span class="sxs-lookup"><span data-stu-id="1eeb4-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="1eeb4-104">在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 個語音路由。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="1eeb4-105">若要部署 E9-1，您必須先設定緊急通話語音路線。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="1eeb4-106">如需建立語音路由的詳細資料，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="1eeb4-107">例如，如果您的部署包含主要 SIP 幹線和次要 SIP 主幹，您可以定義多個路由。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1eeb4-108">若要在 E9-1 邀請中包含位置資訊，您需要設定連接至 E9-1 服務提供者的 SIP 幹線，以透過閘道路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="1eeb4-109">若要這樣做，請將**new-cstrunkconfiguration** Cmdlet 的 EnablePIDFLOSupport 標誌設定為 True。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="1eeb4-110">EnablePIDFLOSupport 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="1eeb4-111">例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`您不需要為 fallback 公用交換電話網絡（PSTN）閘道及緊急位置識別號碼（ELIN）閘道啟用接收位置。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="1eeb4-112">若要設定 E9-1-1 的語音路線</span><span class="sxs-lookup"><span data-stu-id="1eeb4-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="1eeb4-113">以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色的成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="1eeb4-114">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1eeb4-115">執行下列 Cmdlet 以建立新的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="1eeb4-116">此名稱必須與您在位置原則中用於**PSTN**設定的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="1eeb4-117">雖然您的部署會有多個電話使用記錄，但下列範例會將 [緊急使用量] 新增到目前可用 PSTN 用法的清單中。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="1eeb4-118">如需詳細資訊，請參閱[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由](voice-and-pstn.md)。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="1eeb4-119">執行下列 Cmdlet，以使用您在上一個步驟中建立的 PSTN 使用狀況記錄來建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="1eeb4-120">數位模式必須是在位置原則中的 [**緊急撥號字串**] 設定中所使用的相同數位模式。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="1eeb4-121">商務用 Skype 將 "+" 新增到緊急通話，所以需要 "+" 符號。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="1eeb4-122">"Co1-pstngateway-1" 是針對 E9-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 幹線服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="1eeb4-123">下列範例使用「EmergencyRoute」做為語音路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="1eeb4-124">或者，對於 SIP 中繼連線，我們建議您執行下列 Cmdlet 來為 E9 建立本機路由，以供-1-1 服務提供者的 SIP 幹線所處理的通話。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="1eeb4-125">如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="1eeb4-126">下列範例假設使用者的語音原則中有「本機」用法。</span><span class="sxs-lookup"><span data-stu-id="1eeb4-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


