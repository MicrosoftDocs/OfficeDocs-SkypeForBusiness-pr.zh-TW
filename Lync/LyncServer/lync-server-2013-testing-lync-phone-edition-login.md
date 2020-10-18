---
title: Lync Server 2013：測試 Lync Phone Edition 登入
description: Lync Server 2013：測試 Lync Phone Edition 登入。
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
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575239"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Lync Phone Edition 登入

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPhoneBootstrap Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsPhoneBootstrap Cmdlet 可讓系統管理員使用 Lync 2013 Phone Edition 相容裝置登入系統，以驗證指定的使用者（使用指派的電話號碼和 PIN 碼）。  (實際執行測試時，不需要裝置。 ) 

為了讓 Test-CsPhoneBootstrap 進行檢查，主控所測試之使用者帳戶的註冊集區集區必須可透過 DHCP 來探索。 若要判斷註冊機構是否以這種方式被探索，請使用 Cmdlet Get-CsRegistrarConfiguration，並檢查 EnableDHCPServer 屬性的值。 如果此屬性設為 False，則必須使用 Set-CsRegistrarConfiguration 將屬性值設定為 True，並讓註冊機構可使用 DHCP 加以探索。 您也可以使用企業 DHCP 伺服器及設定 Lync Server 特有的選項來執行此動作。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test-CsPhoneBootstrap Cmdlet，您必須至少為有效的 Lync Server 使用者提供電話號碼及用戶端個人識別碼 (PIN) 。 例如，下列命令會測試具有電話號碼12065551219和 PIN 碼0712之使用者的登入能力：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

若要進行更完整的檢查，您也可以包含使用者的 SIP 位址。 在此情況下，必須全部有效的電話號碼、用戶端 PIN 和 SIP 位址，才能成功測試：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

如需詳細資訊，請參閱 [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者能夠連線至 Lync 伺服器，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**

TargetUri： https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.3981276

錯誤：

診斷：

如果指定的使用者無法進行連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00：00：04.1993845

錯誤：錯誤-沒有為 Web-Ticket 服務接收任何回應。

診斷：

先前的輸出說明測試失敗，因為 Web 票證服務沒有回應。 這可能是因為服務本身發生問題，或是因為 SIP 位址、電話號碼或用戶端 PIN 碼已傳遞至 Test-CsPhoneBootstrap。 您可以使用類似下列的命令來驗證使用者的 SIP 位址和電話號碼：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

您可以使用下列命令來確認使用者是否有有效的 PIN 碼：

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

如果 Test-CsPhoneBootstrap 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

包含 Verbose 參數時，Test-CsPhoneBootstrap 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如，以下是失敗登入的部分輸出，其中包含不正確 PIN 碼的會話：

使用 PIN 驗證搭配電話 \\ 分機： 12065551219 PIN：0712

無法取得 web 票證

檢查：

\- Web 服務 url 有效且 web 服務可運作

\- 若要使用 PhoneNo \\ PIN 來驗證，請確定它們符合使用者 uri

\- 若要使用 NTLM \\ Kerberos 驗證，請確定您提供有效的認證

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsPhoneBootstrap 可能失敗的常見原因：

  - 您可能指定了不正確 SIP 位址。 您可以使用類似下列的命令來驗證 SIP 位址是否正確：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了不正確 PIN 碼。 雖然您無法取回使用者的 PIN 碼號碼，但您可以使用類似下列的命令，確認使用者至少具有 PIN 碼號碼：
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了不正確電話號碼。 您可以使用類似下列的命令來驗證使用者的電話：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - 註冊機構集區未啟用 DHCP。 若要判斷您的註冊區集區是否已啟用 DHCP，請執行 Get-CsRegistrarConfiguration Cmdlet，並檢查 EnableDHCPServer 屬性的值。 例如：
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

