---
title: Lync Server 2013： 核取 Lync Server 2013 伺服器憑證
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
ms.openlocfilehash: 11c5e545bc00de48fa5590dc8c4b119a46ffe9e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>檢查 Lync Server 2013 伺服器憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-01_


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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Get-cscertificate cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

Get-cscertificate cmdlet 可讓您擷取每個 Lync 伺服器憑證的相關資訊。 這是特別重要，因為憑證具有內建到期日期。 例如、 私下發出的憑證通常 12 個月後過期。 如果任何您 Lync Server 的憑證到期然後該憑證會更新或取代之前，您會失去隨附的功能。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要傳回每個 Lync 伺服器的相關資訊的憑證只會執行下列命令：

`Get-CsCertificate`

或者，您可以篩選傳回的憑證資訊會根據 [到期日。 例如，此命令傳回的資料限制為過期的憑證 （無法使用之後） 2014 年 6 月 1 日：

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

如需詳細資訊，請參閱 < Get-cscertificate cmdlet 的說明文件。

請注意，雖然 Test-cscertificateconfiguration 指令程式已存在，但它不是很有用給系統管理員。 （相反地，該 cmdlet 主要由使用 [憑證] 精靈。）雖然指令程式的運作方式，它會傳回的資訊是最小值，下列的輸出範例所示：

指紋使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 預設

</div>

<div>

## <a name="reviewing-the-output"></a>檢閱輸出

Get-cscertificate cmdlet 會傳回類似以下的每個 Lync 伺服器憑證資訊：

簽發者： CN = FabrikamCA

NotAfter: 2015/12/28/下午 3:35:41

NotBefore: 1/2/2014年下午 12:49:37

SerialNumber: 611BB01200000000000C

主旨： CN = LYNC SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com，LYNC SE.fabrikam.com，

meet.fabrikam.com，admin.fabrikam.com...}

指紋： A9D51A2911C74FABFF7F2A8A994B20857D399107

使用： 預設值

一般而言，涉及 Lync Server 憑證熱門問題牽涉到日期和時間，例如憑證時才會生效 (NotBefore) 或到期 (NotAfter)。 因為這些日期和時間是非常重要，所以您可能想要限制資訊例如憑證使用、 憑證序號及憑證到期日，傳回的資料然後您可以快速檢閱所有憑證和時將會到期。 若要傳回只是該資訊，請使用與選項搭配命令所示：

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

該命令會傳回類似下列命令，以其到期日期的順序排序的憑證資料：

使用 SerialNumber NotAfter

\--- ------------ --------

預設 611BB01200000000000C 2015/12/28 下午 3:35:41

WebServicesInteral 32980AA20BBB20000191 2016 02 月 15 日下午 2:16:12

WebServicesExternal 0451B012003872651A0C 2016 02 月 20 日上午 7:11:58

如果您有憑證問題，您可能想要檢閱憑證設定 AlternativeNames。 乍看之下，這就好像有問題。 依預設，並會根據您的主控台視窗的大小，Get-cscertificate 可能無法顯示所有名稱：

AlternativeNames: {sip.fabrikam.com，LYNC.fabrikam.com，

meet.fabrikam.com，admin.fabrika...}

若要查看所有另一個指派給憑證的名稱，請使用類似這樣的命令：

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

應會顯示您所有的替代名稱的憑證：

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

