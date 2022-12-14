---
title: 設定 Teams Microsoft自動語音應答
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: 瞭解如何在 teams 中設定和管理自動語音應答Microsoft。
ms.openlocfilehash: 0acdbacb9899184aaf21003193d62b3dcc4eab3a
ms.sourcegitcommit: 81b3403a1a77ba202690c2d88bd8d1d5257048e5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2022
ms.locfileid: "69379359"
---
# <a name="set-up-an-auto-attendant"></a>設定自動語音應答

自動語音應答可讓人員撥打電話給您的組織，並流覽功能表系統與正確的部門、通話佇列、人員或電信業者通話。 您可以透過 teams 系統管理中心或 PowerShell Microsoft為貴組織建立自動語音應答。

請確定您已閱讀 [規劃 Teams 自動語音應答和通話佇列](plan-auto-attendant-call-queue.md) ，並遵循 [開始步驟](plan-auto-attendant-call-queue.md#getting-started) ，然後再遵循本文中的程式。

自動語音應答可以根據來電者的輸入，將通話重新導向到下列其中一個目的地：

- **運算子** - 為自動語音應答定義的運算子。 定義運算子是選用的。 運算子可以定義為此清單中的其他任何目的地。
- **組織中的** 人員- 組織中可接聽語音通話的人員。 此人可以是線上使用者或使用商務用 Skype Server裝載于內部部署的使用者。
- **語音應用程式** - 另一個自動語音應答或通話佇列。  (選擇此目的地時，選擇與自動語音應答或通話佇列相關聯的資源帳戶。) 
- **語音信箱**- 與您指定Microsoft 365 群組相關聯的語音信箱。 您可以選擇是否要語音信箱轉譯，以及「請在鈴聲後面留下訊息」。 系統提示。
  - 在 M365 管理員中心為您指定的Microsoft 365 群組啟用「讓組織外部的人員傳送電子郵件給此小組」。
- **外部電話號碼** - 任何電話號碼。 請參閱 [外部傳輸技術詳細資料](create-a-phone-system-auto-attendant.md?tabs=general-info#external-phone-number-transfers---technical-details)。
- **公告 (音訊檔案)** - 播放音訊檔案。 您上傳儲存為音訊的錄製公告訊息。WAV、.MP3 或 。WMA 格式。 錄製不得大於 5 MB。 系統會播放公告，然後返回自動語音應答功能表。
- **宣告 (輸入)** - 輸入訊息。 您要讓系統讀取的文字。 您最多可以輸入 1000 個字元。 系統會播放公告，然後返回自動語音應答功能表。

> [!NOTE]
> 將通話重新導向至 **組織中的人員** 時，該人員必須具備語音功能。 如需啟用語音的詳細資訊，請參閱 [指派 Teams 附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
>
> 雖然定義 **運** 算符是選用的，但建議您使用運算子。 如果因為刪除使用者或共用語音信箱帳戶而導致自動語音應答設定發生錯誤，自動語音應答會將電話重新導向至電信業者。 如果未定義電信業者，自動語音應答會捨棄通話。

## <a name="whats-new-for-auto-attendants-in-the-past-6-months"></a>過去 6 個月自動語音應答的新功能
 
 - 9 月 - 現在可使用 [**播放] 功能表選項** 來使用 [通話流程]、[下班後通話流程] 和 [假日期間通話流程] 的 [**強制聆聽**] 選項。
 - 8 月 - [通話流程] 中的 **[播放] 功能表選項** 、下班後通話流程和假日期間的通話流程現在支援 \* (星號) ， (\# 井) 鍵。
 - 7 月 - 假日期間的通話流程現在支援 **[播放] 功能表選項**。
 
## <a name="steps-to-create-an-auto-attendant"></a>建立自動語音應答的步驟
新增自動語音應答的步驟如下：

1. 設定一般資訊。
1. 設定基本通話流程。
1. 設定下班後通話流程。
1. 設定假日通話流量。
1. 設定撥號範圍。
1. 設定資源帳戶。

本文概述的步驟是使用 Teams 系統管理中心建立自動語音應答。 如需 **使用 PowerShell 建立自動語音應答的** 指示，請參閱 [使用 PowerShell Cmdlet 建立自動語音應答](create-a-phone-system-auto-attendant-via-cmdlets.md)。

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>請依照下列步驟設定自動語音應答

# <a name="step-1-general-info"></a>[步驟 1：一般資訊](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>步驟 1：設定自動語音應答的一般資訊

若要設定自動語音應答，請在 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)展開 **[語音**]，選取 [ **自動語音應答**]，然後選取 [ **新增]**。

1. 在頂端的方塊中輸入自動語音應答的名稱。

2. 若要指定運算子，請指定撥打電話給電信業者的目的地。 此指定為選用，但建議使用。 設定 **運算** 符選項，允許來電者分隔功能表，並與指定的人員通話。

3. 指定此自動語音應答的時區。 如果您為下班 [後建立個別的通話流程](?tabs=after-hours)，則時區會用於計算上班時間。

4. 指定此自動語音應答 [的支援語言](create-a-phone-system-auto-attendant-languages.md) 。 這是系統產生的語音提示所用的語言。

5. 選擇您是否要啟用語音輸入。 啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。 例如，來電者可以說「一」來選取對應到按鍵 1 的功能表選項，或是說「銷售」來選取名為「銷售」的功能表選項。

   > [!NOTE]
   > 如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。

設定自動語音應答的一般資訊之後，請選取 [ **下一步]**。

# <a name="step-2-basic-call-flow"></a>[步驟 2：基本通話流程](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>步驟 2：設定基本通話流程

### <a name="set-a-greeting"></a>設定問候語

- 如果您選取 **[播放音訊檔案** ]，您可以使用 **[上傳檔案]** 按鈕上傳儲存為音訊的錄製問候語訊息。WAV、.MP3 或 。WMA 格式。 錄製不得大於 5 MB。

- 如果您選取 **[輸入問候語訊息** ]，系統會在自動語音應答接聽電話時讀出您輸入 (最多 1000 個字元) 文字。

### <a name="route-the-call"></a>路由通話

- 如果您選取 **[中斷連線**]，自動語音應答會掛斷通話。
- 如果您選取 **[重新導向通話**]，您可以選擇其中一個呼叫路由目的地。
- 如果您選取 [ **播放] 功能表選項**，可以選擇 **[播放音訊檔案]** 或 [ **在問候語訊息中輸入** ]，然後選擇功能表選項和目錄搜尋。

#### <a name="play-menu-options"></a>[播放] 功能表選項

*新增 - 可以啟用強制聆聽選項，讓來電者在選取前必須先聆聽所有功能表選項。* 
*新增 - \* (星號) 和 \# (磅) 鍵現在可用於功能表選項中*。

如需撥號選項，請將電話鍵臺上的 0-9 按鍵指派給其中一個通話路由目的地。  (星號) 和 \# (井字型大小) 按鍵 \* 是由系統保留，無法重新指派。 按下其中一個按鍵將會重複目前的功能表。

> [!NOTE]
> # 鍵只會備份到最新的自動語音應答。 一旦邊界劃過新的自動語音應答，#鍵將無法帶您前往上一個語音應答。

按鍵對應不一定為連續。 您可以建立一個功能表，其中按鍵 0、1 和 3 對應至選項，而數位 2 鍵則不會使用。

如果您已設定零鍵，建議您將零鍵對應到運算子。 如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。

針對每個功能表選項，指定下列設定：

- **撥號鍵** - 可存取此選項之電話鍵臺上的按鍵。 如果有語音輸入可用，來電者也可以說出此號碼來存取選項。

- **語音命令** ： 定義如果已啟用語音輸入，來電者可以授與這個選項存取的語音命令。 它可以包含多個字，例如「客戶服務」或「營運和理由」。 例如，來電者可以按 2，說「兩個」，或說「銷售」，選取對應到兩個按鍵的選項。 此文字也會透過服務確認提示的語音轉換文字呈現，可能類似「將您的通話轉移至銷售」。

- **重新導向至** - 來電者選擇此選項時所使用的通話路由目的地。 如果您要重新導向至自動語音應答或通話佇列，請選擇與其相關聯的資源帳戶。

##### <a name="directory-search"></a>目錄搜尋

如果您將撥號鍵指派給目的地，建議您選擇 [目錄 **] 搜尋****的 [無**]。 如果來電者嘗試使用指派給特定目的地的按鍵撥打名稱或分機，則在完成名稱或分機輸入之前，可能會意外路由到目的地。 建議您為目錄搜尋建立個別的自動語音應答，並使用撥號鍵將主要自動語音應答連結至該自動語音應答。

如果您未指派撥號鍵，請選擇目錄 **搜尋** 的選項。

**依名稱撥號** - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵臺上輸入。 任何線上使用者或任何使用 商務用 Skype Server 裝載于內部部署的使用者，都是合格的使用者，可以使用 Dial 依名稱找到。

**依分機撥號** - 如果您啟用此選項，來電者可以撥打組織中的使用者的擴充功能來與使用者聯繫。 任何線上使用者或任何使用 商務用 Skype Server 裝載于內部部署的使用者，都是符合資格的使用者，可以透過 **擴充功能找到 Dial**。  (您可以在 [ [撥號](?tabs=dial-scope) 範圍] 頁面上設定誰不包含在目錄中。) 

> [!NOTE]
> 如果您想要同時使用 **[依名稱撥號** ] 和 [ **依擴充功能撥號** ] 功能，可以指派主自動語音應答上的撥號鍵，讓自動語音應答能夠 **使用 [依名稱撥號]**。 在該自動語音應答中，您可以指派 1 個按鍵 (，其中沒有與它相關聯的字母，) 連線到 **擴充功能** 自動語音應答的 Dial。

如需詳細資訊，請參閱 [Dial 和語音參照](dial-voice-reference.md)。

設定基本通話流程選項後，請選取 [ **下一步]**。

# <a name="step-3-after-hours-call-flow"></a>[步驟 3：下班後通話流程](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>步驟 3：設定數小時後的通話流程 (選擇性) 

您可以為每個自動語音應答設定上班時間。

- 如果沒有設定上班時間，則會將一天中的所有天和所有時數視為上班時間，因為預設會設定 24/7 排程。
- 上班時間可以設定為一天當中的休息時間，而所有未設為上班時間的時數，都視為下班後。
- 您可以針對下班後設定不同的來電處理選項和問候語。

根據您設定自動語音應答和通話佇列的設定方式而定，您可能只需要指定自動語音應答與直接電話號碼的下班後通話路由。

如果您想要為下班後來電者個別路由通話，請指定每天的上班時間。

1. 在表格中的平日旁邊，調整 [ **開始** 時間] 和 [ **結束時間]** 。
1. 如有需要，請選取 **[新增時間** ]，指定指定某一天的多組時數，例如指定午餐時間。
1. 選擇數小時後的來電路由選項。 在數小時之後，也可以使用相同的一般通話流程選項。

新增下班後通話流程後，請選取 [ **下一步]**。

# <a name="step-4-holiday-call-flow"></a>[步驟 4：假日通話流程](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>步驟 4：設定假日 (選擇性) 

您的自動語音應答可以為 [您所設定的每個假日提供](set-up-holidays-in-teams.md)通話流程。 您最多可以在每個自動語音應答中新增 20 組佳節。 每個假日集最多可以包含 10 個唯一的日期範圍。 在自動語音應答中新增的所有假日集中，假日日期都必須是唯一的。

*新增 - 可以啟用強制聆聽選項，讓來電者在選取前必須先聆聽所有功能表選項。* 
*新增 - \* (星號) 和 \# (磅) 鍵現在可用於功能表選項中。* 
*新增 - **[播放] 功能表選項** 現在可在假日通話流程中使用。*

1. 在 [假日通話設定] 頁面上，選取 [ **新增]**。

1. 輸入此佳節設定的名稱。

1. 從 [ **假日]** 下拉式清單中，選擇您要使用的假日。

1. 選擇您要使用的問候語類型。

1. 選擇您要中斷聯 **機** 或 **重新導向** 通話。

    1. 如果您選擇重新導向，請選擇通話的呼叫路由目的地。
    1. 如果您選擇播放功能表選項，請設定 [ **播放] 功能表選項**。

1. 選取 [儲存 **]**。

針對每一個額外的假日，視需要重複此程式。

新增所有佳節時段後，請選取 [ **下一步]**。

# <a name="step-5-dial-scope"></a>[步驟 5：撥號範圍](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>步驟 5：將撥號範圍設定 (選用) 

*撥號範圍* 會定義當來電者使用撥號依據名稱或撥號方式延伸時，哪些使用者可在目錄中使用。 [**所有線上使用者]** 的預設值包含貴組織中所有使用 商務用 Skype Server 的線上使用者或內部部署託管的使用者。

您可以在 [包含] 或 [**排除****] 底下** 選取 [**自訂使用者群組**]，然後選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 例如，您可能會想要將貴組織中的高階主管從撥號目錄中排除。

如果使用者同時在兩份清單中，則會從目錄中排除使用者。

> [!NOTE]
> 新使用者可能需要長達 36 小時的時間，才會在目錄中列出他們的名稱。

選取 **您的 [撥號範圍** ] 選項後，選取 [ **下一步]**。

# <a name="step-6-resource-accounts"></a>[步驟 6：資源帳戶](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>步驟 6： (選用) 設定資源帳戶

所有自動語音應答都必須有相關聯的資源帳戶。  第一層自動語音應答至少需要一個具有相關聯服務號碼的資源帳戶。 如有需要，您可以將多個資源帳戶指派給自動語音應答，每個帳戶都有個別的服務號碼。

若要新增資源帳戶，請選取 **[新增帳戶]** ，然後搜尋您要新增的帳戶。 選取 **[新增**]，然後選取 [ **新增]**。

新增資源帳戶後，請選取 [ **下一步]**。

如需詳細資訊，請參閱 [管理 Teams 資源帳戶](manage-resource-accounts.md) 。

---

## <a name="resources-for-complex-scenarios"></a>複雜案例的資源

### <a name="external-phone-number-transfers---technical-details"></a>外部電話號碼移轉 - 技術詳細資料

請參閱 [必要條件](plan-auto-attendant-call-queue.md#prerequisites) ，以允許自動語音應答在外部轉接來電。  另外：

- 對於具有 [通話方案授權](calling-plans-for-office-365.md) 或運算子 [聯](operator-connect-plan.md) 機號碼的資源帳戶，外部移轉電話號碼必須以 E.164 格式輸入 (+[country code][area code][電話號碼]) 。

- 對於具有Microsoft Teams 電話授權和直接路由線上語音路由原則的資源帳戶，外部移轉電話號碼格式取決於[會話框線控制器 (SBC) ](direct-routing-connect-the-sbc.md)設定。

顯示的輸出電話號碼如下所示：

- 針對通話方案和電信業者連線號碼，會顯示原始來電者的電話號碼。
- 如果是直接路由號碼，傳送的號碼是根據 SBC 上的 P-資訊識別 (一) 設定，如下所示：
  - 如果設為 [停用]，則會顯示原始來電者的電話號碼。 這是預設和建議的設定。
  - 如果設定為 [已啟用]，則會顯示資源帳戶電話號碼。

在商務用 Skype混合式環境中，若要將自動語音應答來電轉接至 PSTN，請建立新的內部部署使用者，並將來電轉接設定為 PSTN 號碼。 使用者必須啟用企業語音並指派語音原則。 若要深入瞭解，請參閱 [自動語音應答來電轉接至 PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

### <a name="auto-attendant-diagnostic-tool"></a>自動語音應答診斷工具

如果您是系統管理員，您可以使用下列診斷工具驗證自動語音應答是否能夠接聽來電：

1. 選取 **[執行測試]** 以在 Microsoft 365 系統管理中心填入診斷。

   > [!div class="nextstepaction"]
   > [執行測試：Teams 自動語音應答](https://aka.ms/TeamsAADiag)

2. 在 [執行] 診斷窗格中，在 [**使用者名稱] 或 [Email**] 欄位中輸入 [資源帳戶]，然後選取 [**執行測試]**。

3. 這些測試會識別導致自動語音應答無法接聽來電的租使用者、原則或資源帳戶設定，並提供修正已識別問題的步驟。

### <a name="related-topics"></a>相關主題

[以下是您透過 Teams Phone 取得的功能](./here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
