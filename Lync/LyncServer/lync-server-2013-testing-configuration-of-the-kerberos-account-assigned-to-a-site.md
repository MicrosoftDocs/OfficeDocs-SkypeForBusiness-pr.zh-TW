---
title: 測試指派給網站之 Kerberos 帳戶的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中測試指派給網站之 Kerberos 帳戶的設定

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsKerberosAccountAssignment Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsKerberosAccountAssignment Cmdlet 可讓您確認 Kerberos 帳戶是否與指定的網站產生關聯、該帳戶是否已正確設定，以及該帳戶是否如預期的方式運作。 Kerberos 帳戶是電腦帳戶，可充當執行網際網路資訊伺服器（IIS）之網站中所有電腦的驗證原則。 因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，而新的驗證程式則稱為 Kerberos web 驗證。 這可讓您使用單一帳戶來管理所有 IIS 伺服器。

如需詳細資訊，請參閱[Test CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

根據預設，測試 CsKerberosAccountAssignment 會在畫面上顯示極小的輸出。 相反地，由 Cmdlet 傳回的資訊會寫入 HTML 檔案。 因此，建議您在每次執行 Test CsKerberosAccountAssignment 時包含詳細參數和 Report 參數。 此詳細參數會在執行 Cmdlet 時，在螢幕上提供稍有更詳細的輸出。 Report 參數可讓您指定由 Test CsKerberosAccountAssignment 所產生之 HTML 檔案的檔案路徑和檔案名。 如果您不包含報表參數，HTML 檔案將會自動儲存到 [使用者] 資料夾，並指定如下的名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f .html。

當您執行 Test CsKerberosAccountAssignment 時，您也必須指定網站身分識別。 Kerberos 帳戶是在網站範圍內指派。

下列命令會執行 Test-CsKerberosAccountAssignment，並將輸出儲存到名為 C：\\Logs\\KerberosTest 的檔案中：

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

如需詳細資訊，請參閱[Test CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

Test CsKerberosAccountAssignment Cmdlet 不會傳回簡單的指示成功或失敗。 相反地，您必須使用 Internet Explorer 來查看產生的 HTML 檔案。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsKerberosAccountAssignment 可能失敗的一些常見原因：

  - 您可能指定了不正確的網站身分識別。 若要返回有效網站身分識別的清單，請使用此命令：
    
        Get-CsSite | Select-Identity Identity
    
    網站身分識別通常如下所示：
    
    網站：雷蒙德

  - 指定的網站可能沒有指派給它的 Kerberos 帳戶。 您可以執行如下的命令來判斷 Kerberos 帳戶是否已指派給網站：
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - 您的 Kerberos 帳戶可能有不正確密碼。 如果您在報表中收到下列錯誤訊息，您可能需要重設 Kerberos 帳戶密碼：
    
    InvalidKerberosConfiguration： Kerberos 配置無效。
    
    InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 配置無效。 預期指派的帳戶是 litwareinc\\kerberostest。 確定帳戶未過期，且電腦上設定的密碼與帳戶的 Active Directory 密碼相符。
    
    您可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) Cmdlet 來設定密碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

