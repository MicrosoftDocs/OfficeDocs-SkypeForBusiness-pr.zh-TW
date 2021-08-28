---
title: 在雲端連接器 Edition 中部署媒體旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 閱讀此主題以瞭解使用雲端連接器 Edition 版本2.0 和更新版本部署媒體旁路的步驟。
ms.openlocfilehash: edc00467d878f0f2ae137c86f179f864bb2ca53f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613773"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>在雲端連接器 Edition 中部署媒體旁路
 
> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

閱讀此主題以瞭解使用雲端連接器 Edition 版本2.0 和更新版本部署媒體旁路的步驟。 
  
媒體旁路可讓用戶端直接將媒體傳送到公用交換電話網路 (PSTN) 下一個躍點（閘道或會話邊界控制器 (SBC) ），並從媒體路徑中消除雲端連接器版本元件。 另請參閱 [規劃雲端連接器 Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>啟用媒體旁路

若要啟用媒體旁路，您必須設定媒體旁路 web 服務的 DNS 名稱，並在租使用者設定中開啟媒體旁路。 媒體旁路 web 服務會自動在每家的轉送伺服器上進行部署。 租使用者管理員必須為混合語音服務 (網站) 挑選名稱，而且此名稱應來自為混合式語音註冊的 SIP 網域。 不管用戶端位置為何，所有雲端連接器裝置和所有 PSTN 網站上的服務名稱應該都相同。 Web 服務應該只可在網路內部使用。
  
租使用者管理員必須在內部實際執行 Active Directory 中設定 DNS A 記錄。 如果您有複雜的多網站環境，請參閱 [範例範例：在複雜的多網站環境中，媒體旁路網站 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS 記錄應該只解析內部網路用戶端;不應為外部網路用戶端解析。
  
設定 DNS 之後，使用遠端 PowerShell 商務用 Skype 系統管理員認證，連線至商務用 Skype Online。 如需詳細資訊，請參閱[設定 Windows PowerShell 的電腦](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
在 PowerShell 會話中，輸入下列命令以啟用媒體旁路：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

啟用媒體旁路是兩個步驟的處理常式。 New-CsNetworkMedia Cmdlet 不會立即儲存新的設定。它只會在記憶體中建立設定。 此 Cmdlet 所建立的物件必須儲存在變數中，然後指定給網路設定的 MediaBypassSettings 屬性。 如需詳細資訊，請參閱 [範例：在複雜的多網站環境中媒體旁路網站 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。
  
在內部部署和線上元件之間進行的複寫可能需要長達24小時，所以 Microsoft 建議您先執行必要的命令，再啟用使用者。
  
## <a name="confirm-media-bypass-settings"></a>確認媒體旁路設定

您可以檢查媒體旁路設定，如下所示。 
  
若要檢查您租使用者集區的線上複寫，請在遠端 PowerShell: 中執行下列命令：
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

若要檢查內部部署的複寫，請連線至雲端連接器轉送伺服器，在 PowerShell 中執行下列命令，並確認 Enabled = True 和 AlwaysBypass = True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

若要檢查用戶端設定，請登出商務用 Skype 用戶端，然後重新登入，並確認用戶端是否已收到服務 URL，如下所示：
  
1. 開啟%appdatalocal%\Microsoft\ Office \16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。 
    
2. 搜尋 hybridconfigserviceinternalurl 並確認 URL 與您定義的 URL 相符。
    
## <a name="change-media-bypass-parameters"></a>變更媒體旁路參數

租使用者管理員可以執行下列 Cmdlet，以變更 web 服務的 DNS 名稱：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 用戶端需要登出並登入以取得新的服務名稱並辨識變更。 
  
## <a name="temporarily-disable-media-bypass"></a>暫時停用媒體旁路

此案例可能會對疑難排解或維護十分有用。 若要停用服務，請執行下列 Cmdlet：
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

進行變更之後，可能需要一些時間才能將變更複寫到所有雲端連接器。 若要檢查複寫的狀態，請在雲端連接器轉送伺服器的 PowerShell 中執行下列 Cmdlet： 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

在變更複寫之後，轉送伺服器上的 web 服務會開始拒絕媒體旁路服務的用戶端要求。
  
## <a name="disable-media-bypass-permanently"></a>永久停用媒體旁路

若要永久停用媒體旁路，租使用者管理員必須執行下列命令： 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

系統管理員也需要從內部 DNS 伺服器移除媒體旁路的網頁位址。 進行變更之後，可能需要一些時間才能將變更複寫到所有雲端連接器裝置。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>範例：在複雜的多網站環境中，媒體旁路網站 DNS 記錄
<a name="Example"> </a>

用戶端將從內部 DNS 伺服器接收媒體旁路 web 服務的網址。 所有雲端連接器裝置和雲端連接器 PSTN 網站上的 web 服務名稱都是相同的。 在複雜的多網站環境中，我們建議您針對 Geo-Location 型流量管理使用 Windows 2016 DNS 原則，讓用戶端可以重新導向至其網路的本地 web 服務。 
  
關於 Windows 2016 DNS 原則的詳細資訊，請參閱[使用 DNS 原則進行 Geo-Location 的流量管理與主要伺服器](/windows-server/networking/dns/deploy/primary-geo-location)。
  
以下是一家公司設定的範例，其中包含使用 Windows 2016 DNS 原則進行 Geo-Location 的流量管理的多個網站。
  
旁路服務的名稱是 "hybridvoice.adatum.biz"。
  
阿姆斯特丹中的網站有四個 Cloud Connector 裝置，已使用下列轉送伺服器 IP 位址進行部署：
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
西雅圖的網站有三個雲端連接器裝置，已使用下列轉送伺服器 IP 位址進行部署：
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
使用以 Geo-Location 為基礎的流量管理，DNS 伺服器的設定如下：
  
1. 為阿姆斯特丹和西雅圖子網建立 DNS 用戶端子網。
    
2. 為阿姆斯特丹和西雅圖建立 adatum.biz 的 DNS 區域範圍。
    
3. 在每個 DNS 區域範圍中建立 DNS 記錄。
    
    阿姆斯特丹
    
   - 輸入 A;
    
   - Name： adatum.biz DNS 區域中的 hybridvoice
    
   - 目標：192.168.1.45
    
     建立其他轉送伺服器的其他記錄
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     西雅圖
    
   - 輸入
    
   - 名稱： hybridvoice in adatum.biz DNS 區域
    
   - 目標：10.10.1。8
    
     建立其他轉送伺服器的其他記錄
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 建立將用戶端子網上連至適當區域範圍的 DNS 原則，以確保所需的 DNS 解析。
    
此時，從阿姆斯特丹子網進行 DNS 查詢的用戶端將會傳回192.168.1.45、192.168.1.46、192.168.1.47 和192.168.1.48 位址，而建立相同查詢表單西雅圖的用戶端將會傳回10.10.1.8、10.10.1.9 和10.10.1.10。

> [!NOTE]
> 如果 CCE 裝置似乎沒有取得更新的設定，請查看裝置是否可以透過遠端 PowerShell 聯繫租使用者。 您可以使用 [遠端 PowerShell] 以 Get-CsHybridPSTNAppliance 檢查裝置狀態，或使用 CCE 主機上 PowerShell 來檢查 CcApplianceStatus 的狀態。

  
## <a name="see-also"></a>另請參閱
<a name="Example"> </a>

[規劃 Cloud Connector Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)