---
title: 將您的會話邊界控制器（SBC）連線至直接路由
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
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157943"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>將您的會話邊界控制器（SBC）連線至直接路由 

本文說明如何將您的會話邊界控制器（SBC）連線至手機系統直接路由。  以下是設定直接路由的步驟1：

- **步驟1。將您的 SBC 與電話系統連接並驗證**連線（本文）
- 步驟2。 [允許使用者直接傳送](direct-routing-enable-users.md)
- 步驟3。 [設定通話路由](direct-routing-voice-routing.md)
- 步驟4。 [將數位轉換成替換格式](direct-routing-translate-numbers.md) 

如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定[直接路由](direct-routing-configure.md)。

若要將您的 SBC 連線至直接路由，您必須： 

1. 使用 PowerShell**連線到商務用 Skype Online**系統管理中心。            
2. 將 SBC 連接至租使用者。
3. 驗證連線。 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 連線到商務用 Skype Online 

您可以使用連接至租使用者的 PowerShell 會話，將 SBC 與直接路由介面配對。 若要開啟 PowerShell 會話，請依照[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中所述的步驟進行。 
 
建立遠端 PowerShell 會話之後，請確認您可以看到管理 SBC 的命令。 若要驗證命令，請在 PowerShell 會話中輸入或複製並貼上下列命令，然後按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

這個命令會傳回這裡顯示的四個函數，讓您管理 SBC。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>將 SBC 連接至租使用者 

若要將 SBC 連接至租使用者，請在 PowerShell 會話中輸入下列內容，然後按 Enter 鍵： 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft 建議您在 SBC 中設定最大通話限制，使用可在 SBC 檔中找到的資訊。 如果 SBC 是容量等級，則限制會觸發通知。
  > 2. 您只能將 SBC 的網域部分與您在租使用者中註冊的其中一個網域相符（除了\*onmicrosoft.com），才能將它配對。 SBC \*FQDN 名稱不支援使用 onmicrosoft.com 功能變數名稱。 例如，如果您有兩個功能變數名稱：<br/><br/>
  > **contoso**<br/>**contoso**. onmicrosoft.com<br/><br/>
  > 針對 SBC 名稱，您可以使用名稱 sbc.contoso.com。 如果您嘗試將 SBC 與 name （contoso..）結合使用，系統將不會讓您，因為該域不是由這個租使用者所擁有。<br/>
  > 除了在您的租使用者中註冊的網域外，請務必先擁有該網域的使用者以及指派的 E3 或 E5 授權。 如果不是，您會收到下列錯誤：<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
回報
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
您可以在連線程式期間設定其他選項。 不過，在前面的範例中，只會顯示所需的最低參數。 
 
下表列出您可以在設定參數時使用的其他參數```New-CsOnlinePstnGateway```。

|必填？|名稱|描述|設置|可能值|類型與限制|
|:-----|:-----|:-----|:-----|:-----|:-----|
|是|稱|SBC 的 FQDN 名稱 |無|NoneFQDN name，限制63字元|在[Active Directory 中針對電腦、網域、網站和組織單位命名慣例](https://support.microsoft.com/help/909264)的允許和禁止字元清單|
|否|MediaBypass |指示 SBC 的參數支援「媒體旁路」，且系統管理員想要使用它。|無|滿足<br/>虛假|Boolean|
|是|SipSignalingPort |使用傳輸層安全性（TLS）通訊協定，與直接路由服務通訊時所使用的偵聽埠。|無|任何埠|0到65535 |
|否|FailoverTimeSeconds |當設定為10（預設值）時，閘道不會在10秒內應答的輸出呼叫會路由至下一個可用的幹線;如果沒有其他 trunks，就會自動中斷通話。 組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。 預設值為10。|第|電話|Int|
|否|ForwardCallHistory |指出是否透過主幹轉送通話記錄資訊。 如果啟用，Office 365 PSTN Proxy 會傳送兩個標頭： [歷程記錄] 資訊和 [參照者]。 預設值為**False** （$False）。 |虛假|滿足<br/>虛假|Boolean|
|否|ForwardPAI|指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。 PAI 標頭可用於驗證來電者的身分識別。 如果啟用，則也會傳送隱私權： ID 標頭。 預設值為**False** （$False）。|虛假|滿足<br/>虛假|Boolean|
|否|SendSIPOptions |定義 SBC 是否將傳送 SIP 選項。 如果停用，則會將 SBC 排除在監視及觸發系統中。 我們強烈建議您啟用 SIP 選項。 預設值為**True**。 |滿足|滿足<br/>虛假|Boolean|
|否|MaxConcurrentSessions |由觸發系統所使用。 設定任何值後，當併發會話數量為90% 或高於此值時，警示系統會為租使用者管理員產生警示。 如果未設定參數，就不會產生預警。 不過，監視系統會在每24小時報告併發會話數目。 |非|非<br/>1到100000 ||
|否|MediaRelayRoutingLocationOverride |允許手動選取媒體路徑。 [直接傳送] 會根據 SBC 的公用 IP，指派媒體路徑的資料中心。 我們總是選取最接近 SBC 資料中心的資料。 不過，在某些情況下，例如，美國範圍的公用 IP 可指派給位於歐洲的 SBC。 在此情況下，我們會使用不是最佳的媒體路徑。 這個參數可讓您手動設定媒體流量的首選區域。 只有在通話記錄清楚指出自動指派媒體路徑的資料中心無法指派最接近 SBC 資料中心的情況下，Microsoft 才建議您設定此參數。 |無|ISO 格式的國家/地區代碼||
|否|後|用來針對撥出通話啟用這個 SBC。 可用於在 SBC 更新期間或在維護期間暫時移除它。 |虛假|滿足<br/>虛假|Boolean|
 
## <a name="verify-the-sbc-connection"></a>驗證 SBC 連接 

若要驗證連接： 
- 檢查 SBC 是否在成對的 SBCs 清單中。 
- 驗證 SIP 選項。 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>檢查 SBC 是否在成對的 SBCs 清單中 

在您連接 SBC 之後，請在遠端 PowerShell 會話中執行下列命令，以驗證 SBC 是否出現在成對的 SBCs 清單中： 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

成對閘道應該會出現在清單中，如下列範例所示，且**Enabled**參數應該顯示**True**值。 


返回：
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

### <a name="validate-sip-options-flow"></a>驗證 SIP 選項流程 

若要使用外寄 SIP 選項驗證配對，請使用 SBC 管理介面，並確認 SBC 是否收到其外寄選項訊息的 200 OK 回應。

當直接路由查看內送的選項時，它會開始將傳出的 SIP 選項訊息傳送到 [傳入選項] 訊息中的 [連絡人頭] 欄位中設定的 SBC FQDN。 

若要使用傳入的 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的選項訊息，且其傳送的回應代碼為 200 OK。


## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
