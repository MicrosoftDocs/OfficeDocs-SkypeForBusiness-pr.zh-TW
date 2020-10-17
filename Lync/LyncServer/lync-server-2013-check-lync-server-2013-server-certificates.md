---
title: Lync Server 2013：檢查 Lync Server 2013 伺服器憑證
description: Lync Server 2013：請檢查 Lync Server 2013 伺服器憑證。
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
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543589"
---
# <a name="check-lync-server-2013-server-certificates"></a>檢查 Lync Server 2013 伺服器憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Get-CsCertificate Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Get-CsCertificate Cmdlet 可讓您檢索每一部 Lync Server 憑證的相關資訊。 這一點特別重要，因為憑證具有內建的到期日。 例如，私下發行的憑證通常會在12個月後到期。 如果任何 Lync Server 憑證到期，則在續訂或取代憑證之前，您會失去伴隨的功能。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要傳回每個 Lync Server 憑證的詳細資訊，請執行下列命令：

`Get-CsCertificate`

或者，您可以根據到期日來篩選傳回憑證資訊。 例如，此命令會將傳回的資料限制在2014年6月1日後到期 (無法使用的憑證) ：

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

如需詳細資訊，請參閱 Get-CsCertificate Cmdlet 的說明文件。

請注意，雖然 Test-CsCertificateConfiguration Cmdlet 存在，但對系統管理員而言並不十分實用。  (相反地，該 Cmdlet 主要是由憑證嚮導使用。 ) 雖然 Cmdlet 能夠運作，但它傳回的資訊的價值最低，如下列輸出範例所示：

指紋使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 預設值

</div>

<div>

## <a name="reviewing-the-output"></a>檢查輸出

Get-CsCertificate Cmdlet 會針對每個 Lync Server 憑證傳回類似下列的資訊：

發行者： CN = FabrikamCA

NotAfter： 12/28/2015 3:35:41 PM

NotBefore： 1/2/2014 12:49:37 PM

SerialNumber：611BB01200000000000C

Subject： CN = LYNC-SE.fabrikam.com

AlternativeNames： {sip.fabrikam.com、LYNC-SE.fabrikam.com、

meet.fabrikam.com，admin.fabrikam.com

指紋： A9D51A2911C74FABFF7F2A8A994B20857D399107

使用：預設值

一般來說，與 Lync Server 憑證有關的主要問題包括日期和時間，例如當憑證生效時 (NotBefore) 或到期時 (NotAfter) 。 因為這些日期和時間很重要，您可能想要將傳回的資料限制為憑證使用、憑證序號碼和憑證到期日等資訊。然後，您可以快速查看所有憑證和到期的時間。 若只要傳回該資訊，請使用命令和如下所示的選項：

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

該命令會傳回與下列類似的資料，並以到期日的順序排序憑證：

使用 SerialNumber NotAfter

\--- ------------ --------

預設 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

如果您有憑證問題，您可能想要查看為憑證設定的 AlternativeNames。 乍一看，似乎是問題。 根據預設，根據主控台視窗的大小而定，Get-CsCertificate 可能無法顯示所有的名稱：

AlternativeNames： {sip.fabrikam.com、LYNC.fabrikam.com、

meet.fabrikam.com，fabrika。

若要查看指派給憑證的所有替代名稱，請使用類似下列的命令：

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

應該在憑證上顯示所有替代名稱：

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

