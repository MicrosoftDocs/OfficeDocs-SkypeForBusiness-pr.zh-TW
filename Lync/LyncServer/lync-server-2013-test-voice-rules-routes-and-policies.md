---
title: Lync Server 2013：測試語音規則、路由和原則
description: Lync Server 2013：測試語音規則、路由和原則。
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
ms.openlocfilehash: cf205ac2585298dfc5347d93e382e8bbda9f3ff4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557039"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>在 Lync Server 2013 中測試語音規則、路由和原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_


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
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceUser Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

當使用者撥打電話時，呼叫到達目的地所用的路由，取決於指派給該使用者的原則和撥號對應表。 指定使用者的 SIP 位址和電話號碼，Test-CsVoiceUser Cmdlet 會驗證問題使用者是否可以撥打該號碼。 測試成功時，Test-CsVoiceUser 會傳回下列專案：

  - 根據使用者的撥號對應表，翻譯為 e.164 格式 (的數位) 

  - 提供該轉譯的正常化規則

  - 語音路由使用 (根據路由優先順序) ;

  - 將使用者語音原則連結到語音路由的電話使用方式。

Test-CsVoiceUser 可讓您判斷特定的電話號碼是否會如預期的方式進行路由和轉譯，以及協助疑難排解個別使用者所遇到的呼叫相關問題。

</div>

<div>

## <a name="running-the-test"></a>執行測試

在執行 Test-CsVoiceUser 指令指令時，您必須提供兩種資訊：所撥打的號碼 (DialedNumber) ，以及所測試之使用者帳戶的身分識別。 例如，下列命令會測試具有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者撥打電話號碼 + 1206555-1219 的能力：

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

電話號碼應該以您預期的撥號方式格式化。 例如，如果使用者在撥打長途電話之前未撥打1，則您應該使用此格式：

`-DialedNumber "2065551219"`

當然，在這種情況下，如果您沒有可以將號碼2065551219正確轉譯成 Lync Server 所使用的 e.164 電話格式的正規化規則，則測試會失敗。 如需詳細資訊，請參閱 help 主題 New-CsVoiceNormalizationRule Cmdlet。

如果您想要針對每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

如需詳細資訊，請參閱 Test-CsVoiceUser Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果成功完成測試 (也就是說，如果使用者可以撥打電話給指定的號碼) ，輸出會顯示如已翻譯的電話號碼和對應正規化規則和語音路由等資訊：

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti .。。   LocalRoute Local

由於 Windows PowerShell 畫面的限制，至少某些傳回的資訊 (比對的相符正規化規則) 的完整描述可能不會出現在畫面上。 如果您只對成功或失敗的測試感興趣，則可能不重要。 如果您想要在執行測試時，看到傳回資料的完整詳細資料，然後將輸出輸送至 Format-List Cmdlet：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

這樣會以更易於讀取器的格式顯示輸出：

TranslatedNumber： + 12065551219

MatchingRule： Description =;Pattern = ^ (\\ d {11}) $;轉譯 = + $ 1;

Name = Prefix All; IsInternalExtension = False

FirsMatchingRoute : LocalRoute

MatchingUsage：本機

測試失敗時，Test-CsVoiceUser 會傳回一組空的屬性值：

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

Test-CsVoiceUser Cmdlet 可能失敗的原因有多種：可能不會有可轉譯所提供電話號碼的正常化規則。 語音路由可能會發生問題。 指派給問題使用者的撥號對應表可能發生設定問題。 因此，當您執行 Test-CsVoiceUser Cmdlet 時，您可能會想要加入 Verbose 參數：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

加入詳細的指令 Cmdlet 時，Test-CsVoiceUser 會發佈執行其檢查時所採取之所有步驟的詳細帳戶。 例如，您可能會看到類似下列的步驟： 

詳細：尋找身分識別為 "sip:kenmyer@litwareinc.com" 的使用者

詳細：載入撥號對應表： "RedmondDialPlan"

這項額外資訊可提供您可以採取的步驟，以找出失敗的原因。 例如，此處顯示的詳細資訊輸出會告訴我們所測試的使用者已獲指派撥號對應表 RedmondDialPlan。 如果測試失敗，下一個邏輯的步驟就是驗證 RedmondDialPlan 是否可以轉譯所提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

