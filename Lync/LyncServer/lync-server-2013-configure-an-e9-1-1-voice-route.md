---
title: Lync Server 2013：設定 E9-1-1 語音路由
description: Lync Server 2013：設定 E9-1-1 語音路由。
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
ms.openlocfilehash: 869e9eaeb454943ccd877e90a21461c73065873e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546729"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中設定 E9-1-1 語音路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要部署 E9-1-1，您需要先設定緊急電話語音路由。 如需建立語音路由的詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。 例如，如果您的部署包括主要及次要 SIP 主幹，則可以定義多個路由。

<div>


> [!NOTE]  
> 若要在 E9-1-1 INVITE 中包括位置資訊，則必須先設定連線至 E9-1-1 服務提供者的 SIP 主幹以透過閘道路由傳送緊急電話。 若要進行這項作業，請將 <STRONG>Set-CsTrunkConfiguration</STRONG> Cmdlet 上的 EnablePIDFLOSupport 旗標設定為 True。 EnablePIDFLOSupport 的預設值是 False。 例如： <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>不需要啟用接收後援公用交換電話網路 (PSTN) 閘道的位置，也不需啟用緊急位置識別號碼 (ELIN) 閘道的位置。



</div>

如需使用語音路由的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - **Get-cspstnusage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Get-csvoiceroute**

  - **Remove-Get-csvoiceroute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>設定 E9-1-1 語音路由

1.  使用屬於 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色成員的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  執行下列 Cmdlet 來建立新的 PSTN 使用方式記錄。
    
    這必須是用於 [位置原則] 中 **PSTN** 設定的相同名稱。 雖然部署會有多筆電話使用方式記錄，下列範例會將「緊急使用方式」新增至目前可用的 PSTN 使用方式清單。 如需詳細資訊，請參閱設定 [語音原則和 PSTN 使用方式記錄，以在 Lync Server 2013 中授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  執行下列 Cmdlet，使用上個步驟中所建立的 PSTN 使用方式記錄來建立新的語音路由。
    
    數字模式必須是位置原則的**緊急撥號字串**設定中所使用的相同數字模式。 因為 Lync 會將 "+" 新增至緊急通話，所以需要 "+" 符號。 "Co1-pstngateway-1" 是 E9-1-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 主幹服務 ID。 下列範例會使用“EmergencyRoute”作為語音路由的名稱。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  建議您針對 SIP 主幹連線選擇執行下列 Cmdlet，建立不是由 E9-1-1 伺服器提供者的 SIP 主幹所處理之通話的本機路由。如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。
    
    下列範例假設使用者的語音原則有「本機」使用方式。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

