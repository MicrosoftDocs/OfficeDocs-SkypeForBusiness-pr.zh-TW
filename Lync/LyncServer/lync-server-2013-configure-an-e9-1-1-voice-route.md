---
title: Lync Server 2013：設定 E9-1-1 個語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d40d2ee5dcb0dd7f759751bdab0d3e09f4ebc577
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="0ea8c-102">在 Lync Server 2013 中設定 E9-1-1 的語音路由</span><span class="sxs-lookup"><span data-stu-id="0ea8c-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ea8c-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="0ea8c-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="0ea8c-104">若要部署 E9-1，您必須先設定緊急通話語音路線。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="0ea8c-105">如需建立語音路由的詳細資料，請參閱[在 Lync Server 2013 中建立語音路線](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="0ea8c-106">例如，如果您的部署包含主要 SIP 幹線和次要 SIP 主幹，您可以定義多個路由。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ea8c-107">若要在 E9-1 邀請中包含位置資訊，您需要設定連接至 E9-1 服務提供者的 SIP 幹線，以透過閘道路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="0ea8c-108">若要這樣做，請將<STRONG>new-cstrunkconfiguration</STRONG> Cmdlet 的 EnablePIDFLOSupport 標誌設定為 True。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="0ea8c-109">EnablePIDFLOSupport 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="0ea8c-110">例如：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="0ea8c-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="0ea8c-111">您不需要為 fallback 公用交換電話網絡（PSTN）閘道及緊急位置識別號碼（ELIN）閘道啟用接收位置。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="0ea8c-112">如需使用語音路由的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0ea8c-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0ea8c-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="0ea8c-114">**CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="0ea8c-115">**新-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="0ea8c-116">**CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="0ea8c-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="0ea8c-118">**移除-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="0ea8c-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="0ea8c-119">若要設定 E9-1-1 的語音路線</span><span class="sxs-lookup"><span data-stu-id="0ea8c-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="0ea8c-120">以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色的成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="0ea8c-121">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0ea8c-122">執行下列 Cmdlet 以建立新的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="0ea8c-123">此名稱必須與您在位置原則中用於**PSTN**設定的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="0ea8c-124">雖然您的部署會有多個電話使用記錄，但下列範例會將 [緊急使用量] 新增到目前可用 PSTN 用法的清單中。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="0ea8c-125">如需詳細資訊，請參閱設定[語音原則和 PSTN 使用記錄，以在 Lync Server 2013 中授權呼叫功能與許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="0ea8c-126">執行下列 Cmdlet，以使用您在上一個步驟中建立的 PSTN 使用狀況記錄來建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="0ea8c-127">數位模式必須是在位置原則中的 [**緊急撥號字串**] 設定中所使用的相同數位模式。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="0ea8c-128">[+] 符號是必要的，因為 Lync 會將 "+" 新增到緊急通話。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="0ea8c-129">"Co1-pstngateway-1" 是針對 E9-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 幹線服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="0ea8c-130">下列範例使用「EmergencyRoute」做為語音路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="0ea8c-131">或者，對於 SIP 中繼連線，我們建議您執行下列 Cmdlet 來為 E9 建立本機路由，以供-1-1 服務提供者的 SIP 幹線所處理的通話。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-131">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="0ea8c-132">如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-132">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="0ea8c-133">下列範例假設使用者的語音原則中有「本機」用法。</span><span class="sxs-lookup"><span data-stu-id="0ea8c-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

