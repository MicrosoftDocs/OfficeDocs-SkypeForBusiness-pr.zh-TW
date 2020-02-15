---
title: Lync Server 2013： 使用 Lync Online 設定同盟
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
ms.openlocfilehash: fb679f8bf0fae046bea0177daab22203bbf9aef1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>使用 Lync Online 設定 Lync Server 2013 的同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-08-15_

遵循此區段可設定您的內部部署和 Skype 之間的互通性商務 Online 中的步驟。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>設定您的內部 Edge 服務進行同盟與 Skype 商務 Online

同盟可讓您的內部部署使用者與貴組織中的 Office 365 使用者進行通訊。 若要設定同盟，請執行下列 cmdlet:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>設定您 Skype for Business Online 租用戶共用的 SIP 位址空間

工作階段初始通訊協定 (SIP) 位址是在網路上，類似的電話號碼或電子郵件地址每位使用者的唯一識別碼。 您嘗試將商務用 skype 移動 Lync 使用者從內部部署之前，您需要設定您的 Office 365 租用戶，您在內部部署與共用的共用工作階段初始通訊協定 (SIP) 位址空間。 如果未設定，您可能會看到下列錯誤訊息：

Move-csuser: HostedMigration 容錯： Error=(510)，描述 = （此使用者的租用戶未啟用共用的 sip 位址空間）。

若要設定共用的 SIP 位址空間，建立線上商務用 Skype 的遠端 PowerShell 工作階段，並執行下列 cmdlet:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
若要建立遠端 PowerShell 工作階段與 Skype for Business Online，您必須先安裝 Windows PowerShell，您可以在這裡取得 Skype for Business Online 模組： [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)。

安裝模組之後，您可以建立遠端工作階段使用下列 cmdlet:

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

如需如何建立商務用 Skype 的遠端 PowerShell 工作階段的詳細資訊，請參閱[連線到商務用 Skype 商務線上使用 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

如需使用 Skype for Business Online PowerShell 模組的詳細資訊，請參閱[使用 Windows PowerShell 來管理商務用 Skype](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

