---
title: 設定以位置為基礎的路由的網路設定
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對直接路由建立及設定以位置為基礎的路由的網路區域、網站和子網。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245103"
---
# <a name="configure-network-settings-for-location-based-routing"></a>設定以位置為基礎的路由的網路設定

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

如果您尚未這麼做, 請參閱[直接路由的 [規劃位置] 路由](location-based-routing-plan.md), 以查看在設定位置式路由的網路設定之前, 您必須採取的其他步驟。

本文說明如何設定以位置為基礎的路由的網路設定。 在貴組織中部署手機系統直接路由之後, 接下來的步驟是建立及設定網路區域、網路網站和網路子網。 若要完成本文中的步驟, 您需要熟悉 PowerShell Cmdlet。 若要深入瞭解, 請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

## <a name="define-network-regions"></a>定義網路區域
 網路區域跨多個地理區域互連網路的各個部分。 使用[新的-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) Cmdlet 來定義網路區域。 請注意, RegionID 參數是代表區域地理位置的邏輯名稱, 沒有相依性或限制, 且 CentralSite &lt;site ID&gt;參數是選擇性的。 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在這個範例中, 我們會建立一個名為「印度」的網路區域。 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>定義網路網站

使用[新的-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
在這個範例中, 我們會在印度區域中建立兩個新的網路網站、新德里與 Hyderabad。 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
下表顯示在這個範例中定義的網路網站。 

||網站1 |網站2 |
|---------|---------|---------|
|網站識別碼    |    Site 1 (新德里)     |  Site 2 (Hyderabad)       |
|地區識別碼  |     地區 1 (印度)    |   地區 1 (印度)      |

## <a name="define-network-subnets"></a>定義網路子網

使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 來定義網路子網, 並將它們與網路網站建立關聯。 每個內部子網只能與一個網站建立關聯。 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
在這個範例中, 我們會在子網192.168.0.0 與新德里 network 網站之間以及子網2001之間建立關聯: 4898: e8:25: 844e: 926f: 85ad: dd8e 和 Hyderabad 網路網站。
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
下表顯示在這個範例中定義的子網。 

||網站1 |網站2 |
|---------|---------|---------|
|子網識別碼   |    含     |  2001: 4898: e8:25: 844e: 926f: 85ad: dd8e     |
|遮罩  |     24    |   120      |
|網站識別碼  | Site (新德里) | Site 2 (Hyderabad) |

針對多個子網, 您可以使用如下的腳本匯入 CSV 檔案。
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
在這個範例中, CSV 檔案看起來像這樣:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>定義外部子網
使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Cmdlet 來定義外部子網, 並將其指派給租使用者。 您可以為租使用者定義不受限制的子網數。 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
例如：
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>後續步驟
移至 [[啟用直接路由的以位置為基礎的路由](location-based-routing-enable.md)]。

### <a name="related-topics"></a>相關主題
- [規劃直接路由的以位置為基礎的路由](location-based-routing-plan.md)
- [以位置為基礎的路由術語](location-based-routing-terminology.md)
