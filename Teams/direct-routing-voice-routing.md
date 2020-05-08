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
description: 瞭解如何使用 Microsoft Phone 系統 Direct 路由設定語音路由。
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159010"
---
# <a name="configure-voice-routing-for-direct-routing"></a>設定直接路由的語音路由

本文說明如何設定手機系統 Direct 路由的語音路由。  以下是設定直接路由的步驟3：

- 步驟1。 [將 SBC 與 Microsoft Phone 系統連接並驗證連接](direct-routing-connect-the-sbc.md) 
- 步驟2。 [允許使用者使用直接路由、語音及語音信箱](direct-routing-enable-users.md)
- **步驟3。設定語音路由**（本文）
- 步驟4。 [將數位轉換成替換格式](direct-routing-translate-numbers.md) 

如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定[直接路由](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>語音路由概覽

Microsoft Phone 系統有一個路由機制，可讓您根據下列情況，將呼叫傳送到特定的會話邊界控制器（SBC）： 

- [已呼叫的號碼] 模式 
- 呼叫的號碼模式加上呼叫的特定使用者
 
SBCs 可以指定為 [作用中] 和 [備份]。 當設定為作用中的 SBC 無法用於特定呼叫路由時，該呼叫將會路由至 backup SBC。
 
[語音路由] 是由下列元素所組成： 

- **語音路由策略**– PSTN 用途的容器，可指派給使用者或多位使用者。 

- **PSTN 用途**-語音路由和 PSTN 用途的容器，可在不同的語音路由策略中共用。 

- **語音路由**：一種數位模式，以及一組線上 PSTN 閘道，用於撥打電話號碼符合模式的呼叫。

- **線上 PSTN 閘道**-指向 sbc 的指標，也會儲存在 sbc 中發出呼叫時所套用的設定，例如轉寄 P 斷言身分識別（PAI）或首選編解碼器;可以新增到語音路由。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>範例1：使用單一 PSTN 使用的語音路由

下圖顯示通話流程中的兩個語音路由策略範例。

**通話流程1（在左邊）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話會路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都無法使用，就會掛斷通話。 

**通話流程2（右側）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話就會先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果沒有可用的 SBC，則會嘗試使用較低優先順序的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。 如果沒有任何 SBCs 可用，就會中斷通話。 

![顯示語音路由策略範例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在這兩個範例中，雖然語音路由是指派優先順序，但路由中的 SBCs 會以隨機順序嘗試。

  > [!NOTE]
  > 除非使用者也有 Microsoft 通話方案授權，否則呼叫範例設定中的 [除了模式 + 1 425 XXX xx xx] 或 [+ 1 206 XXX xx xx] 以外的任何號碼。 如果使用者有通話方案授權，通話會根據 Microsoft 通話方案的原則自動傳送。 Microsoft 通話方案會自動套用為所有擁有 Microsoft 通話方案授權的使用者，而且不需要額外的呼叫路由設定。

在下圖所示的範例中，新增了語音信箱，以傳送來電給所有其他美國和加拿大的號碼（移至撥打電話號碼模式 + 1 XXX XXX XX XX 的通話）。

![顯示含有第三個路線的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

針對所有其他通話：

- 如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。 
- 如果沒有與管理員建立的線上語音路線中的數位模式相符，通話會透過 Microsoft 通話方案傳送。
- 如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。

  > [!NOTE]
  > 在此情況下，路由 "Other + 1" 的優先順序值不重要，因為只有一個路由符合模式 + 1 XXX XXX XXX xx。 如果使用者撥打電話給 + 1 324 567 89 89，且 sbc5.contoso.biz 和 sbc6.contoso.biz 都無法使用，通話就會斷撥。

下表摘要列出使用三個語音路由的配置。 在這個範例中，三個路由都是相同 PSTN 使用量（"美國及加拿大"）的一部分。  所有路由都與「美國和加拿大」 PSTN 使用關聯，而 PSTN 使用量則與「僅美國」語音路由策略相關聯。

|**PSTN 使用量**|**語音路線**|**數位模式**|**優先順序**|**SBC**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|呼叫號碼 + 1 425 XXX XX xx 美元或 + 1 206 XXX XX xx 的活動路由|
|美國和加拿大|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|呼叫號碼的備份路由 + 1 425 XXX XX XX or + 1 206 XXX XX xx|
|美國和加拿大|"Other + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼叫號碼的路由 + 1 XXX XXX XXX xx （除 + 1 425 XXX XX 或 + 1 206 XXX XX xx 以外）|
|||||||

## <a name="example-1-configuration-steps"></a>範例1：設定步驟

下列範例顯示如何：

1. 建立單一 PSTN 使用量。
2. 設定三個語音路由。
3. 建立語音路由策略。
4. 將原則指派給名為 Spencer Low 的使用者。

您可以使用[Microsoft 團隊系統管理中心](#admincenterexample1)或[PowerShell](#powershellexample1)來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟1：建立「美國和加拿大」 PSTN 使用量

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **直式路由**]，然後按一下右上角的 [**管理 PSTN 使用方式記錄**]。
2. 按一下 [**新增**]，輸入**美國和加拿大**，然後按一下 [套用 **]。**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟2：建立三個語音路線（雷蒙德1、雷德蒙2及其他 + 1）

下列步驟說明如何建立語音路線。 您可以使用這些步驟，透過舊版表格中所述的設定，為此範例建立三個名為 [雷蒙德 1]、[雷蒙德 2] 及 [其他 + 1] 的語音路由。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **直式路由**]，然後選取 [**語音路由**] 索引標籤。
2. 按一下 [**新增**]，然後輸入語音路線的名稱和描述。
3. 設定優先順序，並指定撥打的號碼模式。
4. 若要使用語音路由註冊 SBC，請在 **[半形註冊（選用）**] 底下，按一下 [**新增 sbcs**]，選取您要登記的 SBCs，然後按一下 [套用 **]。**
5. 若要新增 PSTN 使用記錄，請在 **[PSTN 使用記錄（選用）**] 底下，按一下 [**新增 PSTN 使用量**]，選取您要新增的 PSTN 記錄，**然後按一下 [** 套用]。
6. 按一下 [儲存]****。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟3：建立名為「僅限美國」的語音路由策略，並將「美國和加拿大」 PSTN 使用方式新增至原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **語音路由策略**]，然後按一下 [**新增**]。
2. **僅**以名稱輸入，並新增描述。
3. 在 [ **PSTN 使用記錄**] 底下，按一下 [**新增 PSTN 使用量**]，選取 [美國及加拿大] PSTN 使用方式記錄，然後按一下 [套用 **]。**
4. 按一下 [儲存]****。

若要深入瞭解，請參閱[管理語音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟4：將語音路由策略指派給名為 Spencer 低的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**語音路由策略**] 底下，選取 [僅限美國] 原則，然後按一下 [**儲存**]。

若要深入瞭解，請參閱[管理語音路由策略](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟1：建立「美國和加拿大」 PSTN 使用量

在商務用 Skype Online 的遠端 PowerShell 會話中，鍵入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

輸入以下內容以驗證是否已建立使用：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

這會傳回可能會被截斷的名稱清單：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

下列範例顯示執行`(Get-CSOnlinePSTNUsage).usage` Powershell 命令以顯示完整名稱的結果（不會被截斷）：

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟2：建立三個語音路線（雷蒙德1、雷德蒙2及其他 + 1）

若要在商務用 Skype Online 的 PowerShell 會話中建立「雷蒙德1」路線，請輸入：

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

在某些情況下，需要將所有呼叫路由至同一個 SBC;使用-NumberPattern ". *"

將所有呼叫路由至同一個 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用以下所示的選項，確認您是否已`Get-CSOnlineVoiceRoute`透過執行 PowerShell 命令來正確設定路由：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
應傳回的專案：
<pre>
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
</pre>

在這個範例中，「其他 + 1」路由會自動指派優先順序4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟3：建立名為「僅限美國」的語音路由策略，並將「美國和加拿大」 PSTN 使用方式新增至原則

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

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟4：將語音路由策略指派給名為 Spencer 低的使用者

在商務用 Skype Online 的 PowerShell 會話中，鍵入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

輸入以下命令以驗證原則指派：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

命令會傳回下列內容：
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>範例2：有多個 PSTN 用法的語音路由

在範例1中建立的語音路由策略只允許撥打美國和加拿大電話號碼，除非使用者也指派 Microsoft 通話方案授權。

在下列範例中，您可以建立「無限制」語音路由原則。 原則會重複使用範例1中建立的「美國和加拿大」 PSTN 使用量，以及新的「國際」 PSTN 用法。 此原則會將所有其他呼叫路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。

所顯示的範例會將 [僅限美國] 原則指派給使用者 Spencer 低，並將 [無限制] 原則指派給使用者 John 的使用，以便進行路由，如下所示：

- Spencer [低–美國] 原則。  通話只能在美國和加拿大號碼使用。 呼叫雷德蒙的數位範圍時，必須使用一組特定的半形。 除非指派給使用者的是通話方案授權，否則不會路由非美國數位。

- 約翰（張三）：國際原則。  允許通話至任何號碼。 呼叫雷德蒙的數位範圍時，必須使用一組特定的半形。 使用 sbc2.contoso.biz 和 sbc5.contoso.biz 來路由非美國數位。

![顯示指派給使用者 Spencer 低的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

針對所有其他通話，如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。 如果沒有與管理員建立的線上語音路由中的數位模式相符，就會使用 Microsoft 通話方案傳送通話。  如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。

![顯示指派給使用者 John 的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表摘要列出路由策略「無限制」的使用方式指派和語音路由。 

|**PSTN 使用量**|**語音路線**|**數位模式**|**優先順序**|**SBC**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被呼叫者編號的作用中路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx|
|美國和加拿大|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被呼叫者編號的備份路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx|
|美國和加拿大|"Other + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|被呼叫者的電話號碼 + 1 XXX XXX XX （不包括 + 1 425 XXX XX 或 + 1 206 XXX xx xx）|
|國際|國際|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何數位模式的路線 |

  > [!NOTE]
  > - 語音路由策略中的 PSTN 使用順序非常重要。 此用法會依順序套用，如果在第一個用法中找到一個相符專案，則永遠不會評估其他用法。 「國際」 PSTN 使用量必須放在「美國和加拿大」 PSTN 用法之後。 若要變更 PSTN 用法的順序，請執行`Set-CSOnlineVoiceRoutingPolicy`命令。 <br/>例如，若要將訂單從 "美國和加拿大" 先變更為 [國際 "，然後再執行相反順序：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 系統會自動指派「其他 + 1」和「國際」語音路由的優先順序。 只要其優先順序低於「雷蒙德1」和「雷蒙德2」，就不重要。

## <a name="example-2-configuration-steps"></a>範例2：設定步驟

下列範例顯示如何：

1. 建立名為「國際」的新 PSTN 用途。
2. 建立名為「國際」的新語音路由。
3. 建立稱為無限制的語音路由策略。
4. 將原則指派給使用者 John 的使用方式。

您可以使用[Microsoft 團隊系統管理中心](#admincenterexample2)或[PowerShell](#powershellexample2)來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟1：建立「國際」 PSTN 使用

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **直式路由**]，然後按一下右上角的 [**管理 PSTN 使用方式記錄**]。
2. 按一下 [**新增**]，輸入**國際**，然後按一下 [套用 **]。**

#### <a name="step-2-create-the-international-voice-route"></a>步驟2：建立「國際」語音路由

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **直式路由**]，然後選取 [**語音路由**] 索引標籤。
2. 按一下 [**新增**]，輸入「國際」作為名稱，然後新增描述。
3. 將 [優先順序] 設定為4，然後將 [撥入號碼] 模式設定為 [\d +]。
4. 在 **[半形註冊（選用）**] 底下，按一下 [**新增 sbcs**]，選取 [sbc2.contoso.biz 和 sbc5.contoso.biz]，**然後按一下 [** 套用]。
5. 在 **[PSTN 使用記錄（選用）**] 底下，按一下 [**新增 PSTN 使用量**]，選取「國際」 PSTN 使用記錄，然後按一下 [套用 **]。**
6. 按一下 [儲存]****。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步驟3：建立名為「無限制」的語音路由策略，並將「美國和加拿大」和「國際」 PSTN 用法新增至原則

在此語音路由策略中，會重複使用 PSTN 使用 "美國和加拿大"，以保留對號碼 "+ 1 425 XXX XX" 和 "+ 1 206 XXX XX" （作為本機或內部部署的呼叫）的特殊處理。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **語音路由策略**]，然後按一下 [**新增**]。
2. 輸入 [**無限制**] 作為名稱並新增描述。
3. 在 [ **PSTN 使用記錄**] 底下，按一下 [**新增 PSTN 使用量**]，選取「美國和加拿大」 pstn 使用記錄，然後選取「國際」 pstn 使用記錄。 按一下 **[** 套用]。

    請注意 PSTN 的使用順序：

    - 如果您在此範例中，將電話號碼 "+ 1 425 XXX XX XX" 設定為使用這種方式，則呼叫會遵循「美國和加拿大」使用量中的路由設定，並套用特殊路由邏輯。 也就是說，通話是使用 sbc1.contoso.biz 和 sbc2.contoso.biz 進行路由，然後 sbc3.contoso.biz 和 sbc4.contoso.biz 做為備份路由。

    - 如果「國際」 PSTN 使用量在「美國和加拿大」之前，則對 + 1 425 XXX XX 的呼叫會路由至 sbc2.contoso.biz 和 sbc5.contoso.biz，成為路由邏輯的一部分。

4. 按一下 [儲存]****。

若要深入瞭解，請參閱[管理語音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步驟4：將語音路由策略指派給名為 John 的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**語音路由策略**] 底下，選取 [無限制] 原則，然後按一下 [**儲存**]。

結果是，套用到 John 54777 通話的語音原則是不受限制的，將遵循可供美國、加拿大和國際電話使用的呼叫路由的邏輯。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟1：建立「國際」 PSTN 使用

在商務用 Skype Online 的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步驟2：建立名為「國際」的新語音路由

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步驟3：建立名為 "無限制" 的語音路由策略

在此語音路由原則中，PSTN 使用 "雷德蒙 1" 和 "雷德蒙" 會重複使用，以保留對號碼 "+ 1 425 XXX XX" 和 "+ 1 206 XXX XX" （作為本機或內部部署的呼叫）的特殊處理。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

請注意 PSTN 的使用順序：

  - 如果撥打的號碼是 "+ 1 425 XXX XX"，且使用下列範例所述的使用方式，則呼叫會遵循「美國和加拿大」用法中的路由設定，並套用特殊路由邏輯。 也就是說，通話是使用 sbc1.contoso.biz 和 sbc2.contoso.biz 進行路由，然後 sbc3.contoso.biz 和 sbc4.contoso.biz 做為備份路由。

  - 如果「國際」 PSTN 使用量在「美國和加拿大」之前，則對 + 1 425 XXX XX 的呼叫會路由至 sbc2.contoso.biz 和 sbc5.contoso.biz，成為路由邏輯的一部分。 輸入命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

返回：

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>步驟4：將語音路由策略指派給名為 John 的使用者

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
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

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
