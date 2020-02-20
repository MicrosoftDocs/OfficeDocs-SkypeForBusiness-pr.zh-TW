---
title: Lync Server 2013： 檢查針對電話號碼的主幹組態
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
ms.openlocfilehash: 2832af2c038383e0cca9f8cb931ce4b675b44f2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>檢查針對 Lync Server 2013 中的電話號碼的主幹組態

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 Test-cstrunkconfiguration cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

SIP 主幹將 Lync Server 的內部企業語音網路連線至下列其中一項：

  - 公用交換電話網路 (PSTN)。

  - IP 公用交換機 (PBX)。

  - 工作階段邊界控制器 (SBC)。

測試 Test-cstrunkconfiguration cmdlet 驗證 （視使用者所撥打） 的電話號碼可以轉換成 E.164 網路，並透過指定的 SIP 主幹路由傳送。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行測試 Test-cstrunkconfiguration 指令程式，您必須先使用 Get-cstrunkconfiguration cmdlet 來擷取 SIP 主幹組態設定; 執行個體該執行個體然後以管線傳輸至測試 Test-cstrunkconfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

執行測試 Test-cstrunkconfiguration 第一個執行 Get-cstrunkconfiguration 而將無法運作。 例如，此命令將會失敗但不傳回任何資料：

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

如果您有多個 SIP 主幹組態設定集合，您可以使用類似下列的命令來同時測試每個集合針對相同的電話號碼：

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

如需詳細資訊，請參閱 < 測試 Test-cstrunkconfiguration cmdlet 的說明 」 文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果測試 Test-cstrunkconfiguration 可以再撥打電話對撥打的號碼，轉譯的電話號碼 （以 E.164 格式） 及用來轉譯該電話號碼的規則會同時顯示在畫面上：

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 全域/Redmond

如果測試失敗，測試 Test-cstrunkconfiguration 會傳回空的屬性值：

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

如果測試 Test-cstrunkconfiguration 不會傳回相符項目，通常表示正在測試主幹組態設定中沒有撥出電話號碼轉譯規則能夠將撥打的號碼轉換為 E.164 格式。 若要擷取指派給主幹組態設定集合的轉譯規則，您可以使用類似如下的語法：

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

會傳回的資訊類似的每個轉譯規則：

描述： 沒有國家/地區或區域程式碼的電話號碼。

模式: ^\\+ (\\d\*) $

`Translation : $1`

名稱： NoAreaCode

此時，您可以檢查圖樣屬性 （也就是[規則運算式](https://go.microsoft.com/fwlink/?linkid=400464)的字串） 的值若要查看是否任何轉譯規則設定為處理撥打的號碼。 如果不是，您也必須變更其中一個現有的規則 (Set-CsOutboundTranslationRule)，或使用 New-csoutboundtranslationrule cmdlet 來新增至集合中新的規則。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試 Test-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

