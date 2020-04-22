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
ms.openlocfilehash: 34e96ec4aac4573a05e50eb1b13469731068b6db
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="f05cd-102">設定 Lync Server 2013 與 Lync Online 的同盟</span><span class="sxs-lookup"><span data-stu-id="f05cd-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f05cd-103">_**主題上次修改日期：** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="f05cd-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="f05cd-104">遵循本節中的步驟，設定您的內部部署和商務用 Skype Online 之間的互通性。</span><span class="sxs-lookup"><span data-stu-id="f05cd-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="f05cd-105">設定您的 On-Premises Edge Service 以進行與商務用 Skype Online 的同盟</span><span class="sxs-lookup"><span data-stu-id="f05cd-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="f05cd-106">同盟可讓內部部署的使用者能夠與您組織中的 Microsoft 365 或 Office 365 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="f05cd-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="f05cd-107">若要設定同盟，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f05cd-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="f05cd-108">設定共用 SIP 位址空間的商務用 Skype Online 租使用者</span><span class="sxs-lookup"><span data-stu-id="f05cd-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="f05cd-109">會話初始通訊協定（SIP）位址是網路上每位使用者的唯一識別碼，類似于電話號碼或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f05cd-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="f05cd-110">在您嘗試將 Lync 使用者從內部部署移至商務用 Skype Online 之前，您必須設定 Office 365 組織，以與您的內部部署共用共用會話初始通訊協定（SIP）位址空間。</span><span class="sxs-lookup"><span data-stu-id="f05cd-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="f05cd-111">若未設定此設定，您可能會看到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f05cd-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="f05cd-112">Move-CsUser： HostedMigration fault： Error = （510），Description = （此使用者的租使用者未啟用共用 sip 位址空間。）</span><span class="sxs-lookup"><span data-stu-id="f05cd-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="f05cd-113">若要設定共用 SIP 位址空間，使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f05cd-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="f05cd-114">若要建立與商務用 Skype Online 的遠端 PowerShell 會話，您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 模組，您可以在這裡找到[https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911)：。</span><span class="sxs-lookup"><span data-stu-id="f05cd-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="f05cd-115">安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：</span><span class="sxs-lookup"><span data-stu-id="f05cd-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

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

<span data-ttu-id="f05cd-116">如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，請參閱[使用 Windows PowerShell 連線到商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f05cd-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="f05cd-117">如需使用商務用 Skype Online PowerShell 模組的詳細資訊，請參閱[使用 Windows PowerShell 管理商務用 Skype online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f05cd-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f05cd-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f05cd-118">See Also</span></span>


[<span data-ttu-id="f05cd-119">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f05cd-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

