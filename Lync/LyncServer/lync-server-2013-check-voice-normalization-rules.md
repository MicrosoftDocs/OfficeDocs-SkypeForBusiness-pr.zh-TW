---
title: Lync Server 2013： 檢查語音正規化規則
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
ms.openlocfilehash: eca48668bf0a19392558e10366f7a9bf4bb202ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>核取 [Lync Server 2013 中的語音正規化規則

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試來 cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

語音正規化規則可用來將轉換為 E.164 格式使用 Lync Server (+ 12065551219) 的使用者 (例如，2065551219) 所撥打的電話號碼。 例如，如果使用者在撥打的電話號碼，但不包括國家/地區或區域程式碼 (例如 5551219) 習慣然後您必須可以將該數字轉換成 E.164 格式的語音正規化規則: + 12065551219。 沒有這類規則，使用者無法呼叫 555-1219。

測試來 cmdlet 會驗證指定的語音正規化規則可以成功轉換的指定的電話號碼。 例如，此命令會檢查全域正規化規則 NoAreaCode 可以正規化的需求，並將撥號對應表字串 5551219 轉換。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行測試來指令程式，您必須先使用 Get-csvoicenormalizationrule cmdlet 來擷取要測試之規則的執行個體，並再將以管線傳輸至測試來執行個體。 將無法使用類似如下的語法：

來測試 DialedNumber 」 12065551219"– NormalizationRule 「 全域/前置詞所有 」

相反地，使用語法如下所示，結合了 Get-csvoicenormalizationrule 及測試來 cmdlet:

Get-csvoicenormalizationrule-Identity"全域/前置詞所有 「 |來測試 DialedNumber 「 12065551219 」

<div>


> [!NOTE]  
> . 或者，您也可以使用這種方法來擷取規則的執行個體，然後測試對指定的電話號碼的規則：



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

完全依照您預期該號碼撥打 DialedNumber 參數輸入值。 例如，如果指定的語音正規化規則應會自動新增國碼/地區碼 (值 12065551219 中的初始 1)，則應該將維持關閉國碼/地區碼：

`-DialedNumber "2065551219"`

如果規則設定正確，它會自動加入國碼/地區碼轉譯 Lync 伺服器所使用的 E.164 格式號碼時。

如需詳細資訊，請參閱 < 測試來 cmdlet 的說明 」 文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的語音正規化規則可以翻譯提供的號碼然後轉譯後的數字會顯示畫面上：

TranslatedNumber

\----------------

\+12065551219

如果測試失敗，則會傳回空白的翻譯的數目：

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

如果測試來並傳回表示指定之的語音正規化規則無法將提供的電話號碼轉譯成 Lync 伺服器所使用的 E.164 格式轉譯的號碼。 若要確認，請先確認您正確輸入電話號碼。 例如，您所預期的轉譯類似這樣的數字的問題您語音正規化規則：

`-DialedNumber "1"`

假設已正確輸入號碼，接著應該若要確認指定的正規化規則設計來處理該電話號碼。 例如，一個正規化規則可能設計來處理格式 12065551219，但第二個規則可能設計來處理數 2065551219。 （這是相同的電話號碼，減一開始時國家/地區碼為 1）。若要傳回的語音正規化規則的詳細的資訊，請執行命令類似這樣：

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

若要傳回所有語音正規化規則的詳細的資訊，請改為執行此命令：

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試來](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

