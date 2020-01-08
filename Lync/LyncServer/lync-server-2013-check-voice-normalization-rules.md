---
title: Lync Server 2013：檢查語音正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中檢查語音正常化規則

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceNormalizationRule Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

語音正常化規則是用來將使用者所撥的電話號碼（例如2065551219）轉換為 Lync Server （+ 12065551219）所使用的 E. 164 格式。 例如，如果使用者習慣撥電話號碼（不包括國家/地區碼或區號（例如5551219）），則您必須有可將該數位轉換為 E.i 格式的語音正常化規則： + 12065551219。 如果沒有這類規則，使用者將無法呼叫555-1219。

CsVoiceNormalizationRule Cmdlet 會驗證指定的語音正常化規則是否可以成功轉換指定的電話號碼。 例如，這個命令會檢查全域正常化規則 NoAreaCode 是否可以正常化並轉換撥號字串5551219。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 CsVoiceNormalizationRule Cmdlet，您必須先使用 CsVoiceNormalizationRule Cmdlet 來檢索所測試規則的實例，然後將該實例管路為 Test-CsVoiceNormalizationRule。 類似以下的語法將無法運作：

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "全域/全部首碼"

相反地，請使用如下所示的語法，其中結合了 CsVoiceNormalizationRule 和 CsVoiceNormalizationRule Cmdlet：

CsVoiceNormalizationRule-身分識別 "全域/前置全部" |Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 或者，您也可以使用此方法來取得規則的實例，然後根據指定的電話號碼來測試該規則：



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

輸入 DialedNumber 參數的值，就像您預期要撥打的號碼一樣。 例如，如果指定的語音正常化規則應該自動新增國家/地區代碼（值12065551219中的初始1），那麼您應該離開國家/地區代碼：

`-DialedNumber "2065551219"`

如果規則設定正確，則會在將號碼轉換為 Lync Server 所使用的 E. 164 格式時，自動新增國家/地區代碼。

如需詳細資訊，請參閱 Test CsVoiceNormalizationRule Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的語音正常化規則可以翻譯所提供的數位，則會在螢幕上顯示已翻譯的數位：

TranslatedNumber

\----------------

\+12065551219

如果測試失敗，則會傳回一個空白翻譯的數位：

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果測試 CsVoiceNormalizationRule 確實傳回已翻譯的數位，表示指定的語音正常化規則無法將提供的電話號碼轉譯成 Lync Server 所使用的 e. 164 格式。 若要確認，請先確認您已正確輸入電話號碼。 例如，您會希望語音正常化規則在翻譯如下所示的數位時發生問題：

`-DialedNumber "1"`

假設輸入的數位正確，下一個步驟應該是確認指定的正常化規則是設計來處理該電話號碼。 例如，一個正常化規則可能是設計用來處理12065551219格式，但第二個規則可能是用來處理數位2065551219的設計。 （這是相同的電話號碼，在最開頭則不是國家/地區代碼1）。若要傳回有關語音正常化規則的詳細資訊，請執行如下所示的命令：

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

若要返回所有語音正常化規則的詳細資訊，請改為執行此命令：

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

