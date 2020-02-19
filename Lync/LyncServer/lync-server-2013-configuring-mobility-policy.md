---
title: Lync Server 2013： 設定行動性原則
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
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中設定行動性原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供行動性原則，以決定誰可以使用行動功能，透過工時，voice over IP (VoIP) 或視訊通話和是否 WiFi 將會需要 VoIP 或視訊。 從公司撥號功能可讓行動使用者撥打及接聽通話行動電話上的使用公司電話號碼，而不是行動電話號碼。 這項功能防止受話的方看到發話者的行動電話號碼，並可讓使用者以避免輸出通話的費用。 設定 VoIP 和影片，可讓使用者接收，並使 VoIP 通話和影片。 如果使用者的裝置都必須透過行動數據網路使用 WiFi 網路設定 WiFi 的使用狀況定義。

根據預設，會啟用行動性、 工作，透過呼叫和 VoIP 和視訊功能。 需要 VoIp 和視訊 WiFi 設定已停用。 系統管理員可以執行 Cmdlet 來決定哪些人可以存取這些功能。 您可以依網站或使用者來全域關閉選項。

若要能夠使用行動功能和「從公司撥號」功能，使用者必須符合下列先決條件：

  - 使用者必須能夠針對 Lync Server 2013。

  - 使用者必須能夠使用 Enterprise Voice。

  - 使用者必須被指派 [EnableMobility]**** 選項設為 True 的行動原則。

若要讓使用者能夠使用「從公司撥號」，使用者必須符合下列兩項先決條件：

  - 使用者必須被指派已選取 [使電話同時響鈴]**** 選項的語音原則。

  - 必須為使用者指派 **[EnableOutsideVoice]** 選項設為 True 的行動原則。

<div>


> [!NOTE]  
> 未啟用 Enterprise voice 的使用者可以使用其行動裝置進行 Lync 至 Lync Voice over IP (VoIP) 通話，或其行動裝置上使用 [按一下以加入連結，如果您指派這些使用者語音原則的適當選項可以加入會議。 如需詳細資訊，請參閱<A href="lync-server-2013-defining-your-mobility-requirements.md">定義 Lync Server 2013 的行動性需求</A>。



</div>

如需啟用使用者的 Lync Server 2013 的詳細資訊，請參閱[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 如需為使用者啟用 Enterprise Voice 的詳細資訊，請參閱[啟用使用者的 Lync Server 2013 中的企業語音](lync-server-2013-enable-users-for-enterprise-voice.md)。 如需設定語音原則選項的詳細資訊，請參閱[修改語音原則和設定 Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>

## <a name="to-modify-global-mobility-policy"></a>修改全域行動原則

1.  登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的任何電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  全域關閉對行動性和「從公司撥號」功能的存取權。在命令列中輸入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 您不需要關閉對行動性的存取權，即可關閉「從公司撥號」。不過，如果您要關閉行動性，也必須關閉「從公司撥號」。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>依網站修改行動原則

1.  登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的任何電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  建立網站層級原則，並關閉 VoIP 和視訊，並啟用需要 WiFi IP 音訊和視訊 IP 」 網站。 在命令列中輸入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>依使用者修改行動原則

1.  登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的任何電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  建立使用者層級行動原則，並依使用者關閉行動性和「從公司撥號」。在命令列中輸入：
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    您不需要關閉對行動性的存取權，即可關閉「從公司撥號」。不過，如果您要關閉行動性，也必須關閉「從公司撥號」。
    
    例如：
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>請參閱


[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[啟用使用者的 Lync Server 2013 中的 Enterprise Voice](lync-server-2013-enable-users-for-enterprise-voice.md)  
[修改語音原則和設定 Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[定義 Lync Server 2013 的行動性需求](lync-server-2013-defining-your-mobility-requirements.md)  


[新 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

