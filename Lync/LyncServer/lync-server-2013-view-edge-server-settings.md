---
title: Lync Server 2013：查看邊緣伺服器設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看邊緣伺服器設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_

必須針對配置管理資料庫中的資料來審查一般邊緣伺服器設定，以協助保證所有變更都已按照已定義的變更控制程式進行記錄。

其他檢查可能包含下列各節所述的專案：

<div>

## <a name="verify-the-allow-and-block-lists"></a>確認 [允許] 與 [封鎖] 清單

驗證聯盟網域的 SIP URI "Allow" 和 "Block" 清單，以判斷列出的命名空間是否仍然有效。

您可以使用 Windows PowerShell 來查看允許和封鎖的清單。 若要查看 [允許的網域] 清單上的網域，請執行下列 Windows PowerShell 命令：

`Get-CsAllowedDomain`

該命令會針對 [允許的網域] 清單上的網域傳回如下所示的資訊：

身分識別： contoso.com

網域： contoso.com

ProxyFqdn :

評論

MarkForMonitoring： False

評論

若要查看 [封鎖的網域] 清單中的網域，請使用下列命令：

`Get-CsBlockedDomain`

接著，您將會收到針對每個封鎖網域的相關資訊：

身分識別： tailspintoys.com

網域： tailspintoys.com

Windows PowerShell 也能讓您確認您可以連線到 [允許的網域] 清單中的網域。 例如，這個命令會驗證 Edge 伺服器（TargetFqdn）和聯盟網域 contoso.com 之間的連線：

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

這個命令會確認您的 Edge 伺服器與您在 [允許的網域] 清單中找到的所有網域之間的連線：

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>驗證多個邊緣伺服器相同

如果多個邊緣伺服器部署在負載均衡的陣列中，我們建議您驗證陣列中的所有邊緣伺服器是否都以相同的方式進行設定。

您可以在 [電腦管理] 管理單元的 Lync Server 2013 延伸的詳細資料窗格中，查看 Edge 伺服器的設定。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

