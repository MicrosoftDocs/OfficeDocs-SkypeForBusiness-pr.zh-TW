---
title: Lync Server 2013：測試 Lync Phone Edition 登入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Lync Phone Edition 登入

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsPhoneBootstrap Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsPhoneBootstrap Cmdlet 可讓管理員驗證指定的使用者（使用電話號碼和指派給他/她的 PIN）可以從 Lync 2013 Phone 版本相容的裝置登入系統。 （實際不需要裝置就能執行測試。）

為了讓測試 CsPhoneBootstrap 進行檢查，託管已測試之使用者帳戶的註冊機構池必須使用 DHCP 來探索。 若要判斷註冊機構是否以這種方式被發現，請使用 Cmdlet CsRegistrarConfiguration 並檢查 EnableDHCPServer 屬性的值。 如果此屬性設定為 False，您必須使用 CsRegistrarConfiguration 將屬性值設定為 True，並使用 DHCP 讓註冊機構可搜尋。 您也可以使用企業 DHCP 伺服器並設定 Lync 伺服器專用的選項，來完成此動作。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 CsPhoneBootstrap Cmdlet，您必須至少為有效的 Lync Server 使用者提供電話號碼和用戶端個人識別碼（PIN）。 例如，這個命令會測試具有電話號碼12065551219和 PIN 0712 的使用者的登入能力：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

若要進行更完整的檢查，您也可以包含使用者的 SIP 位址。 在這種情況下，電話號碼、用戶端 PIN 及 SIP 位址都必須是有效的，測試才能成功：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

如需詳細資訊，請參閱[Test CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者能夠連線到 Lync Server，您將會收到與此類似的輸出，結果屬性標示為**成功：**

TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService （.svc）

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.3981276

出錯

自檢

如果指定的使用者無法進行連線，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延隔時間：00：00：04.1993845

錯誤：錯誤-沒有收到 Web 票證服務的回應。

自檢

先前的輸出指出由於 Web 票證服務沒有回應，測試失敗。 這可能是因為服務本身有問題，或是由於 SIP 位址、電話號碼或用戶端 PIN 傳遞到測試 CsPhoneBootstrap。 您可以使用類似以下的命令來驗證使用者的 SIP 位址和電話號碼：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

而且，您可以使用下列命令驗證使用者是否有有效的 PIN：

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

如果測試 CsPhoneBootstrap 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPhoneBootstrap 會傳回其嘗試的每個動作的逐步帳戶。 例如，以下是失敗登錄的一部分輸出，其中包含不正確 PIN 的會話：

將 PIN 驗證與手機\\Ext： 12065551219 PIN：0712結合使用

無法取得網頁入場券

確認

\-Web 服務 url 有效且 web 服務正常運作

\-如果您使用\\PhoneNo PIN 來進行驗證，請確定它們與使用者 uri 相符

\-如果您使用\\的是 NTLM Kerberos 驗證，請確認您提供的是有效認證

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsPhoneBootstrap 可能失敗的一些常見原因：

  - 您可能指定了不正確 SIP 位址。 您可以使用如下的命令來驗證 SIP 位址是否正確：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了不正確 PIN 碼。 雖然您無法取得使用者的 PIN 碼，但您可以使用類似以下的命令，確認使用者至少擁有 PIN 碼：
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了不正確電話號碼。 您可以使用類似下列的命令來驗證使用者的電話：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - 註冊機構池不是 DHCP 啟用的。 若要判斷您的註冊機構池是否已啟用 DHCP，請執行 CsRegistrarConfiguration Cmdlet，然後檢查 EnableDHCPServer 屬性的值。 例如：
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

