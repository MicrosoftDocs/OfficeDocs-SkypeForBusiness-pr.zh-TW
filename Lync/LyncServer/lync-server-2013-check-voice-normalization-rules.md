---
title: Lync Server 2013：檢查語音正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 547f117a9706aa0ab5bf1202c31d0bc9f8ce34fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526210"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中檢查語音正常化規則

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceNormalizationRule Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

語音正規化規則是用來將使用者所撥打的電話號碼轉換 (例如，2065551219) 至 Lync Server (+ 12065551219) 所使用的 e.164 格式。 例如，如果使用者習慣撥打電話號碼，但未包含國家或地區碼 (例如，5551219) 則您必須具有可將該號碼轉換為 e.164 格式的語音正規化規則： + 12065551219。 若未使用此規則，使用者將無法呼叫555-1219。

Test-CsVoiceNormalizationRule Cmdlet 會驗證指定的語音正規化規則是否可成功轉換指定的電話號碼。 例如，此命令會檢查全域正規化規則 NoAreaCode 是否可以標準化及轉換撥號字串5551219。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test-CsVoiceNormalizationRule Cmdlet，您必須先使用 Get-CsVoiceNormalizationRule 指令程式，以取得所測試之規則的實例，然後使用管道將此實例 Get-csvoicenormalizationrule。 類似下列的語法不起作用：

Test-CsVoiceNormalizationRule DialedNumber "12065551219" – NormalizationRule "global/Prefix All"

請改為使用下列語法，它會結合 Get-CsVoiceNormalizationRule 和 Test-CsVoiceNormalizationRule Cmdlet：

Get-CsVoiceNormalizationRule 身分識別 "global/Prefix All" |Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 或者，您也可以使用此方法來取得規則的實例，然後根據指定的電話號碼來測試該規則：



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

輸入 DialedNumber 參數的值，就像您預期要撥打的號碼一樣。 例如，如果指定的語音正規化規則應該會自動將國家/地區代碼新增 (值12065551219中的初始 1) 則您應該保留國家/地區代碼：

`-DialedNumber "2065551219"`

如果規則設定正確，它會在將號碼轉換成 Lync Server 使用的 e.164 格式時，自動新增國家/地區代碼。

如需詳細資訊，請參閱 Test-CsVoiceNormalizationRule Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的語音正規化規則可以轉譯所提供的數目，則會在螢幕上顯示轉譯後的數位：

TranslatedNumber

\----------------

\+12065551219

如果測試失敗，則會傳回空白轉譯後的號碼：

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test-CsVoiceNormalizationRule 傳回轉譯後的數位，表示指定的語音正規化規則無法將提供的電話號碼轉譯成 Lync Server 所使用的 e.164 格式。 若要確認，請先確定您已正確輸入電話號碼。 例如，您預期您的語音正規化規則在轉譯類似以下的數位時會發生問題：

`-DialedNumber "1"`

假設輸入的號碼正確，下一個步驟應該是驗證指定的正規化規則是設計用來處理該電話號碼。 例如，一個正規化規則可能設計用來處理格式12065551219，但是第二個規則可能設計為處理數位2065551219。  (相同的電話號碼，在最開始的位置減去國家碼1。 ) 若要傳回語音正規化規則的詳細資訊，請執行類似如下的命令：

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

若要傳回所有語音正規化規則的詳細資訊，請改為執行下列命令：

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試-Get-csvoicenormalizationrule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

