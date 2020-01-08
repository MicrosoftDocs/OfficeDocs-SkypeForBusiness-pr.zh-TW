---
title: Lync Server 2013：使用 Lync Online 設定同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee7cf175e2ca46a54f3c6505fe5f94b69120763
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40981709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>使用 Lync Online 設定 Lync Server 2013 的同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-08-15_

請依照本節中的步驟，設定您的內部部署與商務用 Skype Online 之間的互通性。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>針對與商務用 Skype Online 的同盟設定您的內部部署邊緣服務

同盟可讓您內部部署中的使用者與貴組織中的 Office 365 使用者進行通訊。 若要設定同盟，請執行下列 Cmdlet：

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>針對共用的 SIP 位址空間設定您的商務用 Skype Online 租使用者

會話初始通訊協定（SIP）位址是網路上每個使用者的唯一識別碼，類似于電話號碼或電子郵件地址。 在您嘗試將 Lync 使用者從內部部署移至商務用 Skype Online 之前，您必須設定您的 Office 365 租使用者，以與您的內部部署部署共用共用會話初始通訊協定（SIP）位址空間。 如果未設定，您可能會看到下列錯誤訊息：

Move-csuser： HostedMigration fault：錯誤 = （510），描述 = （該使用者的租使用者並未啟用共用的 sip 位址空間。）

若要設定共用的 SIP 位址空間，請使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
若要在商務用 Skype Online 中建立遠端 PowerShell 會話，您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 模組，您可以在此處取得[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)：。

安裝模組後，您可以使用下列 Cmdlet 建立遠端會話：

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，請參閱[使用 Windows PowerShell 連線到商務用 Skype online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

如需有關使用商務用 Skype Online PowerShell 模組的詳細資訊，請參閱[使用 Windows PowerShell 管理商務用 Skype online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

<div>

## <a name="see-also"></a>請參閱


[新-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

