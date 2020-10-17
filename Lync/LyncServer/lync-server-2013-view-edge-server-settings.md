---
title: Lync Server 2013：查看 Edge Server 設定
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
ms.openlocfilehash: ceb3f536a0aadb181b1b740d74c8f61715efed21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506390"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看 Edge Server 設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_

應該對照設定管理資料庫中的資料來複查一般 Edge Server 設定，以協助保證所有的變更都是根據定義的變更控制程式所記錄。

其他檢查可以包含下列各節所述的專案：

<div>

## <a name="verify-the-allow-and-block-lists"></a>確認允許和封鎖清單

請驗證同盟網域的 SIP URI 「允許」和「封鎖」清單，以判斷列出的命名空間是否仍然有效。

您可以使用 Windows PowerShell 來查看允許和封鎖的清單。 若要查看允許的網域清單上的網域，請執行下列 Windows PowerShell 命令：

`Get-CsAllowedDomain`

該命令會針對允許的網域清單上的網域，傳回類似以下的資訊：

身分識別： contoso.com

網域： contoso.com

ProxyFqdn

評論：

MarkForMonitoring： False

評論：

若要查看封鎖的網域清單上的網域，請使用下列命令：

`Get-CsBlockedDomain`

接著，您將會收到每個封鎖網域的資訊，例如：

身分識別： tailspintoys.com

網域： tailspintoys.com

Windows PowerShell 也可讓您確認您可以連線至允許的網域清單上的網域。 例如，此命令會驗證 Edge Server (TargetFqdn) 與同盟網域 contoso.com 之間的連線：

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

而且，此命令會驗證您的 Edge Server 與允許的網域清單上的所有網域之間的連線：

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>驗證多部 Edge Server 相同

如果有多部 Edge Server 部署在負載平衡陣列中，建議您驗證陣列中的所有 Edge Server 都是以相同的方式來設定。

您可以在 [電腦管理] 嵌入式管理單元的 Lync Server 2013 擴充功能的詳細資料窗格中，查看 Edge server 的設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

