---
title: Lync Server 2013：測試語音規則、路由及原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>在 Lync Server 2013 中測試語音規則、路由與原則

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
<td><p>次</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceUser Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

當使用者撥打電話時，通話要達到目的地的路線，取決於指派給該使用者的原則和撥號方案。 已知使用者的 SIP 位址和電話號碼，CsVoiceUser Cmdlet 會驗證問題的使用者是否可以完成電話號碼的通話。 如果測試成功，測試 CsVoiceUser 會傳回下列內容：

  - 轉換為. 164 格式的數位（根據使用者的撥號計畫）

  - 提供該翻譯的正常化規則

  - 使用的語音路由（根據路線優先順序）;

  - 將使用者語音原則連結到語音路線的電話使用量。

CsVoiceUser 可讓您判斷某個特定的電話號碼是否會依預期進行路由與翻譯，並協助您排查個別使用者所遇到的與呼叫相關的問題。

</div>

<div>

## <a name="running-the-test"></a>執行測試

執行 CsVoiceUser Cmdlet 時，您必須提供兩種資訊：撥號號碼（DialedNumber），以及所測試的使用者帳戶身分識別。 例如，這個命令會測試擁有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者對電話號碼 + 1206555-1219 撥打電話的能力：

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

電話號碼應按照您預期的撥號方式來格式化。 例如，如果使用者在撥打電話前沒有撥打1長途，您應該使用這個格式：

`-DialedNumber "2065551219"`

當然，在這種情況下，如果您沒有可以正確將數位2065551219轉換成 Lync Server 所使用的 E. 164 電話格式的正常化規則，測試就會失敗。 如需詳細資訊，請參閱 CsVoiceNormalizationRule Cmdlet 的說明主題。

如果您想要針對您的每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

如需詳細資訊，請參閱 Test CsVoiceUser Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試成功完成（也就是，如果使用者可以撥打電話至指定號碼），輸出就會顯示已翻譯的電話號碼與相符的正常化規則及語音路線等資訊：

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti .。。   LocalRoute Local

由於 Windows PowerShell 畫面的限制，至少有一些傳回的資訊（最重要的是相符正常化規則的完整描述）可能不會出現在螢幕上。 如果您只對測試的成功或失敗感興趣，那可能並不重要。 如果您想要查看傳回資料的完整詳細資料，請在執行測試時，將輸出輸送至 Format 清單 Cmdlet：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

如此一來，就能以更容易讀取器的格式來顯示輸出：

TranslatedNumber： + 12065551219

MatchingRule： Description =;Pattern = ^ （\\d{11}） $;譯文 = + $ 1;

Name = Prefix All; IsInternalExtension = False

FirsMatchingRoute : LocalRoute

MatchingUsage： Local

如果測試失敗，測試 CsVoiceUser 會傳回一組空的屬性值：

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

CsVoiceUser Cmdlet 可能失敗的任何幾個原因：可能沒有可翻譯提供的電話號碼的正常化規則。 語音路線可能出現問題。 指派給該使用者的撥號方案可能有設定問題。 因此，您可能會想要在執行 Test CsVoiceUser Cmdlet 時加入詳細參數：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

加入詳細的 Cmdlet 時，測試 CsVoiceUser 會針對執行檢查時所採取的步驟，發出詳細的帳戶。 例如，您可能會看到類似以下的步驟： 

詳細：尋找具有 [sip:kenmyer@litwareinc.com] 身分識別的使用者

詳細：載入撥號方案： "RedmondDialPlan"

此額外資訊可能會提供提示，以找出錯誤原因的相關步驟。 例如，這裡顯示的詳細輸出告訴我們，經過測試的使用者已獲指派撥號方案 RedmondDialPlan。 如果測試失敗，下一個邏輯後續步驟就是確認 RedmondDialPlan 可以翻譯提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

