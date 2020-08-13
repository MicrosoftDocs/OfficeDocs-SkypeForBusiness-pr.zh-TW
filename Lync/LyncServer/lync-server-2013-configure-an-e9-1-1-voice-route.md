---
title: Lync Server 2013：設定 E9-1-1 語音路由
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
ms.openlocfilehash: 767f49aa0074e269de386b2db017dc183e4eb92d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="35ce3-102">在 Lync Server 2013 中設定 E9-1-1 語音路由</span><span class="sxs-lookup"><span data-stu-id="35ce3-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ce3-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="35ce3-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="35ce3-104">若要部署 E9-1-1，您需要先設定緊急電話語音路由。</span><span class="sxs-lookup"><span data-stu-id="35ce3-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="35ce3-105">如需建立語音路由的詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="35ce3-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="35ce3-106">例如，如果您的部署包括主要及次要 SIP 主幹，則可以定義多個路由。</span><span class="sxs-lookup"><span data-stu-id="35ce3-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35ce3-107">若要在 E9-1-1 INVITE 中包括位置資訊，則必須先設定連線至 E9-1-1 服務提供者的 SIP 主幹以透過閘道路由傳送緊急電話。</span><span class="sxs-lookup"><span data-stu-id="35ce3-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="35ce3-108">若要進行這項作業，請將 <STRONG>Set-CsTrunkConfiguration</STRONG> Cmdlet 上的 EnablePIDFLOSupport 旗標設定為 True。</span><span class="sxs-lookup"><span data-stu-id="35ce3-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="35ce3-109">EnablePIDFLOSupport 的預設值是 False。</span><span class="sxs-lookup"><span data-stu-id="35ce3-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="35ce3-110">例如：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="35ce3-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="35ce3-111">不需要啟用接收後援公用交換電話網路 (PSTN) 閘道的位置，也不需啟用緊急位置識別號碼 (ELIN) 閘道的位置。</span><span class="sxs-lookup"><span data-stu-id="35ce3-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="35ce3-112">如需使用語音路由的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="35ce3-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="35ce3-113">**Get-cspstnusage**</span><span class="sxs-lookup"><span data-stu-id="35ce3-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="35ce3-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="35ce3-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="35ce3-115">**New-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35ce3-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35ce3-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="35ce3-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35ce3-117">**Get-csvoiceroute**</span><span class="sxs-lookup"><span data-stu-id="35ce3-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="35ce3-118">**Remove-Get-csvoiceroute**</span><span class="sxs-lookup"><span data-stu-id="35ce3-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="35ce3-119">設定 E9-1-1 語音路由</span><span class="sxs-lookup"><span data-stu-id="35ce3-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="35ce3-120">使用屬於 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="35ce3-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="35ce3-121">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="35ce3-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="35ce3-122">執行下列 Cmdlet 來建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="35ce3-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="35ce3-123">這必須是用於 [位置原則] 中 **PSTN** 設定的相同名稱。</span><span class="sxs-lookup"><span data-stu-id="35ce3-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="35ce3-124">雖然部署會有多筆電話使用方式記錄，下列範例會將「緊急使用方式」新增至目前可用的 PSTN 使用方式清單。</span><span class="sxs-lookup"><span data-stu-id="35ce3-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="35ce3-125">如需詳細資訊，請參閱設定[語音原則和 PSTN 使用方式記錄，以在 Lync Server 2013 中授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="35ce3-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="35ce3-126">執行下列 Cmdlet，使用上個步驟中所建立的 PSTN 使用方式記錄來建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="35ce3-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="35ce3-127">數字模式必須是位置原則的**緊急撥號字串**設定中所使用的相同數字模式。</span><span class="sxs-lookup"><span data-stu-id="35ce3-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="35ce3-128">因為 Lync 會將 "+" 新增至緊急通話，所以需要 "+" 符號。</span><span class="sxs-lookup"><span data-stu-id="35ce3-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="35ce3-129">"Co1-pstngateway-1" 是 E9-1-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 主幹服務 ID。</span><span class="sxs-lookup"><span data-stu-id="35ce3-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="35ce3-130">下列範例會使用“EmergencyRoute”作為語音路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="35ce3-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="35ce3-p105">建議您針對 SIP 主幹連線選擇執行下列 Cmdlet，建立不是由 E9-1-1 伺服器提供者的 SIP 主幹所處理之通話的本機路由。如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。</span><span class="sxs-lookup"><span data-stu-id="35ce3-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="35ce3-133">下列範例假設使用者的語音原則有「本機」使用方式。</span><span class="sxs-lookup"><span data-stu-id="35ce3-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

