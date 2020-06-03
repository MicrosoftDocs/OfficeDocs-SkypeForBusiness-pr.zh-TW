---
title: 在 Microsoft 團隊中管理雲端語音功能的網路拓撲
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何針對 Microsoft 團隊中的雲端語音功能設定網路設定。
ms.openlocfilehash: 03eaeac1bce07cffa7dc000f964f080361a37d40
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539622"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>在 Microsoft 團隊中管理雲端語音功能的網路拓撲

如果您的組織要部署直接路由或[動態緊急通話](configure-dynamic-emergency-calling.md)[的位置路由](location-based-routing-plan.md)，您必須設定網路設定，以便與 Microsoft 團隊中的這些雲端語音功能搭配使用。 網路設定是用來判斷團隊用戶端的位置，包括網路區域、網路網站、子網及信任的 IP 位址。 視您部署的雲端語音功能和功能而定，您可以設定部分或所有的設定。 若要深入瞭解這些詞彙，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)。

您可以在 Microsoft 團隊系統管理中心的 [**網路拓撲**] 頁面或使用 Windows PowerShell 來設定網路設定。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心設定網路設定

[!INCLUDE [preview-feature](includes/preview-feature.md)]

您可以在 [**網路拓撲**] 頁面的 [**網路網站**] 索引標籤上定義網路區域、網路網站和子網。 您可以在這裡建立或修改網路網站、將網站與網路區域建立關聯、將子網與網站建立關聯、開啟以位置為基礎的路由，以及將緊急原則指派給網站。 您也可以新增可全域用於所有網站的網路區域。

#### <a name="add-and-configure-a-network-site"></a>新增及設定網路網站

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置**  >  **網路拓撲**]，然後按一下 [**網路網站**] 索引標籤。
2. 按一下 [**新增**]，然後輸入網站的名稱和描述。

    ![[新增網路] 網站頁面的螢幕擷取畫面](media/manage-network-topology-add-site.png)

3. 若要將網站與網路區域建立關聯，請按一下 [**新增網路區域**]，選取現有的區域，或按一下 [**新增**] 以新增區域，然後按一下 [**連結**]。  
4. 若要啟用網站的位置路由，請開啟 [以位置為**基礎的路由**]。
5. 若要指派緊急服務原則至網站，請執行下列其中一項或兩項操作：

    - 如果您的組織使用的是通話方案或部署的電話系統直接路由，請在 [**緊急通話原則**] 底下，選取您要的原則。
    - 如果您的組織已部署 [電話系統直傳送]，請在 [**緊急呼叫路由策略**] 底下，選取您要的原則。

6. 若要將子網與網站建立關聯，請按一下 [**子網**] 底下的 [**新增子網**] 指定 [IP 版本]、[IP 位址]、[網路範圍]、[新增描述]，**然後按一下 [** 套用]。 每個子網都必須與特定網站相關聯。
7. 按一下 [儲存]****。

#### <a name="modify-a-network-site"></a>修改網路網站

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置**  >  **網路拓撲**]，然後按一下 [**網路網站**] 索引標籤。
2. 按一下網站名稱左邊的，然後按一下 [**編輯**]，選取網站。
3. 進行您想要的變更，然後按一下 [**儲存]。**

### <a name="manage-external-trusted-ip-addresses"></a>管理外部信任的 IP 位址

您可以在 Microsoft 團隊系統管理中心的 [**網路拓撲**] 頁面上的 [**信任**的 ip] 索引標籤上，管理外部信任的 IP 位址。 您可以新增不受限制的外部信任 IP 位址數目。

#### <a name="add-a-trusted-ip-address"></a>新增信任的 IP 位址

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置**  >  **網路拓朴**]，然後按一下 [**信任的 IPs** ] 索引標籤。
2. 按一下 [**新增**]。
3. 在 [**新增信任的 IP 位址**] 窗格中，指定 [ip 版本]、[ip 位址]、[網路範圍]、[新增描述]，**然後按一下 [** 套用]。

    ![[新增信任的 IP 位址] 窗格的螢幕擷取畫面](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>編輯信任的 IP 位址

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置**  >  **網路拓朴**]，然後按一下 [**信任的 IPs** ] 索引標籤。
2. 按一下 IP 位址左邊的，然後按一下 [**編輯**] 來選取它。
3. 在 [**編輯信任的 IP 位址**] 窗格中，進行您要的變更，然後**按一下 [** 套用]。

## <a name="configure-network-settings-using-powershell"></a>使用 PowerShell 設定網路設定

若要完成本節中的步驟，您需要熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>定義網路區域

 使用[新的-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) Cmdlet 來定義網路區域。 請注意，RegionID 參數是代表區域地理位置的邏輯名稱，沒有相依性或限制，且 CentralSite &lt; SITE ID &gt; 參數是選擇性的。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在這個範例中，我們會建立一個名為「印度」的網路區域。
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

另請參閱[設定-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)。

### <a name="define-network-sites"></a>定義網路網站

使用[新的-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。 每個網路網站都必須與一個網路區域建立關聯。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

在這個範例中，我們會在印度區域中建立兩個新的網路網站、新德里與 Hyderabad。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

下表顯示在這個範例中定義的網路網站。

||網站1 |網站2 |
|---------|---------|---------|
|網站識別碼    |    Site 1 （新德里）     |  Site 2 （Hyderabad）       |
|地區識別碼  |     地區1（印度）    |   地區1（印度）      |

另請參閱[設定-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)。

### <a name="define-network-subnets"></a>定義網路子網

使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 來定義網路子網，並將它們與網路網站建立關聯。 每個網路子網只能與一個網站建立關聯。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

在這個範例中，我們會在子網192.168.0.0 與新德里 network 網站之間以及子網2001之間建立關聯：4898： e8：25：844e：926f：85ad： dd8e 和 Hyderabad 網路網站。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

下表顯示在這個範例中定義的子網。

||網站1 |網站2 |
|---------|---------|---------|
|子網識別碼   |    含     |  2001：4898： e8：25：844e：926f：85ad： dd8e     |
|遮罩  |     24    |   120      |
|網站識別碼  | Site （新德里） | Site 2 （Hyderabad） |

針對多個子網，您可以使用如下的腳本匯入 CSV 檔案。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

在這個範例中，CSV 檔案看起來像這樣：

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

另請參閱[設定-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)。

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>定義外部子網（外部信任的 IP 位址）

使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Cmdlet 來定義外部子網，並將其指派給租使用者。 您可以為租使用者定義不受限制的外部子網數。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

例如：

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

另請參閱[設定-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="related-topics"></a>相關主題

- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
