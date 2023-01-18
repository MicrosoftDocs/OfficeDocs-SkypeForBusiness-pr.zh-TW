---
title: 在 Microsoft Teams 中管理雲端語音功能的網路拓撲
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中設定雲端語音功能的網路設定。
ms.openlocfilehash: bdb81fa7f8dee559f7c47e276224ecb2333c7bb5
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812690"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>在 Microsoft Teams 中管理雲端語音功能的網路拓撲

如果貴組織正在部署直接路由或[動態緊急通話](configure-dynamic-emergency-calling.md)[的定位路由](location-based-routing-plan.md)，您必須設定網路設定，以搭配這些 Microsoft Teams 中的雲端語音功能使用。 網路設定是用來判斷 Teams 用戶端的位置，並包含網路區域、網路網站、子網和信任的 IP 位址。 視您要部署的雲端語音功能而定，您可以設定部分或所有這些設定。 若要深入瞭解這些字詞，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。

您可以在 Microsoft Teams 系統管理中心的 [**網路拓撲**] 頁面或使用Windows PowerShell設定網路設定。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心設定網路設定

您可以在 [網路 **拓撲**] 頁面的 [**網路網站**] 索引標籤上定義網路區域、網路網站和子網。 您可以在這裡建立或修改網路網站、建立網站與網路區域的關聯、將子網與網站建立關聯、開啟以位置為基礎的路由，以及指派緊急原則給網站。 您也可以新增可全球用於所有網站的網路區域。

#### <a name="add-and-configure-a-network-site"></a>新增及設定網路網站

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，然後按一下 [**網路網站] 索引** 標籤。
2. 按一下 **[新增**]，然後輸入網站的名稱和描述。

    ![[新增網路網站] 頁面的螢幕擷取畫面。](media/manage-network-topology-add-site.png)

3. 若要建立網站與網路區域的關聯，請按一下 **[新增網路區域**]，選取現有區域或按一下 [ **新增** ] 以新增區域，然後按一下 [ **連結]**。  
4. 若要啟用網站Location-Based路由，請開啟 **[以位置為基礎的路由]**。
5. 若要將緊急服務原則指派給網站，請執行下列一或兩個動作：

    - 如果貴組織使用通話方案、運算子連線或直接路由，請在 [ **緊急通話原則**] 底下，選取所要的原則。
    - 如果貴組織已部署直接路由，請在 [ **緊急通話路由原則**] 底下，選取所要的原則。

6. 若要建立子網與網站的關聯，請在 [ **子網] 底** 下，按一下 [ **新增子網]**。 指定 IP 版本、IP 位址、網路範圍、新增描述，然後按一下 [ **套用]**。 每個子網都必須與特定網站相關聯。
7. 按一下 [儲存]。

#### <a name="modify-a-network-site"></a>修改網路網站

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，然後按一下 [**網路網站] 索引** 標籤。
2. 按一下網站名稱左側以選取網站，然後按一下 [ **編輯]**。
3. 進行您要的變更，然後按一下 [ **儲存]。**

### <a name="manage-external-trusted-ip-addresses"></a>管理外部信任的 IP 位址

您可以在 Microsoft Teams 系統管理中心的 [**網路拓撲**] 頁面的 [**信任的 IP**] 索引標籤上管理外部信任的 IP 位址。 您可以新增無限數目的外部信任 IP 位址。

#### <a name="add-a-trusted-ip-address"></a>新增信任的 IP 位址

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，然後按一下 [**信任的 IP] 索引卷** 標。
2. 按一下 [ **新增]**。
3. 在 [ **新增信任的 IP 位址** ] 窗格中，指定 IP 版本、IP 位址、網路範圍、新增描述，然後按一下 [ **套用]**。

    ![[新增信任的 IP 位址] 窗格的螢幕擷取畫面。](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>編輯信任的 IP 位址

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，然後按一下 [**信任的 IP] 索引卷** 標。
2. 按一下 IP 位址的左側以選取該 IP 位址，然後按一下 [ **編輯]**。
3. 在 [ **編輯信任的 IP 位址** ] 窗格中，進行您要的變更，然後按一下 [ **套用]**。

## <a name="configure-network-settings-using-powershell"></a>使用 PowerShell 設定網路設定

若要完成本節中的步驟，您需要熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>定義網路區域

 使用 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) Cmdlet 來定義網路區域。 請注意，RegionID 參數是一個邏輯名稱，代表區域的地理位置，沒有相依性或限制，而且 CentralSite &lt; 網站識別碼 &gt; 參數是選用的。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在此範例中，我們建立了一個名為「印度」的網路區域。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

另請參閱 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion)。

### <a name="define-network-sites"></a>定義網路網站

使用 [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。 每個網路網站都必須與網路區域建立關聯。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

在此範例中，我們建立了兩個新的網路網站，即印度地區的索里拉巴和索里拉巴。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

下表顯示此範例中定義的網路網站。

|&nbsp;|網站 1 |網站 2 |
|---------|---------|---------|
|網站識別碼    |    網站 1 (關)      |  網站 2 (文拉巴)        |
|地區識別碼  |      (印度地區 1)     |    (印度地區 1)       |

另請參閱 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite)。

### <a name="define-network-subnets"></a>定義網路子網

使用 [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 來定義網路子網，並將它們與網路網站建立關聯。 每個網路子網只能與一個網站相關聯。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

在此範例中，我們建立了子網 192.168.0.0 與並行網路網站與子網 2001：4898：e8：25：844e：926f：85ad：dd8e 與內文拉巴網路網站之間的關聯。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

下表顯示此範例中定義的子網。

|&nbsp;|網站 1 |網站 2 |
|---------|---------|---------|
|子網識別碼   |    192.168.0.0     |  2001：4898：e8：25：844e：926f：85ad：dd8e     |
|面具  |     24    |   120      |
|網站識別碼  | 網站 (日)  | 網站 2 (文拉巴)  |

對於多個子網，您可以使用下列腳本匯入 CSV 檔案。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

在此範例中，CSV 檔案看起來像這樣：

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


另請參閱 [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet)。


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>定義外部信任 IP 位址 (外部子網) 

使用 [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Cmdlet 來定義外部子網，並將它們指派給租使用者。 您可以為租使用者定義無限數目的外部子網。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

例如：

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

另請參閱 [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="enabling-network-roaming-policies"></a>啟用網路漫遊原則

設定網路漫遊原則之後，您必須在 Teams 管理員中心的 [會議>會議原則] 底下，啟用每一個 _ *Meeting* 原則* 內的 **網路設定查閱****_**

您可以編輯全域原則，或建立新原則，並將原則指派給特定使用者。

## <a name="related-topics"></a>相關主題

- [Teams 中雲端語音功能的網路設定](cloud-voice-network-settings.md)
