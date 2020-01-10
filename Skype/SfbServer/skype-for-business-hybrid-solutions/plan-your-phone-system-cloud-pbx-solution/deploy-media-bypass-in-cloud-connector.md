---
title: 在雲端連接器版本中部署媒體旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本部署媒體旁路的步驟。
ms.openlocfilehash: 63d8f9e289c38a50444bee2667c98543e09b875d
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003483"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>在雲端連接器版本中部署媒體旁路
 
請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本部署媒體旁路的步驟。 
  
「媒體旁路」可讓用戶端直接傳送媒體至公用交換式電話網絡（PSTN）的下一個躍點（閘道或會話邊界控制器（SBC）），並從媒體路徑中消除雲端連接器版本元件。 另請參閱[在雲端連接器版本中使用媒體旁路方案](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>啟用媒體旁路

若要啟用媒體旁路，您必須設定媒體旁路 web 服務的 DNS 名稱，並在租使用者配置中開啟 [媒體旁路]。 媒體旁路 web 服務會自動在每個中繼伺服器上進行部署。 租使用者管理員必須挑選混合式語音服務（網站）的名稱，且此名稱應該來自已註冊為混合式語音的 SIP 網域。 不論用戶端位置為何，所有雲端連接器裝置和所有 PSTN 網站上的服務名稱應該都是相同的。 Web 服務只能在網路內部使用。
  
租使用者管理員必須在內部生產 Active Directory 中設定 DNS A 記錄。 如果您有複雜的多網站環境，請參閱範例：在[複雜的多網站環境中，媒體略過網站的 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS 記錄應該只解析內部網路用戶端;它不應該解析外部網路用戶端。
  
在設定 DNS 之後，使用與商務用 Skype 系統管理員認證的遠端 PowerShell，連線到商務用 Skype Online。 如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
在 PowerShell 會話中，輸入下列命令以啟用媒體旁路：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

啟用媒體旁路的程式分為兩個步驟。 新的-CsNetworkMedia Cmdlet 不會立即儲存新的設定;它只會在記憶體中建立設定。 由此 Cmdlet 建立的物件必須儲存到變數，然後指派給網路設定的 MediaBypassSettings 屬性。 如需詳細資訊，請參閱[範例：在複雜的多網站環境中，媒體略過網站的 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。
  
內部部署與線上元件之間的複製可能需要長達24小時，因此 Microsoft 建議您在啟用使用者之前先執行必要的命令。
  
## <a name="confirm-media-bypass-settings"></a>確認媒體旁路設定

您可以檢查媒體旁路設定，如下所示。 
  
若要在您的租使用者池中檢查線上複製，請在遠端 PowerShell 中執行下列命令：
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

若要檢查內部部署的複製，請連線到雲端連接器轉送伺服器，在 PowerShell 中執行下列命令，並確認 Enabled = True 和 AlwaysBypass = True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

若要檢查用戶端設定，請登出商務用 Skype 用戶端，重新登入，然後確認用戶端已收到服務 URL，如下所示：
  
1. 開啟%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。 
    
2. 搜尋 hybridconfigserviceinternalurl 並確認 URL 與您所定義的 URL 相符。
    
## <a name="change-media-bypass-parameters"></a>變更媒體旁路參數

租使用者管理員可以執行下列 Cmdlet 來變更 web 服務的 DNS 名稱：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 用戶端需要登出並登入以取得新的服務名稱並辨識變更。 
  
## <a name="temporarily-disable-media-bypass"></a>暫時停用媒體旁路

這個案例對於疑難排解或維護可能很有用。 若要停用服務，請執行下列 Cmdlet：
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

變更之後，將變更複製到所有雲端連接器可能需要一些時間。 若要檢查複製狀態，請在雲端連接器中繼伺服器上的 PowerShell 中執行下列 Cmdlet： 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

複製變更之後，中繼伺服器上的 web 服務就會開始拒絕媒體旁路服務的用戶端要求。
  
## <a name="disable-media-bypass-permanently"></a>永久停用媒體旁路

若要永久停用媒體旁路，租使用者管理員必須執行下列命令： 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

系統管理員也必須從內部 DNS 伺服器移除 [媒體旁路] 的網址。 進行變更之後，將變更複製到所有雲端連接器裝置可能需要一些時間。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>範例：在複雜的多網站環境中，媒體略過網站的 DNS 記錄
<a name="Example"> </a>

用戶端會從內部 DNS 伺服器接收媒體旁路 web 服務的網址。 在所有雲端連接器裝置和雲端連接器 PSTN 網站上，web 服務的名稱都是相同的。 在複雜的多網站環境中，我們建議您針對地理位置的流量管理使用 Windows 2016 DNS 原則，讓用戶端可以重新導向到網路的本機服務。 
  
如需有關 Windows 2016 DNS 原則的詳細資訊，請參閱[在主要伺服器上使用地理位置的流量管理的 DNS 原則](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)。
  
下列是具有多個網站之公司的配置範例，這些網站使用針對地理位置的流量管理進行的 Windows 2016 DNS 原則。
  
略過服務的名稱為「hybridvoice.adatum.biz」。
  
[阿姆斯特丹] 中的網站有四個雲端連接器裝置，且已使用下列中繼伺服器 IP 位址進行部署：
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
西雅圖中的網站有三個部署了下列中繼伺服器 IP 位址的雲端連接器裝置：
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
使用以地理位置為基礎的流量管理，DNS 伺服器的設定方式如下：
  
1. 為阿姆斯特丹和西雅圖子網建立 DNS 用戶端子網。
    
2. 為阿姆斯特丹和西雅圖的 adatum.biz 建立 DNS 區域範圍。
    
3. 在每個 DNS 區域範圍中建立 DNS 記錄。
    
    阿姆斯特丹
    
   - 鍵入 A;
    
   - Adatum.biz DNS 區域中的名稱： hybridvoice
    
   - 目標：192.168.1.45
    
     建立其他中繼伺服器的其他記錄
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     西雅圖
    
   - 輸入
    
   - Name： hybridvoice adatum.biz DNS 區域
    
   - 目標：10.10.1。8
    
     建立其他中繼伺服器的其他記錄
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 建立將用戶端子網連接至適當區域範圍的 DNS 原則，以確保所需的 DNS 解析度。
    
此時，從阿姆斯特丹子網上進行 DNS 查詢的用戶端將會傳回192.168.1.45、192.168.1.46、192.168.1.47 和192.168.1.48 位址，而用戶端建立相同的查詢表單時，會傳回10.10.1.8，10.10.1.9 和10.10.1.10。

> [!NOTE]
> 如果 CCE 裝置看起來沒有取得更新的設定，請檢查裝置能否透過遠端 PowerShell 與租使用者取得聯繫。 您可以在 CCE 主機上使用 [遠端 PowerShell] 來檢查裝置狀態，以取得 CsHybridPSTNAppliance 或使用 PowerShell，以 CcApplianceStatus 來檢查狀態。

  
## <a name="see-also"></a>另請參閱
<a name="Example"> </a>

[規劃 Cloud Connector Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)
