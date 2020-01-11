---
title: 設定直接路由
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
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: 7a3cd61c3b92482fd402b58734b2af720c21cf3a
ms.sourcegitcommit: f238d70aa34cded327ed252b0eb2704cc7f8f5c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2020
ms.locfileid: "41023417"
---
# <a name="configure-direct-routing"></a>設定直接路由

> [!Tip]
> 請觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式：[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)

如果您尚未這麼做，請閱讀規劃先決條件的 [[直接路由](direct-routing-plan.md)]，並查看設定 Microsoft Phone 系統網路之前所需採取的其他步驟。 

本文說明如何設定 Microsoft Phone 系統 Direct 路由。 它詳細說明如何將支援的會話邊界控制器（SBC）搭配使用，以直接傳送路線，以及如何將 Microsoft 團隊使用者設定為使用直接路由來連接至公用的交換電話網絡（PSTN）。 若要完成本文所述的步驟，管理員需要熟悉 PowerShell Cmdlet。 如需有關使用 PowerShell 的詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

我們建議您確認您的 SBC 已按照您的 SBC 廠商的建議進行設定： 

- [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系統（anynode）部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

您可以設定您的 Microsoft 手機系統，並讓使用者使用直接路由，然後將 Microsoft 團隊設定為首選的呼叫用戶端，方法是完成下列程式： 

- [將 SBC 與 Microsoft 手機系統配對並驗證配對](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [允許使用者使用直接路由服務](#enable-users-for-direct-routing-service)
- 確定 Microsoft 團隊是使用者的首選呼叫用戶端

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>將 SBC 與電話系統的直接路由服務配對 

以下是可讓您將 SBC 連接或配對至直接路由介面的三個高層次步驟： 

- 使用 PowerShell**連線到商務用 Skype Online**系統管理中心 
- 對 SBC 進行配對 
- 驗證配對 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 連線到商務用 Skype Online 

您可以使用連接至租使用者的 PowerShell 會話，將 SBC 與直接路由介面配對。 若要開啟 PowerShell 會話，請依照[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中所述的步驟進行。 
 
建立遠端 PowerShell 會話之後，請確認您可以看到管理 SBC 的命令。 若要驗證命令，請在 PowerShell 會話中輸入或複製/貼上下列內容，然後按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

您的命令會傳回這裡顯示的四個函數，可讓您管理 SBC。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>將 SBC 與租使用者配對 

若要將 SBC 與租使用者進行配對，請在 PowerShell 會話中輸入下列內容，然後按 Enter 鍵： 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. 我們強烈建議您在 SBC 中設定最大通話限制，使用可在 SBC 檔中找到的資訊。 如果 SBC 是容量等級，則限制會觸發通知。
  > 2. 您只能將 SBC 的網域部分與您在租使用者中註冊的其中一個網域相符（除了\*onmicrosoft.com），才能將它配對。 SBC \*FQDN 名稱不支援使用 onmicrosoft.com 功能變數名稱。 例如，如果您有兩個功能變數名稱：<br/><br/>
  > **contoso**<br/>**contoso**. onmicrosoft.com<br/><br/>
  > 針對 SBC 名稱，您可以使用名稱 sbc.contoso.com。 如果您嘗試將 SBC 與 name （contoso..）結合使用，系統將不會讓您，因為該域不是由這個租使用者所擁有。<br/>
  > 除了在您的租使用者中註冊的網域外，請務必先擁有該網域的使用者以及指派的 E3 或 E5 授權。 如果不是，您會收到下列錯誤：<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
回報
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
您可以在配對處理期間設定其他選項。 不過，在前面的範例中，只會顯示所需的最低參數。 
 
下表列出您可以在設定參數時使用的其他參數```New-CsOnlinePstnGateway```。

|必填？|名稱|描述|設置|可能值|類型與限制|
|:-----|:-----|:-----|:-----|:-----|:-----|
|是|稱|SBC 的 FQDN 名稱 |無|NoneFQDN name，限制63字元|在[Active Directory 中針對電腦、網域、網站和組織單位命名慣例](https://support.microsoft.com/help/909264)的允許和禁止字元清單|
|否|MediaBypass |指示 SBC 的參數支援「媒體旁路」，且系統管理員想要使用它。|無|滿足<br/>虛假|Boolean|
|是|SipSignallingPort |使用傳輸層安全性（TLS）通訊協定，與直接路由服務通訊時所使用的偵聽埠。|無|任何埠|0到65535 |
|否|FailoverTimeSeconds |當設定為10（預設值）時，閘道不會在10秒內應答的輸出呼叫會路由至下一個可用的幹線;如果沒有其他 trunks，就會自動中斷通話。 組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。 預設值為10。|第|電話|Int|
|否|ForwardCallHistory |指出是否透過主幹轉送通話記錄資訊。 如果啟用，Office 365 PSTN Proxy 會傳送兩個標頭： [歷程記錄] 資訊和 [參照者]。 預設值為**False** （$False）。 |虛假|滿足<br/>虛假|Boolean|
|否|ForwardPAI|指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。 PAI 標頭可用於驗證來電者的身分識別。 如果啟用，則也會傳送隱私權： ID 標頭。 預設值為**False** （$False）。|虛假|滿足<br/>虛假|Boolean|
|否|SendSIPOptions |定義 SBC 是否將傳送 SIP 選項。 如果停用，則會將 SBC 排除在監視及觸發系統中。 我們強烈建議您啟用 SIP 選項。 預設值為**True**。 |滿足|滿足<br/>虛假|Boolean|
|否|MaxConcurrentSessions |由觸發系統所使用。 設定任何值後，當併發會話數量為90% 或高於此值時，警示系統會在租使用者管理員產生警示。 如果未設定參數，就不會產生預警。 不過，監視系統會在每24小時報告併發會話數目。 |非|非<br/>1到100000 ||
|否|MediaRelayRoutingLocationOverride |允許手動選取媒體路徑。 [直接傳送] 會根據 SBC 的公用 IP，指派媒體路徑的資料中心。 我們總是選取最接近 SBC 資料中心的資料。 不過，在某些情況下，來自例如美國範圍的公用 IP 可以指派給位於歐洲的 SBC。 在這種情況下，我們會使用不是最佳的媒體路徑。 這個參數可讓您手動設定媒體流量的首選區域。 我們只建議在通話記錄中清楚指出自動指派媒體路徑的 datacenter，不會指派最接近 SBC 資料中心的資料中心。 |無|ISO 格式的國家/地區代碼||
|否|後|用來針對撥出通話啟用這個 SBC。 可用於暫時移除 SBC，或在進行更新或在維護期間進行。 |虛假|滿足<br/>虛假|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>驗證 SBC 配對 

確認連線： 
- 檢查 SBC 是否在成對的 SBCs 清單中。 
- 驗證 SIP 選項。 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>驗證 SBC 是否在成對半形的清單中 

在您配對 SBC 之後，請在遠端 PowerShell 會話中執行下列命令，以驗證 SBC 是否出現在成對的 SBCs 清單中：`Get-CSOnlinePSTNGateway`

成對閘道應該會出現在清單中，如下列範例所示，然後確認**Enabled**參數顯示的值**為 True**。 鍵

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
返回：
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>驗證 SIP 選項流程 

若要使用外寄 SIP 選項驗證配對，請使用 SBC 管理介面，並確認 SBC 是否收到其外寄選項訊息的 200 OK 回應。

當直接路由查看內送的選項時，它會開始將傳出的 SIP 選項訊息傳送到 [傳入選項] 訊息中的 [連絡人頭] 欄位中設定的 SBC FQDN。 

若要使用傳入的 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的選項訊息，且其傳送的回應代碼為 200 OK。

## <a name="enable-users-for-direct-routing-service"></a>允許使用者使用直接路由服務 

當您準備好要讓使用者使用直接路由服務時，請遵循下列步驟： 

1. 在 Office 365 中建立使用者並指派電話系統授權。 
2. 確定使用者是駐留在商務用 Skype Online 中。 
3. 設定電話號碼，並啟用企業語音及語音信箱。 
4. 設定語音路由。 此路線會自動驗證。

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>在 Office 365 中建立使用者並指派授權 

在 Office 365 中建立新使用者有兩個選項。 不過，建議您的組織選取並使用其中一個選項來避免路由問題： 

- 在內部部署的 Active Directory 中建立使用者，並將使用者同步處理到雲端。 請參閱[將您的內部部署目錄與 Azure Active Directory 整合](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Office 365 管理員入口網站中建立使用者。 請參閱[個別或大量將使用者新增至 Office 365-系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的商務用 skype Online 部署與商務用 Skype 2015 或 Lync 2010/2013 內部部署共同存在，則支援的唯一選項是在內部部署 Active Directory 中建立使用者，並將使用者同步處理到雲端（選項1）。 

如需授權需求的相關資訊，請參閱[規劃直接路由](direct-routing-plan.md)中的[授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>確定使用者是在商務用 Skype Online 中託管 

[直接傳送] 要求使用者駐留在商務用 Skype Online 中。 您可以透過查看 RegistrarPool 參數來檢查此情況。 它必須在 infra.lync.com 網域中有一個值。

1. [連線至遠端 PowerShell]。
2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>設定電話號碼並啟用企業語音及語音信箱 

在您建立使用者並指派授權之後，下一步就是設定他們的電話號碼和語音信箱。 這可以一步完成。 

若要新增電話號碼並啟用語音信箱：
 
1. 連線到遠端 PowerShell 會話。 
2. 輸入命令： 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

例如，若要將使用者的電話號碼新增至 [Spencer Low]，您可以輸入下列專案： 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

所使用的電話號碼必須設定為完整的 E. 164 電話號碼（國家/地區碼）。 

  > [!NOTE]
  > 如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令介面或 [控制台] 來設定使用者的電話號碼。 

### <a name="configure-voice-routing"></a>設定語音路由 

Microsoft Phone 系統有一個路由機制，可讓您根據下列情況，將呼叫傳送到特定的 SBC： 

- 名為 [數位模式] 
- 撥打電話的電話號碼模式 + 特定使用者
 
SBCs 可以指定為 [作用中] 和 [備份]。 這表示當針對此數值模式設定為作用中的 SBC，或數位模式 + 特定使用者時，會將呼叫路由至備份 SBC。
 
[通話路由] 是由下列元素所組成： 
- 語音路由策略– PSTN 用途的容器;可以指派給使用者或多位使用者 
- PSTN 用途–語音路由和 PSTN 用途的容器;可以在不同的語音路由策略中共用 
- 語音路由-數位模式和一組線上 PSTN 閘道，用於撥打電話號碼符合模式的電話 
- 線上 PSTN 閘道-指向 SBC 的指標也會儲存透過 SBC 發出呼叫時所套用的設定，例如轉寄 P 斷言身分識別（PAI）或首選編解碼器。可以新增到語音路由 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>建立具有一個 PSTN 使用量的語音路由策略 

下圖顯示通話流程中的語音路由策略的兩個範例。

**通話流程1（在左邊）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話會路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都無法使用，就會掛斷通話。 

**通話流程2（右側）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話就會先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果沒有可用的 SBC，則會嘗試使用較低優先順序的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。 如果沒有任何 SBCs 可用，就會中斷通話。 

![顯示語音路由策略範例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在這兩個範例中，雖然語音路由是指派優先順序，但路由中的 SBCs 會以隨機順序嘗試。

  > [!NOTE]
  > 除非使用者也有 Microsoft 通話方案授權，否則呼叫範例設定中的 [除了模式 + 1 425 XXX xx xx] 或 [+ 1 206 XXX xx xx] 以外的任何號碼。 如果使用者有通話方案授權，通話會根據 Microsoft 通話方案的原則自動傳送。 

Microsoft 通話方案會自動套用為所有擁有 Microsoft 通話方案授權的使用者，而且不需要額外的呼叫路由設定。

在下圖所示的範例中，新增了語音信箱，以傳送來電給所有其他美國和加拿大的號碼（移至撥打電話號碼模式 + 1 XXX XXX xx XX 的通話）。

![顯示含有第三個路線的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

針對所有其他通話，如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。 如果沒有與管理員建立的線上語音路線中的數位模式相符，請透過 Microsoft 通話方案傳送。

如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。

  > [!NOTE]
  > 在這種情況下，路由 "Other + 1" 的優先順序值不重要，因為只有一個路由符合模式 + 1 XXX XXX XXX xx。 如果使用者撥打電話給 + 1 324 567 89 89，且 sbc5.contoso.biz 和 sbc6.contoso.biz 都無法使用，通話就會斷撥。

下表摘要列出使用三個語音路由的配置。 在這個範例中，所有三個路由都是「美國和加拿大」相同的 PSTN 使用量。

|**PSTN 使用量**|**語音路線**|**數位模式**|**優先順序**|**SBC**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|僅限美國|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼叫號碼 + 1 425 XXX XX xx 美元或 + 1 206 XXX XX xx 的活動路由|
|僅限美國|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|pplx-2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼叫號碼的備份路由 + 1 425 XXX XX XX or + 1 206 XXX XX xx|
|僅限美國|"Other + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼叫號碼的路由 + 1 XXX XXX XXX xx （除 + 1 425 XXX XX 或 + 1 206 XXX XX xx 以外）|
|||||||

所有路由都與 PSTN 使用量「美國和加拿大」相關聯，且 PSTN 使用量與語音路由策略「僅限美國」相關聯。 在這個範例中，語音路由策略會指派給使用者 Spencer Low （低）。

#### <a name="examples-of-call-routes"></a>通話路線範例

在下列範例中，我們將示範如何設定路由、PSTN 使用方式及路由原則，並將原則指派給使用者。

**步驟1：** 建立 PSTN 使用 "美國和加拿大"。

在商務用 Skype 遠端 PowerShell 會話中，鍵入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

輸入以下內容以驗證是否已建立使用： 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
這會傳回可能會被截斷的名稱清單：
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
在下列範例中，您可以查看執行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`以顯示完整名稱（不會被截斷）的結果。

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**步驟2：** 在商務用 Skype Online 的 PowerShell 會話中，建立三個路線：雷德蒙1、雷德蒙2和其他 + 1，如上表所述。 

若要建立「雷蒙德1」路線，請輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

返回：
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
若要建立雷德蒙2路線，請輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要建立其他 + 1 路線，請輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 請確定 NumberPattern 屬性中的正則運算式是有效的運算式。 您可以使用此網站進行測試：[https://www.regexpal.com](https://www.regexpal.com)

在某些情況下，需要將所有呼叫路由至同一個 SBC;請使用-NumberPattern ". *"

將所有呼叫路由至同一個 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用如下所示的選項，驗證您是否已`Get-CSOnlineVoiceRoute`透過執行 PowerShell 命令來正確設定路線：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
應傳回的專案：
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

在這個範例中，「其他 + 1」路由會自動指派優先順序4。 

**步驟3：** 建立「僅限我們」的語音路由策略，並將 PSTN 使用量「美國和加拿大」加入原則。

在商務用 Skype Online 的 PowerShell 會話中，鍵入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

結果會顯示在這個範例中：

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**步驟4：** 使用 PowerShell 授與使用者 Spencer 低的語音路由原則。

在商務用 Skype Online 的 PowerShell 會話中，鍵入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

輸入以下命令以驗證原則指派：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

返回：
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>建立具有幾個 PSTN 用途的語音路由策略

先前建立的語音路由策略只允許撥打美國和加拿大電話號碼，除非使用者也指派 Microsoft 通話方案授權。

在下列範例中，您可以建立語音路由策略「無限制」。 原則會重複使用在上述範例中建立的 PSTN 使用量 "美國和加拿大"，以及新的 PSTN 使用量 "國際"。 

這會將所有其他呼叫路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。 所顯示的範例會將 [僅限美國] 原則指派給使用者 "Spencer Low"，而不限制使用者「John 的使用方式」。

Spencer [低] –只允許通話至美國和加拿大號碼。 呼叫雷德蒙的數位範圍時，必須使用一組特定的 SBC。 除非指派給使用者的是通話方案授權，否則不會路由非美國數位。

John：可撥打任何號碼的電話。 呼叫雷德蒙的數位範圍時，必須使用一組特定的 SBC。 非美國數位會透過 sbc2.contoso.biz 和 sbc5.contoso.biz 路由。

![顯示指派給使用者 Spencer 低的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

針對所有其他通話，如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。 如果沒有與管理員建立的線上語音路線中的數位模式相符，請透過 Microsoft 通話方案傳送。

如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。

![顯示指派給使用者 John 的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表摘要列出路由策略「無限制」的使用方式指派和語音路由。 

|**PSTN 使用量**|**語音路線**|**數位模式**|**優先順序**|**SBC**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|僅限美國|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被呼叫者編號的作用中路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx|
|僅限美國|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|pplx-2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被呼叫者編號的備份路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx|
|僅限美國|"Other + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|被呼叫者的電話號碼 + 1 XXX XXX XX （不包括 + 1 425 XXX XX 或 + 1 206 XXX xx xx）|
|國際|國際|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何數位模式的路線 |


  > [!NOTE]
  > - 語音路由策略中的 PSTN 使用順序非常重要。 此用法會依順序套用，如果在第一個用法中找到一個相符專案，則永遠不會評估其他用法。 Pstn 使用量 "國際" 必須放在 PSTN 使用 [僅限美國] 後。 若要變更 PSTN 用法的順序，請執行`Set-CSOnlineVoiceRoutingPolicy`命令。 <br/>例如，若要將訂單從 "美國和加拿大" 先變更為 [國際 "，然後再執行相反順序：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 系統會自動指派「其他 + 1」和「國際」語音路由的優先順序。 只要其優先順序低於「雷蒙德1」和「雷蒙德2」，就不重要。

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>使用者 John 的語音路由策略範例

建立 PSTN 使用量 "國際"，語音路由 "國際，" 語音路由策略 "無限制，然後再將它指派給使用者「John 54777」的步驟如下所示。


**步驟 1**：建立 PSTN 使用 "國際"。 

在商務用 Skype Online 的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**步驟 2**：建立新的語音路由「國際」。

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
返回：

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**步驟 3**：建立語音路由策略「無限制」。 

在此語音路由原則中，PSTN 使用 "雷德蒙 1" 和 "雷德蒙" 會重複使用，以保留對號碼 "+ 1 425 XXX XX" 和 "+ 1 206 XXX XX" （作為本機或內部部署的呼叫）的特殊處理。

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

請注意 PSTN 的使用順序：

是. 如果撥打的號碼是 "+ 1 425 XXX XX"，且使用下列範例所述的使用方式，則呼叫會遵循「美國和加拿大」用法中的路由設定，並套用特殊路由邏輯。 也就是說，通話是使用 sbc1.contoso.biz 和 sbc2.contoso.biz 進行路由，然後 sbc3.contoso.biz 和 sbc4.contoso.biz 做為備份路由。

乙. 如果「國際」 PSTN 使用量在「美國和加拿大」之前，則對 + 1 425 XXX XX 的呼叫會路由至 sbc2.contoso.biz 和 sbc5.contoso.biz，成為路由邏輯的一部分。 輸入命令：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

傳回

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**步驟 4**：使用下列命令，將語音路由策略指派給使用者「John xxxxx」。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

然後使用命令驗證作業： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

返回：

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

結果是，套用到 John 54777 通話的語音原則是不受限制的，將遵循可供美國、加拿大和國際電話使用的呼叫路由的邏輯。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>將 [僅限團隊] 模式指派給使用者，以確保在 Microsoft 團隊中撥打土地

直接路由要求使用者只能在 [僅限團隊] 模式中，以確保來電在團隊用戶端中保持通話。 若要將使用者置於 [僅限團隊] 模式，請將 [UpgradeToTeams] TeamsUpgradePolicy 的實例指派給他們。 如果您的組織使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，以瞭解 Skype 與團隊之間的資訊互用性：[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>設定直接傳送來電至語音信箱

[直接路由] 可讓您結束通話呼叫並直接傳送給使用者的語音信箱。 如果您想要直接將來電傳送到語音信箱，請將不透明的 = app 附加至 [要求 URI 標頭]。 例如，「sip： user@yourdomain .com; 不透明 = app：語音信箱」。
在這種情況下，小組使用者將不會收到來電通知，該通話會直接連線至使用者的語音信箱。

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>將撥出和撥出電話的呼叫者和來電數轉換為替代格式

有時候，租使用者管理員可能會根據其建立的模式變更本機號碼和/或撥入式通話，以確保互通性的方程式。 您可以設定一個數位翻譯規則原則，以將被呼叫者或來電者編號轉換成替代格式。 您可以使用原則來轉譯下列各項的數位：

- 入站通話：從 PSTN 端點（來電者）到團隊用戶端（被呼叫者）的呼叫。
- [呼出通話]：從團隊用戶端（來電者）到 PSTN 端點（被叫方）的呼叫。

原則會套用到 SBC 層級。 您可以將多個翻譯規則指派給 SBC，這些規則會依您在 PowerShell 中列出它們時的出現順序來套用。 您也可以在原則中變更規則的順序。

若要建立、修改、查看及刪除數位處理規則，請使用[新的 CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)及[Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) Cmdlet。

若要在 SBCs 上指派、設定及列出編號操作規則，請[使用新的 CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)和[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 以及```InboundTeamsNumberTranslationRules```、 ```InboundPSTNNumberTranslationRules``` ```OutboundTeamsNumberTranslationRules``` ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```、、、、、、、、、、 ```OutboundPSTNNumberTranslationRulesList``` 、、、、、、、、、、和參數。

### <a name="examples"></a>範例

#### <a name="example-sbc-configuration"></a>SBC 範例配置

在範例案例中，我們會執行```New-CsOnlinePSTNGateway``` Cmdlet 來建立下列的 SBC 配置。

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

指派給 SBC 的翻譯規則摘要如下表所示。

|名稱  |模式 |翻譯  |
|---------|---------|---------|
|AddPlus1     |^ （\d{10}） $          |+ 1 $ 1          |
|AddE164SeattleAreaCode      |^ （\d{4}） $          | + 1206555 $ 1         |
|AddSeattleAreaCode    |^ （\d{4}） $          | 425555 $ 1         |
|StripPlus1    |^ + 1 （\d{10}） $          | $1         |

在這些範例案例中，我們有兩個使用者、Alice 和 Bob。 劉愛琳是團隊使用者，她的號碼是 + 1 206 555 0100。 Bob 是 PSTN 使用者，而其號碼是 + 1 425 555 0100。

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>範例1：撥入至十位數的電話

Bob 使用非 E. 164 10 位數的數位呼叫 Alice。 王俊元會撥打2065550100，以達到 Alice。
SBC 在 RequestURI 中使用2065550100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。

|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:2065550100@sbc.contoso.com|邀請 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|自    |至： \<sip:2065550100@sbc.contoso.com>|至： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|從   |發件\<人： sip:4255550100@sbc.contoso.com>|發件\<人： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>範例2：撥入至四位數的電話號碼

Bob 使用四位數的數位撥打 Alice。 王俊元會撥打0100，以達到 Alice。
SBC 在 RequestURI 中使用0100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。

|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com          |邀請 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|自    |至： \<sip:0100@sbc.contoso.com>|至： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|從   |發件\<人： sip:4255550100@sbc.contoso.com>|發件\<人： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>範例3：使用10位數的非 E. 164 號碼撥出通話

劉愛琳會使用十位數的數位呼叫 Bob。 劉愛琳會撥打 425 555 0100 來取得 Bob 的聯繫。
SBC 針對團隊和 PSTN 使用者設定為使用非 E. 164 10 位數的數位。

在這種情況下，撥號方案會在傳送數位至直接路由介面之前先轉換號碼。 當 Alice 在 [團隊用戶端] 中輸入 425 555 0100 時，該數位會依國家/地區撥號方案轉譯為 [+ 14255550100]。 產生的數位是撥號方案規則與團隊翻譯規則的累計正常化。 團隊翻譯規則會移除撥號方案新增的 "+ 1"。

|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:+14255550100@sbc.contoso.com          |邀請 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|自    |至： \<sip:+14255550100@sbc.contoso.com>|至： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|從   |發件\<人： sip:+12065550100@sbc.contoso.com>|發件\<人： sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>範例4：使用四位數的非 E. 164 號碼撥出通話

劉愛琳會使用四位數的數位呼叫 Bob。 Alice 使用0100來從來電到 Bob 或使用連絡人。
SBC 設定為使用非 E. 164 個4位數的團隊使用者，以及十位數的 PSTN 使用者數位。 在這種情況下，不會套用撥號方案。

|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com           |邀請 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|自    |至： \<sip:0100@sbc.contoso.com>|至： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|從   |發件\<人： sip:+12065550100@sbc.contoso.com>|發件\<人： sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)
