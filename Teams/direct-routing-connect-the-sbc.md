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
description: 瞭解如何設定您的 SBC 並將其連線至手機系統直通路由。
ms.openlocfilehash: 900c8c50f60842465ae6a636d5953be81c83af84
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077618"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>將您的會話邊界控制器（SBC）連線至直接路由

本文說明如何設定會話邊界控制器（SBC），並將它連線至 [電話系統直接路由]。  以下是設定直接路由的步驟1：

- **步驟1。將您的 SBC 與電話系統連接並驗證**連線（本文）
- 步驟2。 [允許使用者直接傳送](direct-routing-enable-users.md)
- 步驟3。 [設定通話路由](direct-routing-voice-routing.md)
- 步驟4。 [將數位轉換成替換格式](direct-routing-translate-numbers.md) 

如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定[直接路由](direct-routing-configure.md)。

您可以使用[Microsoft 團隊系統管理中心](#using-the-microsoft-teams-admin-center)或[POWERSHELL](#using-powershell)來設定 SBC，並將其連線至直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 [**語音**  >  **直式路由**]，然後按一下 [ **SBCs** ] 索引標籤。
2. 按一下 [**新增**]。
3. 輸入 SBC 的 FQDN。 <br><br>確認 FQDN 的功能變數名稱部分符合您在租使用者註冊的網域，並請記住， `*.onmicrosoft.com` SBC FQDN 功能變數名稱不支援該功能變數名稱。 例如，如果您有兩個功能變數名稱， `contoso.com` 且 `contoso.onmicrosoft.com` 使用的 `sbc.contoso.com` 是 SBC 名稱。
4. 根據貴組織的需求，為 SBC 設定下列設定。 如需這些設定的詳細資料，請參閱[SBC 設定](#sbc-settings)。

    ![Microsoft 團隊系統管理中心 [新增 SBC] 頁面的螢幕擷取畫面](media/direct-routing-add-sbc.png)

5. 完成後，按一下 [儲存]****。

## <a name="using-powershell"></a>使用 PowerShell

若要將您的 SBC 連線至直接路由，您必須：

1. [使用 PowerShell 連線到商務用 Skype Online](#connect-to-skype-for-business-online-by-using-powershell)。
2. [將 SBC 連接至租](#connect-the-sbc-to-the-tenant)使用者。
3. [確認 SBC](#verify-the-sbc-connection)連線。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 連線到商務用 Skype Online

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

### <a name="connect-the-sbc-to-the-tenant"></a>將 SBC 連接至租使用者

使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) CMDLET 將 SBC 連接至租使用者。 在 PowerShell 會話中，輸入下列內容，然後按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 我們建議您在 SBC 中使用可在 SBC 檔中找到的資訊來設定最大通話限制。 如果 SBC 是容量等級，則限制會觸發通知。
  > 2. 您只能在 SBC 的網域部分與您在租使用者中註冊的其中一個網域（onmicrosoft.com 除外）進行連接。 \* \*SBC FQDN 名稱不支援使用 onmicrosoft.com 功能變數名稱。 例如，如果您有兩個功能變數名稱、 **contoso**和**contoso**onmicrosoft.com，就可以使用 sbc 來取得 sbc 名稱。 如果您嘗試使用名稱（例如 SBC）來連接 SBC，則系統不會讓您，因為該域不是由這個租使用者所擁有。<br/>
  > 除了在您的租使用者中註冊的網域之外，您還必須擁有擁有該網域的使用者以及指派的 E3 或 E5 授權。 如果不是，您會收到下列錯誤：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

以下是一個範例：

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

返回：

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
> 這個範例只會顯示所需的最低參數。 您可以在連線過程中，使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 來設定其他參數。 若要深入瞭解，請參閱[SBC 設定](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>驗證 SBC 連接

若要驗證連接：

- [檢查 SBC 是否在成對的 SBCs 清單中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [驗證 SIP 選項](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>檢查 SBC 是否在成對的 SBCs 清單中

在您連接 SBC 之後，請使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) Cmdlet，確認 SBC 出現在成對的 SBCs 清單中。 在遠端 PowerShell 會話中輸入以下內容，然後按 Enter：

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

#### <a name="validate-sip-options"></a>驗證 SIP 選項

若要使用外寄 SIP 選項驗證配對，請使用 SBC 管理介面，並確認 SBC 是否收到其外寄選項訊息的 200 OK 回應。

當直接路由查看內送的選項時，它會開始將傳出的 SIP 選項訊息傳送到 [傳入選項] 訊息中的 [連絡人頭] 欄位中設定的 SBC FQDN。 

若要使用傳入的 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的選項訊息，且其傳送的回應代碼為 200 OK。

## <a name="sbc-settings"></a>SBC 設定

下表列出您可以在 Microsoft 團隊系統管理中心和使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) Cmdlet 設定的 SBC 選項。

|必填？|Microsoft 團隊系統管理中心設定|PowerShell 參數|描述|設置|可能值|類型與限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**為 SBC 新增 FQDN**|稱 |無|FQDN 名稱，限制63字元|字串，請參閱[適用于電腦、網域、網站和組織單位之 Active Directory 中的命名約定](https://support.microsoft.com/help/909264)的允許和禁止字元清單|
|否|**後**|後|用來針對撥出通話開啟 SBC。 您可以使用此程式在服務更新期間或在維護期間，暫時將 SBC 從服務中移除。 |虛假|滿足<br/>虛假|Boolean|
|是|**SIP 信號埠**|SipSignalingPort |這是用來透過傳輸層（TLS）通訊協定與直接路由進行通訊的偵聽埠。|無|任何埠|0到65535 |
|否|**傳送 SIP 選項**|SendSIPOptions |定義 SBC 是否會傳送 SIP 選項訊息。 我們強烈建議您開啟此設定。 當此設定為 [關閉] 時，系統會將 SBC 排除在監視及報警系統中。|滿足|滿足<br/>虛假|Boolean|
|否|**轉接通話記錄**|ForwardCallHistory |指出通話記錄資訊是否是透過主幹來轉寄。 當您開啟此程式時，Microsoft 365 或 Office 365 proxy 會傳送歷程記錄資訊，並依標頭所參照。 |虛假|滿足<br/>虛假|Boolean|
|否|**轉寄 P-已斷言身分識別（PAI）標頭**|ForwardPAI|指示 PAI 標頭是否與通話一起轉寄。 PAI 標頭可用於驗證來電者的身分識別。 如果此設定為 [開啟]，則也會傳送隱私權： ID 標頭。|虛假|滿足<br/>虛假|Boolean|
|否|**並行通話容量**|MaxConcurrentSessions |當您設定值時，當併發會話數量為90% 或高於此值時，警示系統會通知您。 如果您沒有設定值，就不會產生警示。 不過，監視系統會每隔24小時報告併發會話數目。 |非|非<br/>1到100000 ||
|否|**容錯移轉回應代碼**|FailoverResponseCodes<br>|如果直接路由收到任何用於回應傳出邀請的4xx 或 6xx SIP 錯誤碼，則預設會視為已完成通話。 [外寄] 表示從團隊用戶端撥打電話至 PSTN 與流量流程：團隊用戶端-> 直接路由-> SBC > 電話網絡）。 當您指定容錯移轉回應程式碼時，會強制進行直接路由來嘗試另一個 SBC （如果使用者的語音路由原則中存在另一個 SBC），而當 SBC 由於網路或其他問題而無法撥打電話時，會收到指定的程式碼。 若要深入瞭解，請參閱[從會話邊界控制器（SBC）收到的特定 SIP 代碼的容錯移轉](direct-routing-trunk-failover-on-outbound-call.md)。|408、503、504||Int|
|否|**容錯移轉時間（秒）**|FailoverTimeSeconds |當您設定值時，在您設定的時間內，閘道未接聽的出站通話會傳送到下一個可用的幹線。 如果沒有其他 trunks，就會自動中斷通話。 預設值為10秒。 在有緩慢網路和閘道回應的組織中，這可能會導致不必要地放棄呼叫。|第|電話|Int|
|否|**媒體流量的喜好國家或地區**|MediaRelayRoutingLocationOverride |用來手動設定媒體流量的喜好國家或地區。 我們建議您只有在通話記錄清楚指出媒體路徑的資料中心的預設指派無法使用最接近 SBC 資料中心的路徑時，才能設定此選項。 根據預設，直接路由會根據 SBC 的公用 IP 位址來指派資料中心，並總是選取最接近 SBC 資料中心的路徑。 不過，在某些情況下，預設路徑可能不是最佳路徑。 此參數可讓您手動設定媒體流量的喜好區域。 |無|ISO 格式的國家/地區代碼||
|否|**SBC 支援 PIDF/LO 以進行緊急通話**|PidfloSupported|指定 SBC 是否支援緊急呼叫的「目前狀態資訊資料格式位置」物件（PIDF/LO）。||||
|否|**嘗試尋找使用者時撥打電話**|GenerateRingingWhileLocatingUser|設定是否要在來電者中播放音訊信號，以指出團隊正在進行通話的過程。 此設定僅適用于非媒體旁路模式中的直接路由。 有時，從 PSTN 到團隊用戶端的撥入呼叫可能需要比預期更長的時間才能建立。 在這種情況下，來電者可能不會聽到任何問題，小組用戶端就不會響鈴，而且通話可能會被某些電訊提供者取消。 此設定可協助避免在這些案例中可能會發生的意外 silences。|滿足|滿足<br/>虛假|Boolean|
|否| - |MediaBypass|這個設定指出 SBC 是否支援媒體旁路，以及您是否要將它用於此 SBC。 |無|滿足<br/>虛假|Boolean|

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)
