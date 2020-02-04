---
title: Lync Server 2013：設定通話駐留設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話駐留設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您不想使用預設的通話駐留設定，您可以進行自訂。 當您安裝 [通話駐留] 應用程式時，系統會根據預設設定全域設定。 您可以修改全域設定，也可以指定網站專用的設定。 使用**新的 CsCpsConfiguration** Cmdlet 來建立新的網站特定設定。 使用**CsCpsConfiguration** Cmdlet 來修改現有的設定。

<div>


> [!NOTE]  
> 我們建議您針對備用目的地設定<STRONG>OnTimeoutURI</STRONG>選項，以便在停用通話超時和 ringback 失敗時使用。



</div>

使用**新的 CsCpsConfiguration** Cmdlet 或**CsCpsConfiguration** Cmdlet 來設定下列任何設定：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>此選項：</th>
<th>指定：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>通話結束之後，在撥打電話給接聽電話的電話之前所經過的時間長度。</p>
<p>此值必須以 hh： mm： ss 格式輸入，以指定小時、分鐘和秒。 最小值為10秒，最大值為10分鐘。 預設值為00:01:30。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>通話停用時，是否會在來電者中播放音樂。</p>
<p>值為 True 或 False。 預設值為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>寄存來電在轉寄到指定給<strong>OnTimeoutURI</strong>的回退統一資源識別項（URI）之前，響鈴給應答電話的次數。 預設值為1。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>在超過<strong>MaxCallPickupAttempts</strong>時傳送未應答之暫停呼叫的使用者或回應群組的 SIP 位址。</p>
<p>Value 必須是以 [字串 SIP：] 開頭的 SIP URI。 例如，sip:bob@contoso.com。 預設值為 [沒有轉寄位址]。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>若要設定通話寄存設定

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > 使用<STRONG>CsSite</STRONG> Cmdlet 來識別網站。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

    
    </div>
    
    例如：
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中自訂通話寄存音樂暫停](lync-server-2013-customize-call-park-music-on-hold.md)  


[新-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

