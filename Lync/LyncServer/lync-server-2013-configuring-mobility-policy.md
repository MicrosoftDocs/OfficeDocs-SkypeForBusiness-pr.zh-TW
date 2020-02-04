---
title: Lync Server 2013：設定行動原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中設定行動原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供行動原則，可決定誰可以使用行動功能、透過公司通話、透過 IP （VoIP）或影片呼叫，以及 VoIP 或視頻是否需要 WiFi。 [透過工作通話] 功能可讓行動使用者使用公司電話號碼（而不是行動電話號碼）撥打及接聽行動電話上的通話。 此功能可防止呼叫的參與方查看來電者的行動電話號碼，並讓使用者避免撥出電話費。 設定 VoIP 和影片可讓使用者接收併發出 VoIP 通話和影片。 WiFi 使用的設定定義使用者的裝置是否需要透過行動資料網路使用 WiFi 網路。

根據預設，行動性、透過公司通話，以及 VoIP 與視頻功能都已啟用。 已停用 [VoIp] 和 [影片] 需要 WiFi 的設定。 系統管理員可以執行 Cmdlet 來判斷誰有權存取這些功能。 您可以關閉 [全域]、[按網站] 或 [由使用者] 以外的選項。

若要能夠使用行動功能及透過公司通話，使用者必須符合下列先決條件：

  - 必須針對 Lync Server 2013 啟用使用者。

  - 必須為使用者啟用企業語音。

  - 必須將 [ **EnableMobility** ] 選項設定為 True 的行動原則指派給使用者。

若要讓使用者能夠透過工作使用通話，他們必須滿足下列兩個額外的先決條件：

  - 必須為使用者指派已選取 [**啟用同時撥打電話**] 選項的語音原則。

  - 必須將 [ **EnableOutsideVoice** ] 選項設定為 True 的行動原則指派給使用者。

<div>


> [!NOTE]  
> 未啟用企業語音的使用者可以使用他們的行動裝置，讓 Lync 透過 IP （VoIP）通話，或使用其行動裝置上的 [按一下以加入] 連結來加入會議（如果您為這些使用者指派了適當的語音原則選項）。 如需詳細資訊，請參閱<A href="lync-server-2013-defining-your-mobility-requirements.md">定義 Lync Server 2013 的行動需求</A>。



</div>

如需有關啟用 Lync Server 2013 使用者的詳細資料，請參閱[停用或重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 如需有關啟用企業語音使用者的詳細資料，請參閱[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)。 如需設定語音原則選項的詳細資料，請參閱[修改語音原則和設定 Lync Server 2013 中的 PSTN 使用記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>

## <a name="to-modify-global-mobility-policy"></a>修改全域行動原則

1.  登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在全球範圍內關閉行動與通話的存取權。 在命令列中，輸入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 您可以透過工作關閉通話，而不需關閉行動存取權。 不過，您也無法關閉行動，也不需要關閉 [透過工作通話]。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>依網站修改行動原則

1.  登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  建立網站層級原則，然後關閉 [VoIP] 和 [影片]，並啟用 [IP 音訊] 和 [依網站的 IP 視頻]。 在命令列中，輸入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>依使用者修改行動原則

1.  登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  建立使用者層級行動原則，並透過使用者的工作關閉行動與通話。 在命令列中，輸入：
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    您可以透過工作關閉通話，而不需關閉行動存取權。 不過，您也無法關閉行動，也不需要關閉 [透過工作通話]。
    
    例如：
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>請參閱


[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)  
[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[定義 Lync Server 2013 的行動需求](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[授與 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

