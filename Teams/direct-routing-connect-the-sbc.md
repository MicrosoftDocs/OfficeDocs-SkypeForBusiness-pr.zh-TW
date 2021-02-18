---
title: 將會話邊界控制器 (SBC) 直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定並連接 SBC 到電話系統直接路由。
ms.openlocfilehash: 4240eb4000e813df51b2678ad2e9c37f6bc0c2ac
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278703"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>將會話邊界控制器 (SBC) 直接路由

本文說明如何在 SBC (設定會話邊界控制器) 並連接到電話系統直接路由。  這是設定直接路由之下列步驟的步驟 1：

- **步驟 1。使用電話系統連接 SBC 並驗證 (** 本文) 
- 步驟 2。 [啟用使用者進行直接路由](direct-routing-enable-users.md)
- 步驟 3。 [設定通話路由](direct-routing-voice-routing.md)
- 步驟 4. [將數位轉換成替代格式](direct-routing-translate-numbers.md)

有關設定直接路由所需之所有步驟的資訊，請參閱設定 [直接路由](direct-routing-configure.md)。

您可以使用 Microsoft [Teams 系統管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 來設定 SBC 並連結至直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側流覽中，前往 **[語音**  >  **直接路由**，然後按一下 **SBC 定位** 點。
2. 按一下 [新增 **]**。
3. 輸入 SBC 的 FQDN。 <br><br>請確定 FQDN 的功能變數名稱部分符合已在租使用者中註冊的網域，並請記住 `*.onmicrosoft.com` ，SBC FQDN 功能變數名稱不支援該功能變數名稱。 例如，如果您有兩個功能變數名稱和 `contoso.com` `contoso.onmicrosoft.com` ，請使用 `sbc.contoso.com` 做為 SBC 名稱。 如果使用子域，請確定已在租使用者中註冊此子域。 例如，如果您想要使用， `sbc.service.contoso.com` 則 `service.contoso.com` 必須註冊。
4. 根據貴組織的需求，設定 SBC 的下列設定。 有關這些設定的詳細資訊，請參閱 [SBC 設定](#sbc-settings)。

    ![Microsoft Teams 系統管理中心中新增 SBC 頁面的螢幕擷取畫面](media/direct-routing-add-sbc.png)

5. 完成後，按一下 [儲存]。

## <a name="using-powershell"></a>使用 PowerShell

若要將您的 SBC 連接到直接路由，您必須：

1. [使用 PowerShell 連線到商務用 Skype Online。](#connect-to-skype-for-business-online-by-using-powershell)
2. [將 SBC 連接到租使用者](#connect-the-sbc-to-the-tenant)。
3. [確認 SBC 連接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 連線到商務用 Skype Online

您可以使用連接至租使用者的 PowerShell 會話，將 SBC 與直接路由介面配對。 若要開啟 PowerShell 會話，請遵循設定 [電腦以用於 Windows PowerShell 中概述的步驟](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
 
建立遠端 PowerShell 會話之後，請確認您能看到管理 SBC 的命令。 若要驗證命令，請在 PowerShell 會話中輸入或複製並貼上下列命令，然後按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

此命令會返回此處顯示的四個函數，讓您管理 SBC。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>將 SBC 連接到租使用者

使用 [New-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 將 SBC 連接到租使用者。 在 PowerShell 會話中，輸入下列專案，然後按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 我們建議您使用 SBC 檔中的資訊設定 SBC 通話上限。 如果 SBC 在容量層級，則此限制會觸發通知。
  > 2. 只有當 SBC 的網域部分符合您租使用者中註冊的其中一個網域時，才能連接 SBC，但 \* .onmicrosoft.com。 SBC \* FQDN 名稱不支援使用 .onmicrosoft.com 功能變數名稱。 例如，如果您有兩個功能變數名稱 **，contoso**.com 和 **contoso**.onmicrosoft.com，您可以使用 sbc.contoso.com 作為 SBC 名稱。 如果您嘗試將 SBC 與 sbc.contoso.abc 等名稱連接，系統不會讓您使用，因為網域並非此租使用者所擁有。<br/>
  > 除了在租使用者中註冊的網域之外，擁有該網域的使用者以及已指派的 E3 或 E5 授權也非常重要。 如果沒有，您會收到下列錯誤：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

以下是範例：

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

這會返回：

<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>

> [!NOTE]
> 此範例只會顯示所需參數的最小值。 在連接過程中，您可以使用 [New-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 設定其他參數。 若要深入瞭解，請參閱 [SBC 設定](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>驗證 SBC 連接

若要驗證連接：

- [檢查 SBC 是否在配對 SBC 清單中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [驗證 SIP 選項](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>檢查 SBC 是否在配對 SBC 清單中

連接 SBC 之後，請使用 [Get-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) 來驗證 SBC 是否存在於配對 SBC 清單中。 在遠端 PowerShell 會話中輸入下列專案，然後按 Enter：

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配對閘道應該會顯示在清單中，如下列範例所示，且 **Enabled** 參數應顯示 **True 的值**。

這會返回：

<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA
ExcludedCodecs        :  
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
</pre>

#### <a name="validate-sip-options"></a>驗證 SIP 選項

若要使用外發 SIP 選項驗證配對，請使用 SBC 管理介面並確認 SBC 會接收 200 個待發選項訊息的確定回應。

當直接路由看到傳入的 OPTIONS 時，它會開始將待發 SIP 選項訊息傳送至內送 OPTIONS 訊息中 ，在連絡人標題欄位中所配置的 SBC FQDN。 

若要使用內送 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的 OPTIONS 訊息，而且它傳送的回應程式碼是 200 確定。

## <a name="sbc-settings"></a>SBC 設定

下表列出您可以在 Microsoft Teams 系統管理中心以及使用 [New-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 為 SBC 設定的選項。

|必填？|Microsoft Teams 系統管理中心設定|PowerShell 參數|說明|預設|可能的值|類型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**新增 SBC 的 FQDN**|Fqdn |無|FQDN 名稱，限制 63 個字元|字串，請參閱適用于電腦、網域、網站和[OUs 之 Active Directory](https://support.microsoft.com/help/909264)中命名慣例的允許和不允許字元清單|
|否|**啟用**|啟用|用於開啟 SBC 進行外線通話。 您可以在更新 SBC 或維護期間，使用此功能暫時從服務移除 SBC。 |假|真<br/>假|Boolean|
|是|**SIP 訊號埠**|SipSignalingPort |這是使用傳輸層或 TLS (通訊協定與直接路由通訊 (埠) 埠。|無|任何埠|0 到 65535 |
|否|**傳送 SIP 選項**|SendSIPOptions |定義 SBC 是否會傳送 SIP 選項訊息。 強烈建議您開啟此設定。 關閉此設定時，監控和警示系統會排除 SBC。|真|真<br/>假|Boolean|
|否|**呼叫前轉記錄**|ForwardCallHistory |指出通話記錄資訊是否透過中繼線轉出。 當您開啟此功能時，Microsoft 365 或 Office 365 Proxy 會傳送歷程記錄資訊和參考標頭。 |假|真<br/>假|Boolean|
|否|**將 P-就地識別轉 (PAI) 頁眉**|ForwardPAI|表示 PAI 標頭是否隨著通話一起轉場。 PAI 標頭可用於驗證來電者的身分識別。 如果此設定為啟用，也會一併送出隱私權：ID 標頭。|假|真<br/>假|Boolean|
|否|**同時通話容量**|MaxConcurrentSessions |當您設定值時，當並行會話數目超過或超過此值時，警示系統就會通知您。 如果您沒有設定值，系統不會產生通知。 不過，監視系統會每 24 小時報告同時進行一次會話的數量。 |空|空<br/>1 到 100，000 ||
|否|**容錯移轉回應代碼**|FailoverResponseCodes<br>|如果直接路由收到回應外發邀請的任何 4xx 或 6xx SIP 錯誤碼，則通話預設會視為已完成。 撥出是指從 Teams 用戶端撥打到 PSTN 的流量：Teams 用戶端 -> 直接路由 -> SBC -> 電話網絡) 。 當您指定容錯移轉回應程式碼時，如果使用者的語音路由策略中有另一個 SBC 存在，則強制直接路由嘗試另一個 SBC (如果 SBC 因網路或其他問題而接收指定的代碼時) 則當 SBC 無法撥打時。 若要深入瞭解，請參閱從會話 Border Controller ([SBC ](direct-routing-trunk-failover-on-outbound-call.md)) 。|408, 503, 504||Int|
|否|**容錯移轉時間 (秒)**|FailoverTime秒 |當您設定值時，閘道未在您設定的時間內接聽的外線通話會路由至下一個可用的中繼線。 如果沒有額外的樹線，通話會自動中斷。 預設值為 10 秒。 在網路緩慢和閘道回應緩慢的組織中，這可能會導致不必要的通話中斷。|10|數量|Int|
|否|**媒體流量的偏好國家/地區**|MediaRelayRoutingLocationOverride |用於手動設定媒體流量的偏好國家/地區。 建議您只有在通話記錄清楚指出媒體路徑的資料中心預設指派不是使用最接近 SBC 資料中心的路徑時，才設定此設定。 根據預設，直接路由會根據 SBC 的公用 IP 位址指派資料中心，並一直選取最接近 SBC 資料中心的路徑。 不過，在某些情況下，預設路徑可能並非最佳路徑。 此參數可讓您手動設定媒體流量的偏好區域。 |無|ISO 格式的國家/地區代碼||
|否|**SBC 支援撥打緊急電話的 PIDF/LO**|PidfloSupported|指定 SBC 是否支援緊急電話的目前狀態資訊資料格式 (PIDF/LO) 位置物件。||||
|否|**在嘗試尋找使用者時撥打電話**|GenerateRingingWhileLocatingUser|設定是否播放音訊訊號給來電者，表示 Teams 正在建立通話。 此設定僅適用于非媒體旁路模式的直接路由。 有時候，從 PSTN 撥打到 Teams 用戶端的來電可能需要比預期更久的時間。 發生這種情況時，來電者可能聽不到任何聲音，Teams 用戶端不會響鈴，而且某些電信提供者可能會取消通話。 此設定可協助避免這些情況下會發生意外的靜音。|真|真<br/>假|Boolean|
|否| - |MediaBypass|此設定會指出 SBC 是否支援媒體旁路，以及您是否要在此 SBC 使用媒體。 |無|真<br/>假|Boolean|

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)
