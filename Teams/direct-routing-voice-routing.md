---
title: 設定直接路由的呼叫路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用 Microsoft Direct Routing 設定通話路由。
ms.openlocfilehash: a7f80a71aa83e255efe81b82ce57026ed0749165
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046663"
---
# <a name="configure-call-routing-for-direct-routing"></a>設定直接路由的呼叫路由

本文說明如何設定直接路由的通話路由。 這是設定直接路由的下列步驟 3 步驟 3：

- 步驟 1. [將 SBC 與 Microsoft Phone System 連線並驗證連線](direct-routing-connect-the-sbc.md) 
- 步驟 2. [啟用使用者的直接路由、語音和語音信箱](direct-routing-enable-users.md)
- **步驟 3.設定通話路由** (本文) 
- 步驟 4. [將數位翻譯成替代格式](direct-routing-translate-numbers.md) 

如需設定直接路由所需所有步驟的相關資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="call-routing-overview"></a>通話路由概觀

Microsoft Phone System 的路由機制允許根據下列專案將通話傳送到特定會話框線控制器 (SBC) ： 

- 稱為數位模式 
- 呼叫號碼模式加上撥打電話的特定使用者
 
您可以將 SB 指定為作用中和備份。 當設定為作用中的 SBC 無法用於特定通話路由時，通話將會路由至備份 SBC。
 
通話路由由下列元素組成： 

- **通話路由原則** – 也稱為語音路由原則。 PSTN 使用量容器，可指派給使用者或多個使用者。 

- **PSTN 使用量** – 語音路由和 PSTN 使用量的容器，可在不同的語音路由原則中共用。 

- **語音路由** ： 號碼模式和一組線上 PSTN 閘道，用於撥打號碼符合模式的通話。

- **線上 PSTN 閘道** - 指向 SBC 的指標，也會儲存透過 SBC 撥打電話時所套用的設定，例如轉接 P-維護身分識別 (一個在一起，) 或慣用編解碼器;可新增至語音路由。

## <a name="voice-routing-policy-considerations"></a>語音路由原則考慮

如果使用者有通話方案授權，該使用者的撥出電話會自動透過 Microsoft 通話方案 PSTN 基礎結構路由。 如果您設定並指派線上語音路由原則給通話方案使用者，系統會檢查該使用者的撥出電話，以判斷撥號是否符合線上語音路由原則中定義的號碼模式。 如果有相符專案，通話會透過直接路由主幹路由路由傳送。 如果沒有相符的專案，通話會透過通話方案 PSTN 基礎結構路由。

> [!CAUTION]
> 如果您設定並套用全域 (組織的預設) 線上語音路由原則，貴組織中所有有語音功能的使用者都會繼承該原則，這可能會導致通話方案和電信業者連線使用者的 PSTN 通話不慎路由到直接路由主幹。 如果您不希望所有使用者都使用全域線上語音路由原則，請設定自訂的線上語音路由原則，並將它指派給個別語音使用者。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>範例 1：含一個 PSTN 使用量的語音路由

下圖顯示通話流程中語音路由原則的兩個範例。

**在左側) 上撥打 Flow 1 (：** 如果使用者撥打 +1 425 XXX XX XX 或 +1 206 XXX XX XX，通話會路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果無法使用 sbc1.contoso.biz 或 sbc2.contoso.biz，則會中斷通話。 

**在右側) 上撥打 Flow 2 (：** 如果使用者撥打 +1 425 XXX XX XX 或 +1 206 XXX XX XX，通話會先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果無法使用 SBC，將會嘗試優先順序較低的路由 (sbc3.contoso.biz 並 sbc4.contoso.biz) 。 如果沒有可用的 SBC，則會中斷通話。 

![顯示語音路由原則範例。](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在這兩個範例中，當語音路由被指派優先順序時，會隨機嘗試路由中的 SB。

  > [!NOTE]
  > 除非使用者也擁有 Microsoft 通話方案授權，否則在範例設定中，除了符合模式 +1 425 XXX XX XX 或 +1 206 XXX XX XX XX 的數位外，呼叫任何號碼都會中斷。 如果使用者有通話方案授權，通話會根據 Microsoft 通話方案的原則自動路由。 Microsoft 通話方案會自動套用為擁有 Microsoft 通話方案授權的所有使用者的最後一條路由，而且不需要額外的通話路由設定。

在下列圖表中所示的範例中，新增了一條語音路由，可將通話傳送給所有其他美國與加拿大號碼， (撥打至號碼模式 +1 XXX XXX XX XX) 的通話。

![顯示含有第三條路由的語音路由原則。](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

對於所有其他通話，如果使用者同時擁有 Microsoft 電話系統 (和 Microsoft 通話方案) 的授權，則會使用自動路由。 如果沒有任何專案符合系統管理員建立的線上語音路由中的號碼模式，則通話會透過 Microsoft 通話方案路由。 如果使用者只有 Microsoft Phone System，則會因為沒有相符的規則而中斷通話。

  > [!NOTE]
  > 在此情況下，路由 「Other +1」 的優先順序值沒有作用，因為只有一個路由符合模式 +1 XXX XXX XX XX。 如果使用者撥打 +1 324 567 89 89，且 sbc5.contoso.biz 和 sbc6.contoso.biz 都無法使用，則會中斷通話。

下表摘要列出使用三種語音路由的設定。 在此範例中，這三條路由都屬於相同的 PSTN 使用量，「美國和加拿大」。  所有路由都與「美國和加拿大」PSTN 使用量相關聯，而 PSTN 使用量則與「僅限美國」語音路由原則相關聯。

|**PSTN 使用量**|**語音路由**|**數位模式**|**Priority (優先順序)**|**Sbc**|**描述**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|「Redmond 1」|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|稱為數位 +1 425 XXX XX XX 或 +1 206 XXX XX XX 的使用中路由|
|美國和加拿大|「Redmond 2」|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|稱為數位 +1 425 XXX XX XX 或 +1 206 XXX XX XX 的備份路由|
|美國和加拿大|「Other +1」|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|除了 +1 425 XXX XX XX 或 +1 206 XXX XX XX (外，其他號碼的路徑 +1 XXX XXX XX XX) |
|||||||

## <a name="example-1-configuration-steps"></a>範例 1：設定步驟

下列範例示範如何：

1. 建立單一 PSTN 使用量。
2. 設定三條語音路由。
3. 建立語音路由原則。
4. 將原則指派給名稱為 Low 的使用者。

您可以使用 [Microsoft Teams 系統管理中心](#admincenterexample1) 或 [PowerShell](#powershellexample1) 來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟 1：建立「美國和加拿大」PSTN 使用量

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[語音**  >  **直接路由**]，然後在右上角選取 **[管理 PSTN 使用記錄]**。
2. 按一下 **[新增**]，輸入 **美國和加拿大**，然後按一下 [ **套用]**。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟 2： (Redmond 1、Redmond 2 和 Other +1 建立三條語音路由) 

下列步驟說明如何建立語音路由。 使用這些步驟使用先前表格中所述的設定，為本範例建立名為 Redmond 1、Redmond 2 和 Other +1 的三條語音路由。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[語音**  >  **直接路由**]，然後選取 [**語音路由**] 索引標籤。
2. 按一下 **[新增**]，然後輸入語音路由的名稱和描述。
3. 設定優先順序並指定撥號號碼模式。
4. 若要使用語音路由註冊 SBC，請在 **已註冊的 SBC (選擇性)** 下，按一下 [ **新增 SBC**]，選取您要註冊的 SBC，然後按一下 [ **套用]**。
5. 若要新增 PSTN 使用記錄，請 **在 [PSTN 使用記錄] 底下 (選擇性)**，按一下 [ **新增 PSTN 使用量**]，選取您要新增的 PSTN 記錄，然後按一下 [ **套用]**。
6. 按一下 [儲存]。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟 3：建立名為「僅限美國」的語音路由原則，並將「美國和加拿大」PSTN 使用量新增至原則

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **語音**  >  **路由原則**，然後按一下 [**新增]**。
2. 輸入 **US 僅** 做為名稱，並新增描述。
3. 在 **[PSTN 使用記錄**] 底下，按一下 [ **新增 PSTN 使用量**]，選取 [美國和加拿大] PSTN 使用記錄，然後按一下 [ **套用]**。
4. 按一下 [儲存]。

若要深入瞭解，請參閱 [管理語音路由原則](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟 4：將語音路由原則指派給名稱為「低」的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 按一下 **[原則**]，然後在 [ **指定** 的原則] 旁邊，按一下 [ **編輯]**。
3. 在 **[語音路由原則**] 底下，選取 [僅限美國] 原則，然後按一下 [ **儲存]**。

若要深入瞭解，請參閱 [管理語音路由原則](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步驟 1：建立「美國和加拿大」PSTN 使用量

在 商務用 Skype Online 的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

請確認使用量是透過輸入來建立：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

這會傳回可能被截斷的名稱清單：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

下列範例顯示執行 PowerShell 命令以顯示全名的結果 `(Get-CSOnlinePSTNUsage).usage` ， (未截斷) ：

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步驟 2： (Redmond 1、Redmond 2 和 Other +1 建立三條語音路由) 

若要建立 「Redmond 1」 路由，請在 商務用 Skype Online 的 PowerShell 會話中輸入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

這會傳回：

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
  > 確認 NumberPattern 屬性中的正則運算式是有效的運算式。 您可以使用此網站進行測試： [https://www.regexpal.com](https://www.regexpal.com)

在某些情況下，必須將所有通話路由至相同的 SBC;use -NumberPattern 「.*」

將所有通話路由到同一個 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用選項執行 PowerShell 命令，確認您已正確設定路線 `Get-CSOnlineVoiceRoute` ，如下所示：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
這應該會傳回：

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

在範例中，路由「Other +1」 會自動指派優先順序 4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步驟 3：建立名為「僅限美國」的語音路由原則，並將「美國和加拿大」PSTN 使用量新增至原則

在 商務用 Skype Online 的 PowerShell 會話中，輸入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此範例中會顯示結果：

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步驟 4：將語音路由原則指派給名稱為「低」的使用者

在 商務用 Skype Online 的 PowerShell 會話中，輸入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

輸入此命令以驗證原則指派：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

命令會傳回下列專案：

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>範例 2：具有多個 PSTN 使用量的語音路由

在範例 1 中建立的語音路由原則只允許撥打美國和加拿大的電話號碼，除非 Microsoft 通話方案授權也指派給使用者。

在以下範例中，您可以建立「無限制」語音路由原則。 原則會重複使用範例 1 中建立的「美國和加拿大」PSTN 使用量，以及新的「國際」PSTN 使用量。 此原則會將所有其他通話路由至 SBC sbc2.contoso.biz 和 sbc5.contoso.biz。

顯示的範例會將「美國唯一原則」指派給使用者「最低」，而「無限制」原則則指派給使用者 John Woods，讓路由發生如下：

- Low – 僅限美國原則。  通話僅允許美國和加拿大號碼撥打。 撥打到 Redmond 號碼範圍時，必須使用特定的 SBC 集。 除非將通話方案授權指派給使用者，否則不會路由非美國號碼。

- John Woods – 國際原則。  通話可以撥打任何號碼。 撥打到 Redmond 號碼範圍時，必須使用特定的 SBC 集。 非美國號碼將會使用 sbc2.contoso.biz 和 sbc5.contoso.biz 路由。

![顯示指派給使用者 Low 的語音路由原則。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

對於所有其他通話，如果使用者同時擁有 Microsoft 電話系統 (和 Microsoft 通話方案) 的授權，則會使用自動路由。 如果沒有任何專案符合系統管理員建立的線上語音路由中的號碼模式，則會使用 Microsoft 通話方案路由來電。  如果使用者只有 Microsoft Phone System，則會因為沒有相符規則而中斷通話。

![顯示指派給使用者 John Woods 的語音路由原則。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表摘要列出路由原則「無限制」使用方式指定和語音路由。 

| PSTN 使用量 | 語音路由 | 數位模式 | Priority (優先順序) | Sbc | 描述 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|美國和加拿大|「Redmond 1」|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|來電者號碼的使用中路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美國和加拿大|「Redmond 2」|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|來電者號碼的備份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美國和加拿大|「Other +1」|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|來電者號碼 +1 XXX XXX XX XX XX (除了 +1 425 XXX XX XX 或 +1 206 XXX XX XX) |
|國際|國際|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何數位模式的路由 |

  > [!NOTE]
  > - 語音路由原則中的 PSTN 使用量順序至關重要。 這些使用方式會依順序套用，如果在第一個使用中找到相符專案，則不會評估其他使用量。 「國際」PSTN 使用量必須放在「美國和加拿大」PSTN 使用量之後。 若要變更 PSTN 使用順序，請執行 `Set-CSOnlineVoiceRoutingPolicy` 命令。 <br/>例如，若要將「美國和加拿大」第一個及「國際」第二個順序變更為反向循序執行：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 系統會自動指派「其他 +1」和「國際」語音路由的優先順序。 只要其優先順序低於 「Redmond 1」 和 「Redmond 2」 都沒關係。

## <a name="example-2-configuration-steps"></a>範例 2：設定步驟

下列範例示範如何：

1. 建立稱為國際的新 PSTN 使用量。
2. 建立一條稱為「國際」的新語音路由。
3. 建立稱為無限制的語音路由原則。
4. 將原則指派給使用者 John Woods。

您可以使用 [Microsoft Teams 系統管理中心](#admincenterexample2) 或 [PowerShell](#powershellexample2) 來執行這些步驟。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟 1：建立「國際」PSTN 使用量

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[語音**  >  **直接路由**]，然後在右上角選取 **[管理 PSTN 使用記錄]**。
2. 按一下 **[新增**]，輸入 **[國際**]，然後按一下 [ **套用]**。

#### <a name="step-2-create-the-international-voice-route"></a>步驟 2：建立「國際」語音路由

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[語音**  >  **直接路由**]，然後選取 [**語音路由**] 索引標籤。
2. 按一下 **[新增**]，輸入「國際」做為名稱，然後新增描述。
3. 將優先順序設為 4，然後將撥號號碼模式設定為 \d+。
4. 在 **已註冊 (選用) 的 [SBC**] 底下，按一下 [ **新增 SBC**]，選取 [sbc2.contoso.biz 並 sbc5.contoso.biz]，然後按一下 [ **套用]**。
5. 在 **[PSTN 使用記錄 (選擇性)**] 底下，按一下 [ **新增 PSTN 使用量**]，選取 [國際] PSTN 使用記錄，然後按一下 [ **套用]**。
6. 按一下 [儲存]。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步驟 3：建立名為「無限制」的語音路由原則，並將「美國和加拿大」及「國際」PSTN 使用量新增至原則

此語音路由原則會重複使用 PSTN 使用量 「US and Canada」，以保留撥打 「+1 425 XXX XX XX」 和 「+1 206 XXX XX XX」 作為當地或內部部署通話的通話特殊處理方式。

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **語音**  >  **路由原則**，然後按一下 [**新增]**。
2. 輸入 **無限制** 做為名稱，並新增描述。
3. 在 **[PSTN 使用記錄**] 底下，按一下 [ **新增 PSTN 使用量**]，選取 [美國和加拿大] PSTN 使用記錄，然後選取 [國際] PSTN 使用記錄。 按一下 [ **套用]**。

    記下 PSTN 使用量的順序：

    - 如果撥打電話給號碼 「+1 425 XXX XX XX」，且使用狀況設定為本範例中所示，通話會遵循「美國和加拿大」使用方式中設定的路由，並套用特殊的路由邏輯。 也就是說，通話會先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由，然後 sbc3.contoso.biz 並 sbc4.contoso.biz 做為備份路由。

    - 如果「國際」PSTN 使用量在「美國和加拿大」之前，則呼叫 +1 425 XXX XX XX 會路由至 sbc2.contoso.biz，並 sbc5.contoso.biz 做為路由邏輯的一部分。

4. 按一下 [儲存]。

若要深入瞭解，請參閱 [管理語音路由原則](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步驟 4：將語音路由原則指派給名為 John Woods 的使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 按一下 **[原則**]，然後在 [ **指定** 的原則] 旁邊，按一下 [ **編輯]**。
3. 在 **[語音路由原則**] 底下，選取 [無限制] 原則，然後按一下 [ **儲存]**。

結果發現，套用至 John Woods 通話的語音原則不受限制，且會遵循美國、加拿大及國際電話的通話路由邏輯。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步驟 1：建立「國際」PSTN 使用量

在 商務用 Skype Online 的遠端 PowerShell 會話中，輸入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步驟 2：建立名為「國際」的新語音路由

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

這會傳回：

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步驟 3：建立名為「無限制」的語音路由原則

此語音路由原則會重複使用 PSTN 使用量 「Redmond 1」 和 「Redmond」，以保留撥打 「+1 425 XXX XX XX」 和 「+1 206 XXX XX XX」 做為本機或內部部署通話的通話特殊處理方式。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

記下 PSTN 使用量的順序：

  - 如果撥打電話給號碼 「+1 425 XXX XX XX XX」，且使用方式設定如下列範例，則通話會遵循「美國和加拿大」使用方式中設定的路由，並套用特殊的路由邏輯。 也就是說，通話會先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由，然後 sbc3.contoso.biz 並 sbc4.contoso.biz 做為備份路由。

  - 如果「國際」PSTN 使用量在「美國和加拿大」之前，則呼叫 +1 425 XXX XX XX 會路由至 sbc2.contoso.biz，並 sbc5.contoso.biz 做為路由邏輯的一部分。 輸入命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

這會傳回：

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>步驟 4：將語音路由原則指派給名為 John Woods 的使用者

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

然後使用命令驗證作業： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

這會傳回：

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

結果得出了針對 John Woods 通話所套用的語音原則不受限制，且會遵循美國、加拿大及國際電話可用的通話路由邏輯。

## <a name="run-a-self-diagnostics-tool"></a>執行自我診斷工具

Microsoft 365 系統管理員使用者可以存取可以在租使用者內執行的診斷，以驗證使用者已正確設定直接路由。 

> [!NOTE]
>此功能不適用於 Microsoft 365 Government、由世紀互聯提供的 Microsoft 365 或 Microsoft 365 Germany。

選取 [執行測試]，如下所示。 這會在 Microsoft 365 系統管理 中心填入診斷。
>> [!div class="nextstepaction"]
>> [執行測試：Teams 直接路由](https://aka.ms/TeamsDirectRoutingDiag)

此診斷會執行大量驗證。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
