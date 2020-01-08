---
title: Lync Server 2013：設定 E9-1-1 個語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中設定 E9-1-1 的語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要部署 E9-1，您必須先設定緊急通話語音路線。 如需建立語音路由的詳細資料，請參閱[在 Lync Server 2013 中建立語音路線](lync-server-2013-create-a-voice-route.md)。 例如，如果您的部署包含主要 SIP 幹線和次要 SIP 主幹，您可以定義多個路由。

<div>


> [!NOTE]  
> 若要在 E9-1 邀請中包含位置資訊，您需要設定連接至 E9-1 服務提供者的 SIP 幹線，以透過閘道路由緊急通話。 若要這樣做，請將<STRONG>new-cstrunkconfiguration</STRONG> Cmdlet 的 EnablePIDFLOSupport 標誌設定為 True。 EnablePIDFLOSupport 的預設值為 False。 例如：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>您不需要為 fallback 公用交換電話網絡（PSTN）閘道及緊急位置識別號碼（ELIN）閘道啟用接收位置。



</div>

如需使用語音路由的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - **Set-CsPstnUsage**

  - **CsPstnUsage**

  - **新-CsVoiceRoute**

  - **CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **移除-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>若要設定 E9-1-1 的語音路線

1.  以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色的成員的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  執行下列 Cmdlet 以建立新的 PSTN 使用記錄。
    
    此名稱必須與您在位置原則中用於**PSTN**設定的名稱相同。 雖然您的部署會有多個電話使用記錄，但下列範例會將 [緊急使用量] 新增到目前可用 PSTN 用法的清單中。 如需詳細資訊，請參閱設定[語音原則和 PSTN 使用記錄，以在 Lync Server 2013 中授權呼叫功能與許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  執行下列 Cmdlet，以使用您在上一個步驟中建立的 PSTN 使用狀況記錄來建立新的語音路由。
    
    數位模式必須是在位置原則中的 [**緊急撥號字串**] 設定中所使用的相同數位模式。 [+] 符號是必要的，因為 Lync 會將 "+" 新增到緊急通話。 "Co1-pstngateway-1" 是針對 E9-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 幹線服務識別碼。 下列範例使用「EmergencyRoute」做為語音路由的名稱。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  或者，對於 SIP 中繼連線，我們建議您執行下列 Cmdlet 來為 E9 建立本機路由，以供-1-1 服務提供者的 SIP 幹線所處理的通話。 如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。
    
    下列範例假設使用者的語音原則中有「本機」用法。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

