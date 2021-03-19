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
description: 瞭解如何設定 SBC 並連結至電話系統直接路由。
ms.openlocfilehash: 72075e7a7aed0196ac883d5f81069f2517c9fd9c
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875063"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>將會話邊界控制器 (SBC) 直接路由

本文將說明如何設定會話邊界控制器 (SBC) 並連接到電話系統直接路由。  這是設定直接路由的下列步驟的第 1 個步驟：

- **步驟 1.使用電話系統連接 SBC 並驗證** (本文) 
- 步驟 2. [啟用使用者進行直接路由](direct-routing-enable-users.md)
- 步驟 3. [設定通話路由](direct-routing-voice-routing.md)
- 步驟 4. [將數位轉換成替代格式](direct-routing-translate-numbers.md)

若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。

您可以使用 Microsoft [Teams 系統管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 來設定 SBC 並連結至直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側流覽中，前往 **[語音**  >  **直接路由**，然後按一下 **[SBC> 定位** 點。
2. 按一下 [新增 **]**。
3. 輸入 SBC 的 FQDN。 <br><br>請確定 FQDN 的功能變數名稱部分符合在租使用者中註冊的網域，並請記住 `*.onmicrosoft.com` ，SBC FQDN 功能變數名稱不支援該功能變數名稱。 例如，如果您有兩個功能變數名稱和 `contoso.com` `contoso.onmicrosoft.com` ，請使用 `sbc.contoso.com` 做為 SBC 名稱。 如果使用子域，請確定此子域也已在租使用者中註冊。 例如，如果您想要使用 `sbc.service.contoso.com` ，則 `service.contoso.com` 必須註冊。
4. 根據貴組織的需求，設定 SBC 的下列設定。 有關這些設定的詳細資訊，請參閱 [SBC 設定](#sbc-settings)。

    ![Microsoft Teams 系統管理中心新增 SBC 頁面的螢幕擷取畫面](media/direct-routing-add-sbc.png)

5. 完成後，按一下 [儲存]。

## <a name="using-powershell"></a>使用 PowerShell

若要將您的 SBC 連接到直接路由，您必須：

1. [使用 PowerShell 連線至商務用 Skype Online。](#connect-to-skype-for-business-online-by-using-powershell)
2. [將 SBC 連接到租使用者](#connect-the-sbc-to-the-tenant)。
3. [驗證 SBC 連接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 連線到商務用 Skype Online

您可以使用連接到租使用者的 PowerShell 會話，將 SBC 配對至直接路由介面。 若要開啟 PowerShell 會話，請遵循為 [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)設定電腦中概述的步驟。
 
建立遠端 PowerShell 會話之後，請確認您能看到管理 SBC 的命令。 若要驗證命令，請在 PowerShell 會話中輸入或複製並貼上下列命令，然後按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

命令會返回此處顯示的四個函數，讓您管理 SBC。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>將 SBC 連接到租使用者

使用 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 將 SBC 連接到租使用者。 在 PowerShell 會話中，輸入下列專案，然後按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 建議您使用 SBC 檔中的資訊，在 SBC 中設定通話上限。 如果 SBC 處於容量層級，則此限制會觸發通知。
  > 2. 只有當 SBC 的 FQDN 網域部分符合您租使用者中註冊的其中一個網域時，才能連接 SBC，但 \* .onmicrosoft.com。 SBC \* FQDN 名稱不支援使用 .onmicrosoft.com 功能變數名稱。 例如，如果您有兩個功能變數名稱 **，contoso**.com 和 **contoso**.onmicrosoft.com，您可以使用 sbc.contoso.com 名稱作為 SBC 名稱。 如果您嘗試使用 sbc.contoso.abc 等名稱來連接 SBC，系統不會讓您使用，因為網域並非此租使用者所擁有。<br/>
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
> 此範例只顯示最小所需的參數。 在連接過程中，您可以使用 [New-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 設定其他參數。 若要深入瞭解，請參閱 [SBC 設定](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>驗證 SBC 連接

若要驗證連接：

- [檢查 SBC 是否位於配對 SBC 清單中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [驗證 SIP 選項](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>檢查 SBC 是否位於配對 SBC 清單中

連接 SBC 之後，請使用 [Get-CsOnlinePSTNGateway Cmdlet](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) 來驗證 SBC 是否存在於配對 SBC 清單中。 在遠端 PowerShell 會話中輸入下列專案，然後按 Enter：

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配對閘道應該會出現在清單中，如下列範例所示， **且 Enabled** 參數應顯示 **值 True**。

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

若要使用外發 SIP 選項驗證配對，請使用 SBC 管理介面並確認 SBC 收到 200 個確定回應給待發的 OPTIONS 訊息。

當直接路由看到傳入的 OPTIONS 時，它會開始將外寄 SIP 選項郵件傳送至內送選項訊息中 ，在連絡人標題欄位中所配置的 SBC FQDN。 

若要使用內送 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的 OPTIONS 訊息，並且傳送的回應代碼為 200 確定。

## <a name="sbc-settings"></a>SBC 設定

下表列出您可以在 Microsoft Teams 系統管理中心使用 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 為 SBC 設定的選項。

|必填？|Microsoft Teams 系統管理中心設定|PowerShell 參數|說明|預設|可能的值|類型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**新增 SBC 的 FQDN**|Fqdn |無|FQDN 名稱，限制 63 個字元|字串，請參閱[Active Directory](https://support.microsoft.com/help/909264)電腦、網域、網站和 OUs 中命名慣例中允許和不允許的字元清單|
|否|**啟用**|啟用|用於開啟 SBC 進行外發通話。 您可以在更新 SBC 或維護期間，使用此功能暫時從服務移除 SBC。 |假|真<br/>假|Boolean|
|是|**SIP 訊號埠**|SipSignalingPort |這是使用傳輸層和 TLS 通訊協定與直接路由通訊 (埠) 埠。|無|任何埠|0 到 65535 |
|否|**傳送 SIP 選項**|SendSIPOptions |定義 SBC 是否要傳送 SIP 選項訊息。 我們強烈建議您開啟此設定。 關閉此設定時，SBC 會排除在監控和警示系統之外。|真|真<br/>假|Boolean|
|否|**轉往通話記錄**|ForwardCallHistory |指出通話記錄資訊是否透過主幹轉轉。 當您開啟此功能時，Microsoft 365 或 Office 365 Proxy 會傳送歷程記錄資訊和引用標頭。 |假|真<br/>假|Boolean|
|否|**將 P-確認身分識別轉 (PAI) 頁眉**|ForwardPAI|指出 PAI 標頭是否與通話一起轉轉。 PAI 標頭可用於驗證來電者的身分識別。 如果此設定為啟用，也會送出 Privacy：ID 標頭。|假|真<br/>假|Boolean|
|否|**同時通話容量**|MaxConcurrentSessions |當您設定值時，當同時會話數目為 90% 或高於此值時，通知系統會通知您。 如果您沒有設定值，系統不會產生通知。 不過，監控系統會每 24 小時報告一次並行會話數目。 |空|空<br/>1 到 100，000 ||
|否|**容錯移轉回應代碼**|容錯移轉ResponseCodes<br>|如果 Direct Routing 收到回應外發邀請的任何 4xx 或 6xx SIP 錯誤碼，則通話預設會視為已完成。 外撥是指從 Teams 用戶端撥打到 PSTN 的流量流量：Teams 用戶端 -> 直接路由 -> SBC ->電話網絡) 。 當您指定容錯移轉回應程式碼時，當 SBC 因為網路或其他問題而無法進行通話時，當您收到指定的代碼時) 如果使用者的語音路由策略中存在另一個 SBC (，則強制直接路由嘗試另一個 SBC。 若要深入瞭解，請參閱從會話邊界控制器或 SBC (接收[的特定 SIP) 。](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|否|**容錯移轉時間 (秒)**|FailoverTime秒 |當您設定值時，閘道在您設定時間內未接聽的外發通話會路由到下一個可用的主幹。 如果沒有額外的主幹，系統會自動中斷通話。 預設值為 10 秒。 在網路和閘道回應緩慢的組織中，這可能會導致不必要地中斷通話。|10|數量|Int|
|否|**媒體流量的偏好國家/地區**|MediaRelayRoutingLocationOverride |用於手動設定您偏好的媒體流量國家/地區。 建議您只在通話記錄清楚指出媒體路徑資料中心的預設指派不使用最接近 SBC 資料中心的路徑時，才設定此設定。 根據預設，直接路由會根據 SBC 的公用 IP 位址指派資料中心，並一直選取最接近 SBC 資料中心的路徑。 不過，在某些情況下，預設路徑可能並非最佳路徑。 此參數可讓您手動設定媒體流量的偏好區域。 |無|ISO 格式的國家/地區代碼||
|否|**SBC 支援 PIDF/LO 撥打緊急電話**|PidfloSupported|指定 SBC 是否支援目前狀態資訊資料格式位置物件 (PIDF/LO) 緊急通話。||||
|否| - |MediaBypass|此設定會指出 SBC 是否支援媒體旁路，以及您是否要使用此 SBC。 |無|真<br/>假|Boolean|

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)
