---
title: 商務用 Skype Server 視訊的螢幕畫面分享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 商務用 Skype Server 規劃與影片畫面共用的配置資訊（VbSS）
ms.openlocfilehash: f0d474772b94389c1d69264be61b3bee2b46a385
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817043"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>商務用 Skype Server 視訊的螢幕畫面分享 
 
商務用 Skype Server 2015 中的影片畫面共用（VbSS）現已可供下載：[商務用 Skype server 2015 累計更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。 VbSS 隨附于商務用 Skype Server 2019。
  
以影片為基礎的畫面共用或 VbSS，會隨著 Lync 螢幕共用而增長。 VbSS 與傳統螢幕共用的差異，必須與所使用的基本協定以及其 excel 位於何處。 螢幕共用使用遠端桌面通訊協定（RDP），這相當於在人員電腦之間建立數以千計的1對1會話。 較新的技術（VbSS）會使用使用者資料包通訊協定（UDP）。
  
商務用 Skype Server 想要改善人員的1對1，以及其一對多（多方）交談和會議體驗。 VbSS 會使用媒體平臺（依賴 UDP 做為基礎通訊協定），目的是改善影片啟動時間、觀賞品質（尤其是您正在觀看的內容是快速的移動），以及整體的可靠性。
  
改善螢幕共用的其中一個原因，就是 VbSS 和 RDP 之間的轉換會盡可能順暢地進行。 由於 VbSS 是在商務用 Skype Server 的螢幕共用中所使用的基礎技術的更新，因此，除非您是在網路流量中查看 SIP 詳細資料，或是您要共用的內容，否則可能難以偵測到您正在使用的技術為快速移動或立體。 例如，如果您的工作場所有許多舊版用戶端，則在您的會議和交談中，RDP 仍可提供安全的故障。 商務用 Skype Server 在用戶端連線時，會使用內部邏輯來決定要套用哪兩種方法（VbSS 或傳統螢幕共用）。 在情況下，RDP 可以和將取代為 VbSS，因此您的流覽體驗不會中斷。
  
## <a name="planning"></a>規劃

### <a name="vbss-pros-and-cons"></a>VbSS 的優點與缺點

切換到 VbSS 旨在改善三項主要功能：
  
1. 進行螢幕共用（最多5%）與 RDP 單獨比較，以獲得更可靠的對比。

2. 讓會話設定和影片體驗與 RDP （半時間）更快速，且每秒的畫面改善6:1。

3. 在低頻寬情況下，即使是在共用高運動內容（例如3D 圖形）時，它的運作效果都比 RDP 要好得多。
    
請記住，這些數位依賴于健康情況和對您網路的適當效能調整，如果您的用戶端在行動裝置上，也可能會包含您自己的外部網路。
  
您也應該注意，您的共用內容的一些逼真度/crispness 已經過大量的可靠性、速度和效能。 在大多數情況下，使用者不會看到這種情況。
  
### <a name="ports-and-protocols"></a>連接埠和通訊協定

**所需的伺服器埠**

|**伺服器角色**|**服務名稱**|**埠或埠範圍**|**通訊協定**|**筆記**|
|:-----|:-----|:-----|:-----|:-----|
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |5065  <br/> |TCP-OUT  <br/> |用於應用程式共用的傳入 SIP 偵聽要求。  <br/> |
|前端伺服器  <br/> |商務用 Skype Server 應用程式共用服務  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用來共用應用程式的媒體埠範圍。  <br/> |
   
**所需的用戶端埠**

|**元件**|**埠範圍**|**通訊協定**|**筆記**|
|:-----|:-----|:-----|:-----|
|台  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |應用程式共用。  <br/> |
   
如果已啟用下列媒體埠的 QoS，且 VbSS 已啟用，則在包含桌面共用作為 MCU 的會議期間，就會使用下方以粗體顯示的視訊連接埠設定，以供螢幕共用流量使用。 
  
> [!IMPORTANT]
> 這些設定是一個特殊的情況，在同時執行這兩個功能時，必須使用這些確切的設定。 這會覆寫 [QoS][檔](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的其他建議設定。 針對應用程式共用，除了定義這些埠值之外，您還需要在 QoS GPO 中指定 ASMCUSVC。 
  
**應用程式伺服器 QoS/VbSS 必要的設定**

|**Property**|**埠值**|**通訊協定**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP-IN  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP-IN  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP-IN  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP-IN  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP-OUT  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP-OUT  <br/> |
   
### <a name="capacity-planning"></a>容量規劃

每個執行商務用 Skype Server 2015 累積更新2（CU2）或更新版本的前端伺服器，都支援最多375個參與者使用 RDP 進行畫面共用（不過每個會議僅有250）。 此容量不會變更 CU3，而是在推出 VbSS 時使用。
  
我們所說的是，我們已在實驗室中完成效能與壓力測試，而且應該考慮使用您自己的部署（視情況而定）。
  
假如
  
- 您在部署中使用商務用 Skype Server 2015 CU2 或更新版本。
    
- 商務用 Skype Server 環境中的所有使用者都有比1920x1080 高的螢幕解析度。
    
在完整容量（如上所述）是每個前端伺服器總的375螢幕共用參與者，但在每個會議中只有250，則您的前端伺服器可能會利用的是1十億位元網卡的 ~ 89%。 這是因為商務用 Skype Server CU2 （RDP）中現有的螢幕共用技術會以簡報者電腦的原生解析度來傳送螢幕內容。 如此一來，使用商務用 Skype Server 2015 CU2，您可能已遇到網路瓶頸，讓螢幕解析度更高。
  
若要緩解此情況，下列其中一或多個選項可能很有用：
  
- 將您的前端伺服器從1千兆網卡升級為 10 Gigabit 乙太網卡。

- 增加前端伺服器的數目，以進行負載平衡流量。

- 將 cap 放在任何一個通道所使用的最大頻寬，限制 VbSS 和 RDP 所使用的頻寬（位元速率）。
    
此表格中的數位會受到個別網路以及共用內容的影響。 請進行測試，為您的網路或網路建立比較基準。
  
|**1080p 內容**|**RDP 平均值**|**RDP 峰值**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|.PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|顯示器  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒體流量的網路頻寬需求

VbSS 頻寬為：
  
|**影片編碼解碼器**|**解析度和長寬比**|**最大視頻有效負載位元速率（Kbps）**|**最小視頻有效負載位元速率（Kbps）**|
|:-----|:-----|:-----|:-----|
|H-p  <br/> |1920x1080 （16:9）  <br/> （[長寬比] 視共用的監視器解析度而定，並不會永遠為16:9）  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>用戶端和伺服器支援

以影片為基礎的螢幕共用需要商務用 Skype Server 2015 CU3 或更新版本，以及適用于商務用 Skype 與[會議支援](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的行動[用戶端功能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中所列的支援用戶端目前版本。 
  
在某些情況下，螢幕共用會轉換為 RDP，如下所示：
  
- 如果您的帳戶是託管在 ASMCU 不符合支援 VbSS 之最小組建的環境中。
- 如果有人使用較舊版本的商務用 Skype 用戶端加入您的會話，例如任何使用低於16.0.6330.1000 的任何 Windows 用戶端版本、商務用 Skype 房間系統裝置或商務用 Skype 行動裝置 App。 
- 如果使用者是從商務用 Skype Web App 共用。
- 如果有人使用 Mac 版商務用 Skype，而不是託管于商務用 skype Online，或使用7月、2018累計更新（或更新版本）的商務用 skype Server 2015。
- 如果有人啟動任何程式/Windows 共用，
- 如果有人開始錄製會議。
- 如果有人在會話期間喚醒打電話給遠端螢幕控制。 
- 超過250個參與者的會議（目前不支援 VbSS）。

請注意，一旦會話轉換為 RDP，就不會轉換回 VbSS。 同樣地，從 VbSS 轉場是無縫的，而且在大多數情況下，都不容易偵測到您的願望。
    
> [!NOTE]
> 在商務用 Skype 畫面共用中，不支援封鎖或嘗試封鎖、從 VbSS 轉換為 RDP。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>啟用、停用和設定 VbSS

最重要的是，一旦您安裝商務用 Skype Server 2015 累計更新3（CU3）或更新版本之後，您的所有使用者預設都會啟用1到1和多方 VbSS。 如果您有理由讓所有使用者都無法使用此功能，這可能會給您帶來問題。 在這種情況下，您可以使用這些步驟來停用使用者（[啟用使用者] 步驟如下所示）：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何從 VbSS 停用使用者

- 您可以在商務用 Skype 管理主控台中執行此 Cmdlet 來指派不允許 VbSS 使用 VbSS 的使用者原則（將 [PolicyName] 取代為您所執行的原則）：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 您也可以更新全域會議原則，這將會影響所有沒有指派原則的使用者：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    如需此命令的詳細資訊，請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果您需要完全關閉 VbSS，您可以執行此命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    如需此命令的詳細資訊，請參閱[設定 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何讓使用者使用 VbSS

- 您可以在商務用 Skype 管理主控台中執行此 Cmdlet 來指派允許 VbSS 使用 VbSS 的特定使用者原則（將 [PolicyName] 取代為您所執行的原則）：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 您也可以更新全域會議原則，這將會影響所有沒有指派原則的使用者：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    如需此命令的詳細資訊，請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果您需要在關閉後再開啟 VbSS （預設為開啟），您可以執行這個命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    如需此命令的詳細資訊，請參閱[設定 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 2015 累計更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[商務用 Skype Server 2015 提供影片畫面共用（VBSS）](https://support.microsoft.com/en-us/kb/3170163)
