---
title: Lync Server 2013： 檢視 Edge Server 設定
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
ms.openlocfilehash: 03eb804329bd0e8ce5c502c44d1ef1071e19f65c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>在 Lync Server 2013 中檢視 Edge Server 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-20 個_

一般 Edge Server 設定應該檢閱對組態管理資料庫中的資料，以協助確保所有變更所都記載依定義的變更控制程序。

額外檢查可能包括下列各節所述：

<div>

## <a name="verify-the-allow-and-block-lists"></a>確認 [允許] 和 [封鎖清單

確認 SIP URI 「 允許 」 及 「 區塊 」 清單的同盟網域，以判斷是否列出命名空間仍然有效。

您可以使用 Windows PowerShell 來檢視允許和封鎖清單。 若要檢閱允許網域清單上的網域，請執行下列 Windows PowerShell 命令：

`Get-CsAllowedDomain`

該命令會傳回的資訊類似網域的允許網域清單上：

身分識別： contoso.com

網域： contoso.com

ProxyFqdn:

註解：

MarkForMonitoring: False

註解：

若要檢閱封鎖的網域清單上的網域，請使用此命令：

`Get-CsBlockedDomain`

接著，您會收到這每個封鎖的網域的資訊：

身分識別： tailspintoys.com

網域： tailspintoys.com

Windows PowerShell 也可讓您確認您可以連線到網域允許網域清單上。 例如，此命令會驗證您的 Edge Server (TargetFqdn) 與同盟的網域 contoso.com 之間的連線：

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

與此命令會驗證您的 Edge Server 與所有在您允許網域清單上找到的網域之間的連線：

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>確認 [多部 Edge Server 皆相同

如果負載平衡陣列中部署多部 Edge Server，建議您確認陣列中的所有 Edge Server 已都設定的方式相同。

在 [電腦管理] 嵌入式管理單元的 Lync Server 2013 副檔名的詳細資料窗格中，您可以檢視 Edge Server 的設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-csblockeddomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

