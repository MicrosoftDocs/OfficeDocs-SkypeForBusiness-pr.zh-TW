---
title: Lync Server 2013：檢查 Lync Server 2013 伺服器憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>檢查 Lync Server 2013 伺服器憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-01_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsCertificate Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsCertificate Cmdlet 可讓您取得每個 Lync 伺服器憑證的相關資訊。 這特別重要，因為憑證擁有內建的到期日。 例如，私人頒發的憑證通常會在12個月後到期。 如果您的任何 Lync 伺服器憑證到期，您將會遺失隨附的功能，直到重新更新或取代憑證為止。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要返回每個 Lync 伺服器憑證的相關資訊，請執行下列命令：

`Get-CsCertificate`

或者，您可以根據到期日來篩選退回憑證資訊。 例如，這個命令會將傳回的資料限制為到期的憑證（在2014年6月1日之後就不能使用）：

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

如需詳細資訊，請參閱 CsCertificate Cmdlet 的說明文件。

請注意，雖然 CsCertificateConfiguration Cmdlet 存在，但管理員並不是很實用的。 （相反，該 Cmdlet 主要由證書嚮導使用）。雖然這個 Cmdlet 能正常運作，但其傳回的資訊是最小值，如下列輸出範例所示：

指紋使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 預設值

</div>

<div>

## <a name="reviewing-the-output"></a>檢查輸出

CsCertificate Cmdlet 會針對您的每個 Lync Server 憑證傳回如下所示的資訊：

Issuer （頒發者）： CN = FabrikamCA

NotAfter： 12/28/2015 3:35:41 PM

NotBefore： 1/2/2014 12:49:37 PM

SerialNumber：611BB01200000000000C

Subject： CN = LYNC-SE.fabrikam.com

AlternativeNames： {sip.fabrikam.com，LYNC-SE.fabrikam.com，

meet.fabrikam.com、admin.fabrikam.com ...}

Thumbprint： A9D51A2911C74FABFF7F2A8A994B20857D399107

使用：預設值

根據規則，涉及 Lync Server 憑證的主要問題涉及日期和時間，例如當證書生效（NotBefore）或到期時（NotAfter）。 由於這些日期和時間如此重要，因此您可能會想要將傳回的資料限制在證書使用、憑證序號及證書到期日等資訊。然後，您就可以快速查看所有憑證以及到期日。 若要只返回該資訊，請使用此命令與下列選項一起顯示：

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

該命令會傳回如下所示的資料，並以其到期日的順序排序憑證：

使用 SerialNumber NotAfter

\--- ------------ --------

預設 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

如果您有憑證問題，您可能會想要查看為憑證設定的 AlternativeNames。 乍一看，那就是問題。 根據預設，視主控台視窗的大小而定，CsCertificate 可能無法顯示所有名稱：

AlternativeNames： {sip.fabrikam.com，LYNC.fabrikam.com，

meet.fabrikam.com、fabrika ...}

若要查看指派給憑證的所有替代名稱，請使用類似以下的命令：

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

這應該會在您的憑證上顯示所有替代名稱：

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>請參閱


[CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

