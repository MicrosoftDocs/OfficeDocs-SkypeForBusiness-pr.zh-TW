---
title: 為 Microsoft Teams 設定自動語音應答
author: CarolynRowe
ms.author: crowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 瞭解如何在 Microsoft Teams 中為大型組織設定和測試自動語音應答。
ms.openlocfilehash: a0b50a83e54059dca68562c2140ece6253448dd0
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059094"
---
# <a name="set-up-an-auto-attendant"></a>設定自動語音應答

自動語音應答可讓人員撥打電話給您的組織，並流覽功能表系統與正確的部門、通話佇列、人員或電信業者通話。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 為貴組織建立自動語音應答。

> [!TIP]
> 本文適用于大型組織。 如果您的組織是小型企業，請改為閱讀 [設定自動語音應答 - 小型企業教學課程](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 。

請確定您已閱讀[規劃Teams自動語音應答和通話佇列](plan-auto-attendant-call-queue.md)，並遵循[開始步驟](plan-auto-attendant-call-queue.md#getting-started)，再依照本文中的程式進行。

自動語音應答可以根據來電者的輸入，將通話導向下列其中一個目的地： <a name="call-routing-options" ></a>

- **運算子** - 為自動語音應答定義的運算子。 定義運算子是選用的。 運算子可以定義為此清單中的其他任何目的地。
- **組織中的** 人員- 組織中可接聽語音通話的人員。 此人可以是線上使用者或使用商務用 Skype Server裝載于內部部署的使用者。
- **語音應用程式** - 另一個自動語音應答或通話佇列。  (選擇此目的地時，選擇與自動語音應答或通話佇列相關聯的資源帳戶。) 
- **語音信箱**- 與您指定之Microsoft 365群組相關聯的語音信箱。 您可以選擇是否要語音信箱轉譯，以及「請在鈴聲後面留下訊息」。 系統提示。
- **外部電話號碼** - 任何電話號碼。  (請參閱 [外部傳輸技術詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 資料) 。
- **公告 (音訊檔案)** - 播放音訊檔案。 您上傳儲存為音訊的錄製公告訊息。WAV、.MP3 或 。WMA 格式。 錄製不得大於 5 MB。 系統會播放公告，然後返回自動語音應答功能表。
- **宣告 (輸入)** - 輸入訊息。 您要讓系統讀取的文字。 您最多可以輸入 1000 個字元。 系統會播放公告，然後返回自動語音應答功能表。

當您設定自動語音應答時，系統會提示您在不同階段選擇其中一個選項。

若要設定自動語音應答，請在Teams系統管理中心展開 **[語音**]，選取 [**自動語音應答**]，然後選取 [**新增]**。

## <a name="video-demonstration"></a>視訊示範

這段影片示範如何在 Teams 中建立自動語音應答的基本範例。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>一般資訊

![名稱、運算子、時區、語言和語音輸入自動語音應答設定的螢幕擷取畫面。](media/auto-attendant-general-info-page-new.png)

1. 在頂端的方塊中輸入自動語音應答的名稱。

2. 若要指定運算子，請指定撥打電話給電信業者的目的地。 此指定為選用 (，但建議) 。 設定 **運算** 符選項，允許來電者分隔功能表，並與指定的人員通話。

3. 指定此自動語音應答的時區。 如果您為下班 [後建立個別的通話流程](#call-flow-for-after-hours)，則時區會用於計算上班時間。

4. 指定此自動語音應答 [的支援語言](create-a-phone-system-auto-attendant-languages.md) 。 這是系統產生的語音提示所用的語言。

5. 選擇您是否要啟用語音輸入。 啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。 例如，來電者可以說「一」來選取對應到按鍵 1 的功能表選項，或是說「銷售」來選取名為「銷售」的功能表選項。

   > [!NOTE]
   > 如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。

6. 選取 **[下一步]**。

## <a name="call-flow"></a>通話流程

![問候語訊息設定的螢幕擷取畫面。](media/auto-attendant-call-flow-greeting-message.png)

選擇當自動語音應答接聽電話時，是否要播放問候語。

如果您選取 **[播放音訊檔案**]，您可以使用 **[Upload檔案**] 按鈕上傳儲存為音訊的錄製問候語訊息。WAV、.MP3 或 。WMA 格式。 錄製不得大於 5 MB。

如果您選取 **[輸入問候語訊息** ]，系統會在自動語音應答接聽電話時讀出您輸入 (最多 1000 個字元) 文字。

![通話路由設定的螢幕擷取畫面。](media/auto-attendant-call-flow-route-call-message.png)

選擇您要路由通話的路由方式。

如果您選取 **[中斷連線**]，自動語音應答會掛斷通話。

如果您選取 **[重新導向通話**]，您可以選擇其中一個呼叫路由目的地。

如果您選取 [ **播放] 功能表選項**，可以選擇 **[播放音訊檔案]** 或 [ **在問候語訊息中輸入** ]，然後選擇功能表選項和目錄搜尋。

### <a name="menu-options"></a>功能表選項

![撥號鍵選項的螢幕擷取畫面。](media/auto-attendant-call-flow-menu-options-complete.png)

如需撥號選項，請將電話鍵臺上的 0-9 按鍵指派給其中一個通話路由目的地。  ( (星號) 和 \# (井) 按鍵 \* 是由系統保留，無法重新指派。 按下其中一個按鍵將會重複目前的功能表。) 

> [!NOTE]
> # 鍵只會備份到最新的自動語音應答。 一旦邊界劃過新的自動語音應答，#鍵將無法帶您前往上一個語音應答。

按鍵對應不一定為連續。 您可以建立一個功能表，其中按鍵 0、1 和 3 對應至選項，而數位 2 鍵則不會使用。

如果您已設定零鍵，建議您將零鍵對應到運算子。 如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。

針對每個功能表選項，指定下列設定：

- **撥號鍵** - 可存取此選項之電話鍵臺上的按鍵。 如果有語音輸入可用，來電者也可以說出此號碼來存取選項。

- **語音命令** ： 定義如果已啟用語音輸入，來電者可以授與這個選項存取的語音命令。 它可以包含多個字，例如「客戶服務」或「營運和理由」。 例如，來電者可以按 2，說「兩個」，或說「銷售」，選取對應到兩個按鍵的選項。 此文字也會透過服務確認提示的語音轉換文字呈現，可能類似「將您的通話轉移至銷售」。

- **重新導向至** - 來電者選擇此選項時所使用的通話路由目的地。 如果您要重新導向至自動語音應答或通話佇列，請選擇與其相關聯的資源帳戶。

### <a name="directory-search"></a>目錄搜尋

如果您將撥號鍵指派給目的地，建議您選擇 [目錄 **] 搜尋****的 [無**]。 如果來電者嘗試使用指派給特定目的地的按鍵撥打名稱或分機，則在完成名稱或分機輸入之前，可能會意外路由到目的地。 建議您為目錄搜尋建立個別的自動語音應答，並使用撥號鍵將主要自動語音應答連結至該自動語音應答。

如果您未指派撥號鍵，請選擇目錄 **搜尋** 的選項。

**依名稱撥號** - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵臺上輸入。 任何線上使用者或任何使用 商務用 Skype Server 裝載于內部部署的使用者，都是合格的使用者，可以使用 Dial 依名稱找到。  (您可以在 [ [撥號](#dial-scope) 範圍] 頁面上設定誰不包含在目錄中。) 

**依分機撥號** - 如果您啟用此選項，來電者可以撥打組織中的使用者的擴充功能來與使用者聯繫。 任何線上使用者或任何使用 商務用 Skype Server 裝載于內部部署的使用者，都是符合資格的使用者，可以透過 **擴充功能找到 Dial**。  (您可以在 [ [撥號](#dial-scope) 範圍] 頁面上設定誰不包含在目錄中。) 

您想要用於 Dial By Extension 的使用者必須將擴充功能指定為下列 Active Directory 中定義之其中一個手機屬性的一部分， (並透過Azure AD 連線) 或Azure Active Directory進行同步處理。  (如需詳細資訊，請參閱 [個別或大量新增使用者](/microsoft-365/admin/add-users/add-users) 。) 

- OfficePhone/TelephoneNumber (AD 和 Azure AD) 
- HomePhone (AD) 
- Mobile/MobilePhone (AD 和 Azure AD) 
- OtherTelephone (AD) 

在使用者電話號碼欄位中輸入擴充功能所需的格式可以是下列其中一種格式：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「+15555555678;ext=5678」
- 範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「+15555555678x5678」
- 範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「x5678」

您可以在[Microsoft 365 系統管理中心](https://admin.microsoft.com/)或[Azure Active Directory 系統管理中心](https://aad.portal.azure.com)中設定擴充功能。 自動語音應答和通話佇列最多可能需要 12 小時才能進行變更。

> [!NOTE]
> 如果您想要同時使用 **[依名稱撥號** ] 和 [ **依擴充功能撥號** ] 功能，可以指派主自動語音應答上的撥號鍵，讓自動語音應答能夠 **使用 [依名稱撥號]**。 在該自動語音應答中，您可以指派 1 個按鍵 (，其中沒有與它相關聯的字母，) 連線到 **擴充功能** 自動語音應答的 Dial。

如需詳細資訊，請參閱 [Dial 和語音參照](dial-voice-reference.md) 。

選取目錄 **搜尋** 選項後，選取 [ **下一步]**。

## <a name="call-flow-for-after-hours"></a>數小時後的通話流程

![日後和時間設定的螢幕擷取畫面。](media/auto-attendant-business-hours.png)

您可以為每個自動語音應答設定上班時間。 如果沒有設定上班時間，則會將一天中的所有天和所有時數視為上班時間，因為預設會設定 24/7 排程。 上班時間可以設定為一天當中的休息時間，而所有未設為上班時間的時數，都視為下班後。 您可以針對下班後設定不同的來電處理選項和問候語。

根據您設定自動語音應答和通話佇列的設定方式而定，您可能只需要指定自動語音應答與直接電話號碼的下班後通話路由。

如果您想要為下班後來電者個別路由通話，請指定每天的上班時間。 選取 **[新增時間** ]，指定指定某一天的多組時數，例如指定午餐時間。

指定上班時間之後，再選擇下班後的來電路由選項。 您可使用與上述指定之上班時間通話路由相同的選項。

完成後，選取 **[下一步** ]。

## <a name="call-flows-during-holidays"></a>假日期間的通話流量

![假日和佳節問候語設定的螢幕擷取畫面。](media/auto-attendant-holiday-greeting.png)

您的自動語音應答可以為 [您所設定的每個假日提供](set-up-holidays-in-teams.md)通話流程。 您可以為每個自動語音應答新增最多 20 個排定的假日。

1. 在 [假日通話設定] 頁面上，選取 [ **新增]**。

2. 輸入此佳節設定的名稱。

3. 從 [ **假日]** 下拉式清單中，選擇您要使用的假日。

4. 選擇您要使用的問候語類型。

    ![假日通話動作設定的螢幕擷取畫面。](media/auto-attendant-holiday-actions.png)

5. 選擇您是否要 **[中斷連線**]、[ **重新導向**] 或 [ **播放] 功能表選項**。

6. 如果您選擇重新導向，請選擇通話的呼叫路由目的地。

7. 如果您選擇播放功能表選項，請設定功能表 [選項](#menu-options)。

8. 選取 [儲存 **]**。

![列出假日的假日設定螢幕擷取畫面。](media/auto-attendant-holiday-call-settings.png)

針對每一個額外的假日，視需要重複此程式。

當您已新增所有假日時，請選取 **[下一步]**。

## <a name="dial-scope"></a>撥號範圍

![包含和排除選項之轉盤範圍的螢幕擷取畫面。](media/auto-attendant-dial-scope.png)

*撥號範圍* 會定義當來電者使用撥號依據名稱或撥號方式延伸時，哪些使用者可在目錄中使用。 [**所有線上使用者]** 的預設值包含貴組織中所有使用 商務用 Skype Server 的線上使用者或內部部署託管的使用者。

您可以選取 [包含] 或 [**排除****] 底下的** **[自訂使用者群組**]，然後選擇一或多個Microsoft 365群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 例如，您可能會想要將貴組織中的高階主管從撥號目錄中排除。  (如果使用者同時在兩份清單中，則會從目錄中排除使用者。) 

> [!NOTE]
> 新使用者可能需要長達 36 小時的時間，才會在目錄中列出他們的名稱。

當您完成設定撥號範圍時，請選取 **[下一步]**。

## <a name="resource-accounts"></a>資源帳戶

所有自動語音應答都必須有相關聯的資源帳戶。  第一層自動語音應答至少需要一個具有相關聯服務號碼的資源帳戶。 如有需要，您可以將多個資源帳戶指派給自動語音應答，每個帳戶都有個別的服務號碼。

![資源帳戶新增帳戶面板的螢幕擷取畫面。](media/auto-attendant-add-resource-account.png)

若要新增資源帳戶，請選取 **[新增帳戶]** ，然後搜尋您要新增的帳戶。 選取 **[新增**]，然後選取 [ **新增]**。

![顯示具有指派服務號碼之資源帳戶的資源帳戶清單螢幕擷取畫面。](media/auto-attendant-resource-account-assigned.png)

當您完成新增資源帳戶時，選取 [ **提交** ] 以完成自動語音應答設定。

如需詳細資訊，請參閱[管理Teams資源帳戶](manage-resource-accounts.md)。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話號碼移轉 - 技術詳細資料

請參閱 [必要條件](plan-auto-attendant-call-queue.md#prerequisites) ，以允許自動語音應答在外部轉接來電。  另外：

- 對於具有[通話方案授權](calling-plans-for-office-365.md)或[電信業者連線](operator-connect-plan.md)號碼的資源帳戶，外部移轉電話號碼必須以 E.164 格式輸入， (+[country code][area code][phone number]) 。

- 對於具有Microsoft Teams 電話授權和直接路由線上語音路由原則的資源帳戶，外部移轉電話號碼格式取決於[會話框線控制器 (SBC) ](direct-routing-connect-the-sbc.md)設定。

顯示的輸出電話號碼如下所示：

  - 針對通話方案和電信業者連線號碼，會顯示原始來電者的電話號碼。
  - 如果是直接路由號碼，傳送的號碼是根據 SBC 上的 P-資訊識別 (一) 設定，如下所示：
    - 如果設為 [停用]，則會顯示原始來電者的電話號碼。 這是預設和建議的設定。
    - 如果設定為 [已啟用]，則會顯示資源帳戶電話號碼。

在商務用 Skype混合式環境中，若要將自動語音應答來電轉接至 PSTN，請建立新的內部部署使用者，並將來電轉接設定為 PSTN 號碼。 使用者必須啟用企業語音並指派語音原則。 若要深入瞭解，請參閱 [自動語音應答來電轉接至 PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

## <a name="auto-attendant-cmdlets"></a>自動語音應答 Cmdlet

Windows PowerShell可讓您以批次或程式設計的方式，透過命令列建立及管理自動語音應答。

下列 Cmdlet 可讓您管理自動語音應答：

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

下列的額外 Cmdlet 也需要管理使用者、資源帳戶、Microsoft Teams 電話授權、電話號碼、音訊檔案，以及搭配通話佇列使用的支援語言：

使用者/Teams

- 使用者
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams： 
- - [Get-Team](/powershell/module/teams/Get-Team)

資源帳戶：

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

虛擬Teams 電話授權：

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

電話編號指派：

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

音訊檔案

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

支援語言和時區

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

如需使用 PowerShell 建立自動語音應答的逐步指南，請參閱[使用 PowerShell Cmdlet 建立自動語音應](create-a-phone-system-auto-attendant-via-cmdlets.md)答

## <a name="auto-attendant-diagnostic-tool"></a>自動語音應答診斷工具

如果您是系統管理員，您可以使用下列診斷工具驗證自動語音應答是否能夠接聽來電：

1. 選取 **[執行測試]** 以在 Microsoft 365 系統管理中心填入診斷。 

   > [!div class="nextstepaction"]
   > [執行測試：Teams自動語音應答]](https://aka.ms/TeamsAADiag)

2. 在 [執行] 診斷窗格中，在 [ **使用者名稱] 或 [電子郵件** ] 欄位中輸入 [資源帳戶]，然後選取 [ **執行測試]**。

3. 這些測試會識別導致自動語音應答無法接聽來電的租使用者、原則或資源帳戶設定，並提供修正已識別問題的步驟。

## <a name="related-topics"></a>相關主題

[以下是您可以透過Teams 電話](./here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
