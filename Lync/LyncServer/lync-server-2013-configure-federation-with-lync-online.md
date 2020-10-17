---
title: Lync Server 2013：設定與 Lync Online 的同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfeffc8a72d26167b9771e6437d21ba55c8f5636
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525950"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>設定 Lync Server 2013 與 Lync Online 的同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-08-15_

遵循本節中的步驟，設定您的內部部署和商務用 Skype Online 之間的互通性。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>設定您的 On-Premises Edge Service 以進行與商務用 Skype Online 的同盟

同盟可讓內部部署的使用者能夠與您組織中的 Microsoft 365 或 Office 365 使用者通訊。 若要設定同盟，請執行下列 Cmdlet：

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>設定共用 SIP 位址空間的商務用 Skype Online 租使用者

會話初始通訊協定 (SIP) 位址是網路上每位使用者的唯一識別碼，類似于電話號碼或電子郵件地址。 在您嘗試將 Lync 使用者從內部部署移至商務用 Skype Online 之前，您必須設定 Microsoft 365 或 Office 365 組織，以共用內部部署的共用會話初始通訊協定 (SIP) 位址空間。 若未設定此設定，您可能會看到下列錯誤訊息：

Move-CsUser： HostedMigration fault： Error = (510) ，描述 = (此使用者的租使用者未啟用共用 sip 位址空間。 ) 

若要設定共用 SIP 位址空間，使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
若要建立與商務用 Skype Online 的遠端 PowerShell 會話，您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 模組，您可以在這裡找到： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) 。

安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：

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

如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，請參閱 [使用 Windows PowerShell 連線到商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

如需使用商務用 Skype Online PowerShell 模組的詳細資訊，請參閱 [使用 Windows PowerShell 管理商務用 Skype online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
