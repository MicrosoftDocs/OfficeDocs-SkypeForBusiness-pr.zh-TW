---
title: Lync Server 2013： 測試語音規則、 路由和原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>測試語音規則、 路由和 Lync Server 2013 中的原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-20 個_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoiceUser cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

當使用者進行的通話時，呼叫會採用到達其目的地的路由會依的原則和撥號對應表指派給該使用者而定。 指定使用者的 SIP 地址和電話號碼，測試 CsVoiceUser cmdlet，驗證是否有問題的使用者可以完成該號碼。 如果測試成功，測試 CsVoiceUser 傳回下列結果：

  - 號碼轉譯成 E.164 格式 （根據使用者的撥號對應表）

  - 提供的翻譯正規化規則

  - 使用的語音路由 （根據路由優先順序）;

  - 連結至語音路由的使用者的語音原則電話使用方式。

測試 CsVoiceUser 可讓您判斷特定的電話號碼是否會路由傳送翻譯不如預期，並可協助您針對個別使用者所遇到的通話相關問題進行疑難排解。

</div>

<div>

## <a name="running-the-test"></a>執行測試

執行測試 CsVoiceUser 指令程式時，您就必須提供兩項資訊： 正在撥打 (DialedNumber) 以及要測試的使用者帳戶的身分識別號碼。 例如，此命令還能測試能力具有要撥打的電話號碼 +1206555 SIP 位址 sip:kenmyer@litwareinc.com 的使用者-1219年:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

您所預期要撥打的方式應格式化的電話號碼。 例如，如果使用者通常不要撥接 1 之前撥長途電話打電話您應該使用此格式：

`-DialedNumber "2065551219"`

當然，在此情況下，測試將會失敗如果您沒有可以正確地轉譯成 Lync 伺服器所使用的 E.164 電話格式數字 2065551219 正規化規則。 如需詳細資訊，請參閱說明主題 New-csvoicenormalizationrule cmdlet。

如果您想要針對每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

如需詳細資訊，請參閱 < 測試 CsVoiceUser cmdlet 的說明 」 文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果測試成功完成時 （亦即，如果使用者可以撥打電話到指定的數字），輸出會顯示類似的轉譯的電話號碼和相符的正規化規則，以及語音路由的資訊：

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti...]   LocalRoute 本機

[Windows PowerShell] 畫面的限制，因為至少部分傳回的資訊 （最值得注意的是比對的正規化規則的完整描述） 可能不會顯示螢幕上。 如果您只有感興趣的成功或失敗的測試，然後這可能不重要。 如果您偏好以查看傳回的資料的完整詳細資料，然後輸出內容輸送到 Format-list 指令程式執行測試時：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

將更多的讀取者易記的格式顯示輸出：

TranslatedNumber: + 12065551219

MatchingRule: Description =;圖樣 = ^ (\\d{11}) $;翻譯 = + $1;

名稱 = 首碼所有; IsInternalExtension = False

FirsMatchingRoute: LocalRoute

MatchingUsage： 本機

如果測試失敗，測試 CsVoiceUser 會傳回空集合的屬性值：

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

有任意數目的為什麼測試 CsVoiceUser 指令程式可能會失敗的原因： 可能不會有可翻譯的提供的電話號碼正規化規則。 可能的語音路由的問題。 可能與撥號對應指派給使用者，有問題的組態問題。 因此，您可能想要加入 Verbose 參數，當您執行測試 CsVoiceUser 指令程式：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

加入 Verbose 指令程式時，請測試 CsVoiceUser 會發給中採取的所有步驟的詳細的帳戶，進行其檢查時。 例如，您可能會看到類似以下的步驟執行： 

VERBOSE： 尋找使用者身分識別 」 sip:kenmyer@litwareinc.com"

VERBOSE： 載入撥號對應表: 「 RedmondDialPlan 」

此額外資訊可以提供提示想找出失敗的原因時，可採取的步驟。 例如，如下所示的詳細資訊輸出告訴我們正在測試使用者已指派撥號對應表 redmonddialplan 指派。 如果測試失敗，一個邏輯的下一步是確認 RedmondDialPlan 可以翻譯提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試 CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

