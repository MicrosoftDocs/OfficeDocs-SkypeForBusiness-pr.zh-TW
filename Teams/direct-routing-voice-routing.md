---
title: 設定直接路由的語音路由
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
description: 瞭解如何使用 Microsoft Phone System Direct 路由設定語音路由。
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383977"
---
# <a name="configure-voice-routing-for-direct-routing"></a>設定直接路由的語音路由

本文將說明如何設定電話系統直接路由的語音路由。  這是下列步驟中的步驟 3，用於配置直接路由：

- 步驟 1。 [使用 Microsoft Phone 系統連接 SBC 並驗證連接](direct-routing-connect-the-sbc.md) 
- 步驟 2. [啟用使用者進行直接路由、語音和語音信箱](direct-routing-enable-users.md)
- **步驟 3.設定語音路由** (本文) 
- 步驟 4. [將數位轉換成替代格式](direct-routing-translate-numbers.md) 

若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>語音路由概觀

Microsoft Phone System 具有路由機制，可讓通話傳送至特定會話邊界控制器 (SBC) 根據： 

- 稱為數位模式 
- 所謂的號碼模式加上撥打電話的特定使用者
 
SBCs 可指定為使用中和備份。 當已配置為使用中 SBC 的 SBC 不適用於特定通話路由時，該通話會路由至備份 SBC。
 
語音路由由下列元素組成： 

- **語音路由策略** ： PSTN 使用方式的容器，可指派給使用者或多個使用者。 

- **PSTN 使用** 方式 ： 語音路由和 PSTN 使用方式的容器，可在不同的語音路由策略中共用。 

- **語音路由** ： 號碼模式和一組線上 PSTN 閘道，用於電話號碼符合該模式的通話。

- **線上 PSTN** 閘道 - 指向 SBC 的指標，該指標也會儲存透過 SBC 進行通話時所適用之組式，例如轉寄 P-Identity (PAI) 編解碼器;可以新增到語音路由。

## <a name="voice-routing-policy-considerations"></a>語音路由策略考慮

如果使用者有通話方案授權，該使用者的外發通話會自動透過 Microsoft 通話方案 PSTN 基礎結構路由。 如果您設定線上語音路由策略並指派給通話方案使用者，會檢查該使用者的外撥電話，以判斷撥號號碼是否符合線上語音路由策略中定義的號碼模式。 如果有相符專案，電話會透過直接路由主幹路由。 如果沒有相符專案，通話會透過通話方案 PSTN 基礎結構路由。

> [!CAUTION]
> 如果您設定並適用全域 (全組織的預設) 線上語音路由原則，貴組織中所有支援語音的使用者都會繼承該原則，這可能會導致從通話方案使用者的 PSTN 通話不小心路由到直接路由主幹。 如果您不希望所有使用者都使用全域線上語音路由策略，請設定自訂的線上語音路由策略，並將其指派給啟用語音的個別使用者。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>範例 1：使用一個 PSTN 的語音路由

下圖顯示通話流程的兩個語音路由策略範例。

**呼叫流程 1 (左側) ：** 如果使用者撥打 +1 425 XXX XX XX 或 +1 206 XXX XX XX，通話會路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 或 sbc2.contoso.biz，通話會中斷。 

**通話流程 2 (右側) ：** 如果使用者撥打 +1 425 XXX XX XX 或 +1 206 XXX XX XX，該通話會先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果兩者均無法使用 SBC，系統將會嘗試優先順序較低的路由， (sbc3.contoso.biz sbc4.contoso.biz) 。 如果沒有任何 SBCs 可用，系統即會中斷通話。 

![顯示語音路由策略範例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在這兩個範例中，當語音路由被指派優先順序時，路由中的 SBC 會隨機嘗試。

  > [!NOTE]
  > 除非使用者也擁有 Microsoft 通話方案授權，否則除了範例組式中符合模式 +1 425 XXX XX XX 或 +1 206 XXX XX XX 以外的任何號碼會中斷通話。 如果使用者有通話方案授權，系統就會根據 Microsoft 通話方案的政策自動路由通話。 Microsoft 通話方案會自動作為最後一個路由，適用于擁有 Microsoft 通話方案授權且不需要其他通話路由配置的所有使用者。

在下列圖表所示的範例中，會新增語音路由，以將電話傳送給所有其他美國和加拿大號碼 (呼叫稱為號碼模式 +1 XXX XXX XX XX) 。

![顯示具有第三個路由的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

對於所有其他通話，如果使用者同時擁有 Microsoft Phone system (Microsoft 通話方案) ，系統即會使用自動路由。 如果管理員所建立的線上語音路由中沒有任何符合號碼模式，則通話會透過 Microsoft 通話方案路由。 如果使用者只有 Microsoft Phone System，系統會因為找不到符合的規則而中斷通話。

  > [!NOTE]
  > 在這種情況下，路由 「其他 +1」 的優先順序值並不重要，因為只有一個路由符合模式 +1 XXX XXX XX XX。 如果使用者撥打 +1 324 567 89 89，sbc5.contoso.biz 和 sbc6.contoso.biz，通話即會中斷。

下表摘要列出使用三種語音路由的組態。 在此範例中，這三個路由都是相同 PSTN 使用量的一部分，即「美國和加拿大」。  所有路由都與「美國和加拿大」PSTN 使用量相關聯，而 PSTN 使用量則與「僅美國」語音路由政策相關聯。

|**PSTN 使用量**|**語音路由**|**數位圖樣**|**優先**|**Sbc**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|"Redmond 1"|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|稱為號碼的主動路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美國和加拿大|"Redmond 2"|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|稱為號碼的備份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美國和加拿大|「其他 +1」|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|除了 + (1 425 XXX XX XX 或 +1 206 XXX XX XX) |
|||||||

## <a name="example-1-configuration-steps"></a>範例 1：組組步驟

下列範例顯示如何：

1. 建立單一 PSTN 使用量。
2. 設定三個語音路由。
3. 建立語音路由策略。
4. 將策略指派給名為 Spencer Low 的使用者。

您可以使用 Microsoft [Teams 系統管理中心或](#admincenterexample1) [PowerShell](#powershellexample1) 來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟 1：建立「美國和加拿大」PSTN 使用量

1. 在 Microsoft Teams 系統管理中心的左側導航中，前往 **[語音** 直接路由>，然後在右上角選取 [  >  ******管理 PSTN 使用記錄**> 。
2. 按一下 **[新增**，**輸入美國和加拿大**，然後按一下 **[Apply.**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟 2：建立三個語音路由 (Redmond 1、Redmond 2 和其他 +1) 

下列步驟說明如何建立語音路由。 使用這些步驟，使用上一個資料表中概述的設定，針對此範例建立名為 Redmond 1、Redmond 2 和 Other +1 的三個語音路由。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **直接路由**，然後選取 **語音路由定位** 點。
2. 按一下 **[新增**」，然後輸入語音路由的名稱和描述。
3. 設定優先順序並指定撥號號碼模式。
4. 若要使用語音路由註冊 SBC，請在註冊 (選擇性) 的 **SBC** 下，按一下 [新增 SBC，選取您想要註冊的 **SBC，** 然後按一下 [ **申請**> 。
5. 若要新增 PSTN 使用量記錄，請在 **PSTN** 使用記錄 (選擇性) 下，按一下 [新增 **PSTN** 使用量，選取您想要新增的 PSTN 記錄，然後按一下 **[Apply.**
6. 按一下 [儲存]。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟 3：建立名為「僅美國」的語音路由策略，並新增「美國和加拿大」PSTN 使用方式至該政策

1. 在 Microsoft Teams 系統管理中心的左側導航中，前往 **[**  >  **語音語音路由規則**，然後按一下 [**新增**> 。
2. 輸入 **US Only** 做為名稱並新增描述。
3. 在 **PSTN 使用量記錄下**，按一下 [ **新增 PSTN 使用量**，選取 「美國和加拿大」PSTN 使用記錄，然後按一下 [ **適用**> 。
4. 按一下 [儲存]。

若要深入瞭解，請參閱管理 [語音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟 4：將語音路由策略指派給名為 Spencer Low 的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 按一下 **[政策**」，然後按一下 [ **已指派之策略>** 旁的 [ **編輯**> 。
3. 在 **[語音路由策略>** 下，選取 [僅適用于美國」政策，然後按一下 [ **儲存**。

若要深入瞭解，請參閱管理 [語音路由策略](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟 1：建立「美國和加拿大」PSTN 使用量

在商務用 Skype Online 中的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

確認使用方式是輸入：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

會返回可能會被截斷的名稱清單：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

下列範例顯示執行 PowerShell 命令以顯示完整名稱 (`(Get-CSOnlinePSTNUsage).usage` 未) ：

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟 2：建立三個語音路由 (Redmond 1、Redmond 2 和其他 +1) 

若要建立「Redmond 1」路由，請在商務用 Skype Online 的 PowerShell 會話中輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

這會返回：

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

若要建立 Redmond 2 路由，請輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要建立其他 +1 路由，請輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 請確定 NumberPattern 屬性中的正則運算式是有效的運算式。 您可以使用這個網站來測試： [https://www.regexpal.com](https://www.regexpal.com)

在某些情況下，需要將所有通話路由至同一個 SBC;use -NumberPattern ".*"

將所有通話路由至相同的 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用選項執行 PowerShell 命令，確認您正確配置路由， `Get-CSOnlineVoiceRoute` 如下所示：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
應該會返回：

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

在範例中，路由「其他 +1」已自動指派優先順序 4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟 3：建立名為「僅美國」的語音路由策略，並新增「美國和加拿大」PSTN 使用方式至該政策

在商務用 Skype Online 的 PowerShell 會話中，輸入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此範例顯示結果：

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟 4：將語音路由策略指派給名為 Spencer Low 的使用者

在商務用 Skype Online 的 PowerShell 會話中，輸入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

輸入此命令以驗證策略指派：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

命令會返回下列專案：

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>範例 2：使用多個 PSTN 使用方式的語音路由

在範例 1 中建立的聲音路由策略只允許撥打美國和加拿大的電話號碼，除非 Microsoft 通話方案授權也指派給使用者。

在以下範例中，您可以建立「無限制」語音路由策略。 此政策會重複使用在範例 1 中建立「美國和加拿大」PSTN 使用方式，以及新的「國際」PSTN 使用量。 此策略會路由所有其他通話至 SBC sbc2.contoso.biz sbc5.contoso.biz。

顯示的範例將 US Only 策略指派給使用者 Spencer Low，以及無限制策略指派給使用者 John Woods，讓路由執行方式如下：

- Spencer Low – 僅美國政策。  只能撥打美國和加拿大號碼。 撥打至 Redmond 號碼範圍時，必須使用一組特定的 SBC。 除非指派通話方案授權給使用者，否則不會路由非美國號碼。

- John Woods – 國際政策。  任何號碼都允許通話。 撥打至 Redmond 號碼範圍時，必須使用一組特定的 SBC。 非美國號碼會使用 sbc2.contoso.biz sbc5.contoso.biz。

![顯示指派給使用者 Spencer Low 的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

對於所有其他通話，如果使用者同時擁有 Microsoft Phone system (Microsoft 通話方案) ，則系統會使用自動路由。 如果管理員所建立的線上語音路由中沒有任何符合號碼模式，則通話會使用 Microsoft 通話方案路由。  如果使用者只有 Microsoft Phone System，系統會因為找不到符合的規則而中斷通話。

![顯示指派給使用者 John Woods 的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表摘要列出路由策略「無限制」的使用指定和語音路由。 

| PSTN 使用量 | 語音路由 | 數位圖樣 | 優先 | Sbc | 描述 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|"Redmond 1"|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|通話者號碼的活動路由 +1 425 XXX XX 或 +1 206 XXX XX|
|美國和加拿大|"Redmond 2"|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|通話者號碼的備份路由 +1 425 XXX XX 或 +1 206 XXX XX|
|美國和加拿大|「其他 +1」|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|通話者號碼 +1 XXX XXX XX XX (除了 +1 425 XXX XX XX 或 +1 206 XXX XX XX) |
|國際|國際|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何數位模式的路由 |

  > [!NOTE]
  > - 語音路由策略中的 PSTN 使用順序至關重要。 使用方式會以順序進行，如果第一個使用方式找到相符專案，則永遠不會評估其他使用量。 「國際」PSTN 使用量必須放在「美國和加拿大」PSTN 使用量之後。 若要變更 PSTN 使用順序，請執行 `Set-CSOnlineVoiceRoutingPolicy` 命令。 <br/>例如，若要先將「美國和加拿大」和「國際」第二個訂單變更為反向循序執行：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 系統會自動指派「其他 +1」和「國際」語音路由的優先順序。 只要優先順序低於 "Redmond 1" 和 "Redmond 2"，就無所謂。

## <a name="example-2-configuration-steps"></a>範例 2：組組步驟

下列範例顯示如何：

1. 建立稱為國際的新 PSTN 使用方式。
2. 建立稱為國際的新語音路由。
3. 建立稱為無限制的語音路由策略。
4. 將策略指派給使用者 John Woods。

您可以使用 Microsoft [Teams 系統管理中心或](#admincenterexample2) [PowerShell](#powershellexample2) 來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟 1：建立「國際」PSTN 使用方式

1. 在 Microsoft Teams 系統管理中心的左側導航中，前往 **[語音** 直接路由>，然後在右上角選取 [  >  ******管理 PSTN 使用記錄**> 。
2. 按一下 **[新增，** 輸入 **國際**，然後按一下 **[Apply.**

#### <a name="step-2-create-the-international-voice-route"></a>步驟 2：建立「國際」語音路由

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **直接路由**，然後選取 **語音路由定位** 點。
2. 按一下 **[新增**，輸入「國際」做為名稱，然後新增描述。
3. 將優先順序設為 4，然後將撥號號碼模式設定為 \d+。
4. 在 **註冊的 SBC (選**) 下，按一下 [新增 **SBCs，** 選取 sbc2.contoso.biz 並 sbc5.contoso.biz，然後按一下 [ **申請**。
5. 在 **[PSTN 使用量** 記錄 (選) 中，按一下 [新增 **PSTN** 使用量，選取 「國際」PSTN 使用記錄，然後按一下 **[Apply.**
6. 按一下 [儲存]。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步驟 3：建立名為「無限制」的語音路由策略，並新增「美國和加拿大」和「國際」PSTN 使用方式至該政策

「美國和加拿大」的 PSTN 使用方式會在此語音路由政策中重複使用，以保留特殊處理，以撥打「+1 425 XXX XX XX"和「+1 206 XXX XX XX"作為當地或內部部署通話。

1. 在 Microsoft Teams 系統管理中心的左側導航中，前往 **[**  >  **語音語音路由規則**，然後按一下 [**新增**> 。
2. 輸入 **No Restrictions** 做為名稱，然後新增描述。
3. 在 **PSTN 使用量記錄下**，按一下 [ **新增 PSTN 使用量**，選取 「美國和加拿大」PSTN 使用記錄，然後選取 「國際」PSTN 使用記錄。 按一下 **[Apply.**

    記下 PSTN 使用順序：

    - 如果撥打的號碼是「+1 425 XXX XX XX"，且此範例中的使用方式設定為「+1 425 XXX XX」，則通話會遵循「美國和加拿大」使用方式所設定路由，並套用特殊路由邏輯。 也就是說，先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由通話，sbc3.contoso.biz sbc4.contoso.biz 路由。

    - 如果 「國際」PSTN 使用量在 「美國和加拿大」之前，撥打 +1 425 XXX XX XX 會路由至 sbc2.contoso.biz sbc5.contoso.biz 作為路由邏輯的一部分。

4. 按一下 [儲存]。

若要深入瞭解，請參閱管理 [語音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步驟 4：將語音路由策略指派給名為 John Woods 的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 按一下 **[政策**」，然後按一下 [ **已指派之策略>** 旁的 [ **編輯**> 。
3. 在 **[語音路由策略>** 下，選取 [無限制」 政策，然後按一下 [ **儲存**。

結果是，適用于 John Woods 通話的語音原則不受限制，而且會遵循適用于美國、加拿大及國際通話的通話路由邏輯。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟 1：建立「國際」PSTN 使用方式

在商務用 Skype Online 中的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步驟 2：建立名為「國際」的新語音路由

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

這會返回：

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步驟 3：建立名為「無限制」的語音路由策略

PSTN 使用方式「Redmond 1」和「Redmond」會在此語音路由策略中重複使用，以保留「+1 425 XXX XX XX"和「+1 206 XXX XX XX」號碼作為當地或內部部署通話的特殊處理。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

記下 PSTN 使用順序：

  - 如果撥打的號碼為「+1 425 XXX XX" 且使用方式設定為下列範例，則通話會遵循「美國和加拿大」使用方式所設定路由，並套用特殊路由邏輯。 也就是說，先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由通話，sbc3.contoso.biz sbc4.contoso.biz 路由。

  - 如果 「國際」PSTN 使用量在 「美國和加拿大」之前，撥打 +1 425 XXX XX XX 會路由至 sbc2.contoso.biz sbc5.contoso.biz 作為路由邏輯的一部分。 輸入命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

這會返回：

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>步驟 4：將語音路由策略指派給名為 John Woods 的使用者

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

然後使用命令驗證作業： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

這會返回：

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

結果是，適用于 John Woods 通話的語音原則不受限制，而且會遵循適用于美國、加拿大及國際通話的通話路由邏輯。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
