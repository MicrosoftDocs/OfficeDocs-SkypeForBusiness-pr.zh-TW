---
title: Lync Server 2013：設定行動性原則
description: Lync Server 2013：設定行動性原則。
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
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569999"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中設定行動性原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供行動原則，可決定誰可以使用行動功能、撥打工作、透過 IP 語音 (VoIP) 或影片，以及 VoIP 或影片是否需要 WiFi。 「透過工作通話」功能可讓行動使用者使用公司電話號碼，而不是行動電話號碼，撥打和接聽行動電話。 這項功能可防止叫用方看到來電者的行動電話號碼，並可讓使用者避免撥出電話費用。 設定 VoIP 和影片可讓使用者接收及撥打 VoIP 通話和影片。 WiFi 使用狀況設定定義使用者的裝置是否需要透過行動電話資料網路使用 WiFi 網路。

預設會啟用行動性、呼叫透過工作，以及 VoIP 和影片功能。 已停用 WiFi 的 VoIp 和影片所需的設定。 系統管理員可以執行 Cmdlet 來決定哪些人可以存取這些功能。 您可以依網站或使用者來全域關閉選項。

若要能夠使用行動功能和「從公司撥號」功能，使用者必須符合下列先決條件：

  - 使用者必須啟用 Lync Server 2013。

  - 使用者必須能夠使用 Enterprise Voice。

  - 使用者必須被指派 [EnableMobility]**** 選項設為 True 的行動原則。

若要讓使用者能夠使用「從公司撥號」，使用者必須符合下列兩項先決條件：

  - 使用者必須被指派已選取 [使電話同時響鈴]**** 選項的語音原則。

  - 必須為使用者指派 **[EnableOutsideVoice]** 選項設為 True 的行動原則。

<div>


> [!NOTE]  
> 未啟用 Enterprise Voice 的使用者可以使用行動裝置，將 Lync to Lync over IP (VoIP) 通話，或透過使用行動裝置上的 [加入] 連結（如果您為這些使用者指派語音原則的適當選項）來加入會議。 如需詳細資訊，請參閱 <A href="lync-server-2013-defining-your-mobility-requirements.md">定義您的 Lync Server 2013 行動需求</A>。



</div>

如需對 Lync Server 2013 啟用使用者的詳細資訊，請參閱 [Disable or 重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 如需關於為使用者啟用 Enterprise Voice 的詳細資訊，請參閱 [Enable 使用者 For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。 如需設定語音原則選項的詳細資訊，請參閱 [在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>

## <a name="to-modify-global-mobility-policy"></a>修改全域行動原則

1.  登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  全域關閉對行動性和「從公司撥號」功能的存取權。在命令列中輸入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 您不需要關閉對行動性的存取權，即可關閉「從公司撥號」。不過，如果您要關閉行動性，也必須關閉「從公司撥號」。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>依網站修改行動原則

1.  登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  建立網站層級原則，並關閉 VoIP 和影片，並啟用 IP 音訊和 IP 影片的必要 WiFi。 在命令列中輸入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>依使用者修改行動原則

1.  登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

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
[在 Lync Server 2013 中啟用使用者的 Enterprise Voice](lync-server-2013-enable-users-for-enterprise-voice.md)  
[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[定義 Lync Server 2013 的行動需求](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

