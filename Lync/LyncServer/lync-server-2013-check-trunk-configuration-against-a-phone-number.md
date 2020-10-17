---
title: Lync Server 2013：對照電話號碼檢查主幹設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 881e161a01b589db2db172cb5115858b522d262b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526230"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>對照 Lync Server 2013 中的電話號碼檢查主幹設定

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsTrunkConfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

SIP 主幹將 Lync Server internal Enterprise Voice 網路連接至下列任何一種：

  - 公用交換電話網路 (PSTN) 。

  - IP 公用 exchange 交換器 (PBX) 。

  -  (SBC) 的會話邊界控制器。

Test-CsTrunkConfiguration 指令程式會驗證使用者 (所撥打的電話號碼，) 可轉換成 e.164 網路，並透過指定的 SIP 主幹進行路由傳送。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test-CsTrunkConfiguration Cmdlet，您必須先使用 Get-CsTrunkConfiguration Cmdlet，以取得 SIP 主幹設定設定的實例;然後，該實例會管線傳送至 Test-CsTrunkConfiguration：

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

執行 Test-CsTrunkConfiguration 但未先執行 Get-CsTrunkConfiguration 將無法運作。 例如，此命令將會失敗，而不會傳回任何資料：

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

如果您有多個 SIP 主幹設定的集合，您可以使用類似下列的命令，對相同的電話號碼測試每個集合：

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

如需詳細資訊，請參閱 Test-CsTrunkConfiguration Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-CsTrunkConfiguration 可以撥打撥號號碼，則已轉譯的電話號碼 (為 e.164 格式) 而且用於轉譯該電話號碼的規則會顯示在畫面上：

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219全球/Redmond

測試失敗時，Test-CsTrunkConfiguration 會傳回空的屬性值：

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test-CsTrunkConfiguration 不會傳回符合，通常表示所測試的主幹設定設定沒有可以將撥號號碼轉換為 e.164 格式的撥出電話號碼轉譯規則。 若要取得指派給主幹設定設定集合的轉譯規則，您可以使用類似下列的語法：

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

針對每個轉譯規則傳回類似下列的資訊：

描述：沒有國家或地區代碼的電話號碼。

模式： ^ \\ + (\\ d \*) $

`Translation : $1`

名稱： NoAreaCode

此時，您會檢查 Pattern 屬性的值 (它是 [正則運算式](https://go.microsoft.com/fwlink/?linkid=400464) 字串) ，以查看是否有任何轉譯規則設定為處理撥號號碼。 如果不是，您必須變更其中一個現有的規則 (CsOutboundTranslationRule) 或使用 New-CsOutboundTranslationRule 指令程式將新規則新增至集合。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

