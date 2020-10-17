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
ms.openlocfilehash: 72d3f60747f9b3456a6999358b0cf318b5e6d91d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521160"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話駐留設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您不想要使用預設的通話駐留設定，可以進行自訂。 當您安裝通話駐留應用程式時，系統會預設設定全域設定。 您可以修改全域設定，也可以指定網站特定設定。 使用 **New-CsCpsConfiguration** Cmdlet 可建立新的網站特定設定。 使用 **Set-CsCpsConfiguration** Cmdlet 可修改現有設定。

<div>


> [!NOTE]  
> 建議您至少設定 <STRONG>OnTimeoutURI</STRONG> 選項，作為當駐留通話逾時且回撥失敗時的後援目的地。



</div>

使用 **New-CsCpsConfiguration** Cmdlet 或 **Set-CsCpsConfiguration** Cmdlet 進行下列任何一項設定：


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
<td><p>從駐留通話之後到回撥原先接聽該通話的電話之前，需經過的時間長度。</p>
<p>此值必須以 hh:mm:ss 格式輸入，以指定小時、分鐘和秒數。最小值為 10 秒，最大值為 10 分鐘。預設值為 00:01:30。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>駐留通話時是否對來電者播放音樂。</p>
<p>值為 True 或 False。預設為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>在將駐留通話轉接至 <strong>OnTimeoutURI</strong> 指定的後援統一資源識別元 (URI) 之前，需將駐留通話回撥至當初接聽該通話的次數。預設值為 1。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>在超過 <strong>MaxCallPickupAttempts</strong> 時，將未接聽的駐留通話路由至的使用者或回應群組的 SIP 位址。</p>
<p>值必須是以字串 sip: 開頭的 SIP URI。例如，sip:bob@contoso.com。預設沒有轉接位址。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>設定通話駐留設定

1.  以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > 使用 <STRONG>Get-CsSite</STRONG> Cmdlet 來識別網站。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

    
    </div>
    
    例如：
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中自訂通話駐留的等候音樂](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

