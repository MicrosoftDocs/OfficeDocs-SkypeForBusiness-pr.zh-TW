---
title: 商務用 Skype Server 視訊的螢幕畫面分享
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: '商務用 Skype Server 以影片為基礎的螢幕共用 (VbSS 的規劃和設定資訊) '
ms.openlocfilehash: 0eb381504e797879d9e4235d7ae9cce69f1a468c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396425"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>商務用 Skype Server 視訊的螢幕畫面分享 
 
KB3061064 中的2015商務 Skype 用影片畫面 (VbSS) 現在可供下載：[商務用 Skype Server 2015 累計更新](https://www.microsoft.com/download/details.aspx?id=47690)。 VbSS 包含商務用 Skype Server 2019。
  
以影片為基礎的螢幕共用或 VbSS，會成長至 Lync 螢幕共用。 VbSS 與傳統畫面共用之間的差異，必須與所用的基礎通訊協定及 excel 的定義相同。 螢幕共用使用遠端桌面通訊協定 (RDP) ，它非常適合在人員的電腦之間建立數千個1對1會話。 更新的技術 VbSS 會使用使用者資料包通訊協定 (UDP) 。
  
商務用 Skype Server 想要提升人員的1對1，及其一對多 (多方) 交談和會議體驗。 VbSS 會利用以 UDP 為基礎通訊協定) 的媒體平臺 (，其目的是為了縮短影片的開始時間，在您所觀賞的情況下，您所看到的內容的觀賞品質 (尤其是在您所觀賞的情況下，您所看到的內容的) 速度和整體可靠性。
  
改善螢幕共用的目的之一是，在 VbSS 和 RDP 之間的轉變會盡可能順利進行。 因為 VbSS 是在商務用 Skype Server 的螢幕共用中所使用的基礎技術更新，所以除非您在網路流量中查看 SIP 詳細資料，或是共用快移或立體的內容，否則可能很難偵測出您要使用的技術。 例如，如果您的工作場所有許多舊版用戶端，則 RDP 仍可作為您的會議和交談的安全。 商務用 Skype Server 會使用內部邏輯來決定兩種方法中的哪一種 (VbSS 或傳統的螢幕共用) 會在用戶端連線時套用。 當情況呼叫它時，RDP 可以和會取代 VbSS，因此您的觀賞體驗不會中斷。
  
## <a name="planning"></a>規劃

### <a name="vbss-pros-and-cons"></a>VbSS 優點和缺點

切換至 VbSS 旨在進行三項重要改進：
  
1. 將螢幕共用 (高達5% 的 ) 比獨立于 RDP 更可靠。

2. 將會話設定和影片體驗與 RDP 個別相較于 RDP (安裝程式的速度提高了一半，6:1 但每秒幀數的) 都會提高。

3. 即使在共用高運動內容時（例如立體圖形），在低頻寬條件下，它的運作方式要好于 RDP。
    
請記住，這些數位取決於您網路的健康情況和適當效能調整，如果您的用戶端在行動裝置上，可能會包含您自己的網路。
  
您也應該知道，共用內容的一些逼真度/crispness 已針對可靠性、速度和效能而提高效益。 在大多數情況下，使用者不會看到這種情況。
  
### <a name="ports-and-protocols"></a>連接埠和通訊協定

**必要的伺服器埠**

|**伺服器角色**|**服務名稱**|**埠或埠範圍**|**Protocol** (通訊協定)|**附註**|
|:-----|:-----|:-----|:-----|:-----|
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |5065  <br/> |TCP  <br/> |用於應用程式共用的傳入 SIP 聆聽要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用於應用程式共用的媒體埠範圍。  <br/> |
   
**必要的用戶端埠**

|**元件**|**連接埠範圍**|**Protocol** (通訊協定)|**附註**|
|:-----|:-----|:-----|:-----|
|用戶端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |應用程式共用。  <br/> |
   
如果已啟用下列媒體埠的 QoS，而且 VbSS 也已啟用，則在包含桌面共用的會議期間，您的畫面共用流量會使用以粗體顯示的影片埠設定。 
  
> [!IMPORTANT]
> 這些設定為特殊案例，在同時執行這兩種功能時，必須使用這些設定。 這會覆寫 [QoS 檔](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)中的其他建議設定。 針對應用程式共用，除了定義這些埠值之外，還需要在 QoS GPO 中指定 ASMCUSVC.exe。 
  
**Application Server QoS/VbSS 必要設定**

|**屬性**|**埠值**|**Protocol** (通訊協定)|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>容量規劃

每個執行商務用 Skype Server 2015 累積更新 2 (CU2) 或更新版本的每個前端伺服器都支援最多375參與者使用 RDP (，但只有250每個會議) 。 當引進和使用 VbSS 時，此容量不會變更 CU3 後的容量。
  
也就是說，我們已在實驗室中完成效能和應力測試，而且也應視您的部署 (考慮，視) 的使用方式而定，也應考慮下列度量。
  
假設：
  
- 您正在部署中使用商務用 Skype Server 2015 CU2 或更新版本。
    
- 商務用 Skype Server 環境中的所有使用者都具有高於1920x1080 的螢幕解析度。
    
在上面所述的完整容量 (（如以上所述）為每個前端伺服器的375螢幕共用參與者總數，雖然每個會議只有 250) ，但您的前端伺服器可能會使用大約 1 Gb 網路卡的89%。 這是因為商務用 Skype Server CU2 中的現有螢幕共用技術會 (RDP) 以原生解析度為簡報者的電腦傳送螢幕上的內容。 因此，在中所述的螢幕解析度越高，您可能會遇到與商務用 Skype Server 2015 CU2 的畫面共用的網路瓶頸。
  
為了緩解這種情況，下列一或多個選項可能很有用：
  
- 將前端伺服器從 1 Gb 的網卡升級為 10 Gb 的乙太網卡。

- 增加前端伺服器數目，以進行負載平衡流量。

- 將 cap 置於任一通道所使用的最大頻寬上，以限制 VbSS 和 RDP 所用的頻寬 (位元速率) 。
    
此表格中的數位會受到個別網路及共用內容的影響。 請測試以建立網路或網路的基準。
  
|**1080p 內容**|**RDP 平均**|**RDP 峰值**|**平均 VbSS**|**VbSS 峰**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|影片  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒體流量的網路頻寬需求

VbSS 頻寬如下：
  
|**視訊轉碼器**|**解析度和外觀比例**|**最大影片負載位元速率 (Kbps)**|**最小影片負載位元速率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H-p  <br/> |1920x1080 (16:9)   <br/>  (的方位比例取決於共用者的監視器解析度，而且不一定會是 16:9)   <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>用戶端和伺服器支援

以影片為基礎的螢幕共用需要商務用 Skype Server 2015 CU3 或更新版本，以及商務用 Skype 和[會議支援](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的行動[用戶端功能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中所列支援用戶端的目前版本。 
  
在某些情況下，螢幕共用會轉換為 RDP，如下所示：
  
- 如果您的帳戶主控于 ASMCU 未符合支援 VbSS 的最低組建的環境中。
- 如果使用舊版本商務用 Skype 用戶端的人員加入您的會話，例如，使用任何 Windows 用戶端版本低於16.0.6330.1000、商務用 Skype 會議室系統裝置或商務用 Skype 行動應用程式的人員。 
- 使用者從商務用 Skype Web 應用程式共用。
- 如果有人在 Mac 上使用商務用 Skype，而非使用商務用 Skype 線上或商務用 Skype Server 2015 與2018累積更新 (或更新版本) 。
- 如果有人啟動任何程式/Windows 共用。
- 如果有人開始記錄會話。
- 如果有人在會話期間呼叫遠端螢幕控制。 
- 超過250位參與者的會議 (目前不支援 VbSS) 。

請注意，一旦會話轉換至 RDP，它就不會轉換回 VbSS。 同樣地，從 VbSS 的過渡是指無縫的，而且在大多數情況下，使用願望也不會偵測到。
    
> [!NOTE]
> 在商務用 Skype 螢幕共用時，不支援封鎖或嘗試封鎖，從 VbSS 轉換為 RDP。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>啟用、停用及設定 VbSS

最棒的是，當您已安裝商務用 Skype Server 2015 累計更新 3 (CU3) 或更新版本，所有使用者預設都會啟用1對1和多方 VbSS。 如果您有理由不讓所有使用者啟用此功能，這可能會造成問題。 在此情況下，您可以使用這些步驟來停用使用者 (啟用使用者的步驟將遵循) ：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何使用 VbSS 來停用使用者

- 您可以在商務用 Skype 管理主控台中執行此指令程式，以將不允許 VbSS 的使用者原則指派給不允許 VbSS 的任何使用者， (以 PolicyName 的原則取代 [) ]：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 您也可以更新全域會議原則，此原則會影響所有未指派原則的使用者：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    如需此命令的詳細資訊，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果您需要完全關閉 VbSS，您可以執行下列命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    如需此命令的詳細資訊，請參閱 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何讓使用者能夠使用 VbSS

- 您可以在商務用 Skype 管理主控台中執行此指令程式，以指定特定的使用者原則，以允許任何需要使用 VbSS 的使用者， (以您為 PolicyName 執行這項原則的 VbSS 執行：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 您也可以更新全域會議原則，此原則會影響所有未指派原則的使用者：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    如需此命令的詳細資訊，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果您需要在關閉 VbSS 後再開啟它 () 預設為開啟狀態，您可以執行下列命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    如需此命令的詳細資訊，請參閱 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 2015 累計更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[商務用 Skype Server 2015 提供以影片為基礎的螢幕共用 (VBSS) ](https://support.microsoft.com/kb/3170163)