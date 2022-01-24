---
title: 設定自動Microsoft Teams
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
description: 瞭解如何在 Microsoft Teams 中為大型組織設定和測試自動Microsoft Teams。
ms.openlocfilehash: 834ca1b68e64047c6405c2aefba361e0ef4f1e81
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180956"
---
# <a name="set-up-an-auto-attendant"></a>設定自動機務員

自動話務員可讓人打電話給您的組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。 您可以使用系統管理中心或 PowerShell 為貴組織Microsoft Teams自動助理。

> [!TIP]
> 本文適用于大型組織。 如果貴組織是小型企業，請改為閱讀設定自動話務員 [- 小型企業](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 教學課程。

請務必先閱讀自動Teams[](plan-auto-attendant-call-queue.md)和通話佇列方案，並遵循開始使用的步驟，然後再遵循本文中的程式[](plan-auto-attendant-call-queue.md#getting-started)。

自動語音機可以根據來電者的輸入，將通話直接路由至下列其中一個目的地： <a name="call-routing-options" ></a>

- **運算子** - 為自動話務員定義的運算子。 定義運算子是選擇性的。 運算子可以定義為此清單的其他任何目的地。
- **組織中可以接聽** 語音通話的人。 此人員可以是線上使用者，或使用內部部署託管商務用 Skype Server。
- **語音應用程式** - 另一個自動語音留言機或通話佇列。  (選擇此目的地時，選擇與自動電話機或通話佇列相關聯的資源帳戶。) 
- **語音** 信箱 - 與您指定的Microsoft 365群組相關聯的語音信箱。 您可以選擇是否要語音信箱字幕和「請在語音信箱後留言」。 系統提示。
- **外部電話號碼** - 任何電話號碼。  (請參閱[外部移轉技術詳細資料) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **音訊 (公告)** - 播放音訊檔案。 您上傳的已錄製公告訊息，儲存為音訊。WAV、.MP3或 。WMA 格式。 錄製內容不能大於 5 MB。 系統會播放公告，然後返回自動助理功能表。
- **公告 (輸入)** - 在郵件中輸入。 您希望系統讀取的文字。 您最多可以輸入 1000 個字元。 系統會播放公告，然後返回自動助理功能表。

當您設定自動語音機時，系統會提示您于各個階段選擇其中一個選項。

若要設定自動語音Teams，請在系統管理中心展開 **語音**，選取自動語音留言，然後選取 **新增**。

## <a name="video-demonstration"></a>影片示範

這段影片顯示如何在 Teams 中建立自動Teams。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>一般資訊

![名稱、運算子、時區、語言和語音輸入的自動語音留言設定螢幕擷取畫面。](media/auto-attendant-general-info-page-new.png)

1. 在頂端方塊中輸入自動助理的名稱。

2. 若要指定運算子，請指定撥打給接線員的目的地。 此指定為選擇性 (，但建議使用) 。 設定運算子 **選項** ，讓來電者離開功能表，與指定的人員說話。

3. 指定此自動助理的時區。 如果您為小時後建立個別的通話流程，則時區會用來 [計算上班時間](#call-flow-for-after-hours)。

4. 指定此 [自動翻譯](create-a-phone-system-auto-attendant-languages.md) 的支援語言。 這是系統產生的語音提示所使用的語言。

5. 選擇是否要啟用語音輸入。 啟用時，每個功能表選項的名稱會變成語音辨識關鍵字。 例如，來電者可以說「一」，以選取對應到按鍵 1 的功能表選項，或說「銷售」以選取名為「銷售」的功能表選項。

   > [!NOTE]
   > 如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。

6. 選取 下 **一個**。

## <a name="call-flow"></a>通話流程

![問候語訊息設定螢幕擷取畫面。](media/auto-attendant-call-flow-greeting-message.png)

選擇當自動回應接聽來電時，是否要播放問候語。

如果您選取 **播放音訊檔案**，您可以使用 Upload **按鈕上傳** 儲存為音訊的錄製問候語訊息。WAV、.MP3或 。WMA 格式。 錄製內容不能大於 5 MB。

如果您選取輸入 **問候語訊息** ，當自動 (接聽來電時，系統會朗讀您輸入) 最多 1000 個字元的文字。

![通話路由設定螢幕擷取畫面。](media/auto-attendant-call-flow-route-call-message.png)

選擇通話的路由方式。

如果您選取中斷 **連接**，自動電話機會掛斷通話。

如果您選取 **重新導向通話**，您可以選擇其中一個呼叫路由目的地。

如果您選取 **了播放功能表選項**，您可以選擇播放音訊檔案或輸入問候語訊息，然後選擇功能表選項和目錄搜尋。

### <a name="menu-options"></a>功能表選項

![撥號鍵選項的螢幕擷取畫面。](media/auto-attendant-call-flow-menu-options-complete.png)

針對撥號選項，將電話鍵臺上的 0-9 鍵指派給其中一個撥號路由目的地。  (系統會保留 (星號)  () 的按鍵，且無法重新 \* \# 指派。 按下其中一個按鍵會重複目前的功能表。) 

> [!NOTE]
> # 鍵只會備份到最新的自動助理。 一旦邊界跨越到新的自動助理，# 鍵將無法將您帶往上一個。

鍵的映射不必是連續的。 雖然沒有使用數位 2 鍵，但可以建立對應到選項的按鍵 0、1 和 3 的功能表。

如果您已經配置零鍵，建議您將零鍵與運算子進行比對。 如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。

針對每個功能表選項，指定下列設定：

- **撥號鍵** - 電話鍵臺上的按鍵，以存取此選項。 如果語音輸入可用，來電者也可以說這個號碼來存取選項。

- **Voice 命令** - 定義來電者可以給予的語音命令以存取此選項 ，如果已啟用語音輸入。 它可以包含多個字詞，例如「客戶服務」或「營運與理由」。 例如，來電者可以按 2，說出「兩」，或說「銷售」以選取對應到兩個按鍵的選項。 此文字也會以服務確認提示的文字呈現為語音轉語音，例如「將通話轉接至銷售」。

- **重新導向** 至 - 當來電者選擇此選項時所使用的通話路由目的地。 如果您要重新導向到自動電話機或通話佇列，請選擇與其相關聯的資源帳戶。

### <a name="directory-search"></a>目錄搜尋

如果您將撥號鍵指派給目的地，建議您選擇 **目錄搜尋的****無**。 如果來電者嘗試使用指派給特定目的地的按鍵撥號名稱或分機，他們可能會在您輸入名稱或分機之前，意外路由到目的地。 建議您為目錄搜尋建立個別的自動總機，並擁有使用撥號鍵的自動總機連結。

如果您沒有指派撥號鍵，請選擇目錄 **搜尋的選項**。

**按名稱** 撥號 - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵臺上輸入。 任何線上使用者或任何使用 商務用 Skype Server 託管于內部部署的使用者，都是合格的使用者，而且可以使用撥號名稱找到。  (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)

**分機撥號** - 如果您啟用此選項，來電者可以撥打其電話分機，與貴組織的使用者聯繫。 任何線上使用者或任何使用 商務用 Skype Server 託管于內部部署的使用者，都是合格的使用者，而且可以使用 **分機撥號找到**。  (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)

您想要提供撥號分機的使用者，需要將分機指定為 Active Directory 或 Azure Active Directory (中定義的下列其中一個電話屬性的一部分Azure Active Directory (請參閱個別或大量[](/microsoft-365/admin/add-users/add-users)新增使用者以瞭解更多資訊。) 

- OfficePhone
- 家用電話
- Mobile/MobilePhone
- PhoneNumber/PhoneNumber
- OtherTelephone

在使用者電話號碼欄位中輸入分機所需的格式可以是下列其中一種格式：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber"+15555555678;ext=5678"
- 範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- 範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

您可以在系統管理中心或 Microsoft 365 系統管理中心[中Azure Active Directory](https://admin.microsoft.com/)[副檔名](https://aad.portal.azure.com)。 自動電話機和通話佇列最多可能需要 12 小時才能進行變更。

> [!NOTE]
> 如果您想要同時使用名稱撥號和分機撥號功能，您可以在主自動電話機上指派撥號鍵，以到達啟用名稱撥號 **的自動總機**。 您可以在該自動話務員中指派 1 個按鍵 (沒有與其關聯的字母) **分機自動** 總機。

選取目錄搜尋 **選項之後，** 請選取 下 **一步**。

## <a name="call-flow-for-after-hours"></a>數小時後的通話流程

![日時數和時間設定後的螢幕擷取畫面。](media/auto-attendant-business-hours.png)

您可以針對每個自動話務員設定上班時間。 如果未設定上班時間，則一天中所有的天數和所有時數會視為上班時間，因為預設會設定 24/7 排程。 工作時間可以設定為一天中的休息時間，所有未設定為上班時間的時數會視為工作時間之後。 您可以為工作時間設定不同的來電處理選項和問候語。

根據您如何配置自動電話機和通話佇列，您可能只需要為具有直接電話號碼的自動電話機指定後通話路由。

如果您想要為非工作時間的來電者個別進行通話路由，請為每天指定您的上班時間。 選取 **新增時間** 以指定指定一天的陣列時數，例如，指定午餐休息時間。

指定上班時間之後，請選擇數小時後的通話路由選項。 上述指定的上班時間通話路由也提供相同的選項。

完成後 **，** 請選取下一步。

## <a name="call-flows-during-holidays"></a>假日期間通話流程

![假日和假日問候語設定螢幕擷取畫面。](media/auto-attendant-holiday-greeting.png)

您的自動電話機可以針對您設定的每個 [假日有通話流程](set-up-holidays-in-teams.md)。 您最多可以將 20 個排定的假日加到每個自動乘務員。

1. 在假日通話設定頁面上 **，選取** 新增 。

2. 輸入此假日設定的名稱。

3. 從假日 **下** 拉下拉，選擇您想要使用的假日。

4. 選擇您想要使用的問候語類型。

    ![假日通話動作設定螢幕擷取畫面。](media/auto-attendant-holiday-actions.png)

5. 選擇是否要中斷 **連接或****重新** 導向通話。

6. 如果您選擇重新導向，請選擇通話的呼叫路由目的地。

7. 選取 [儲存 **]**。

![列出假日的假日設定螢幕擷取畫面。](media/auto-attendant-holiday-call-settings.png)

針對每一個額外的假日，根據需要重複此程式。

當您新增所有假日後，請選取下 **一步**。

## <a name="dial-scope"></a>撥號範圍

![撥號範圍包含和排除選項的螢幕擷取畫面。](media/auto-attendant-dial-scope.png)

撥號 *範圍* 會定義當來電者使用撥號名稱或撥號分機時，哪些使用者可在目錄中使用。 預設為 **所有線上使用者**，包括貴組織的所有使用者，這些使用者都是線上使用者，或是由內部部署使用者商務用 Skype Server。

您可以選取在包含或排除下的自訂使用者群組，並選擇一或多個Microsoft 365群組、通訊群組清單或安全性群組，以包含或排除特定使用者。  例如，您可能會想要將貴組織的主管排除在撥號目錄中。  (如果使用者同時位於這兩個清單中，就會被排除在目錄中。) 

> [!NOTE]
> 新使用者最多可能需要 36 小時，才能將名稱列在目錄中。

設定好撥號範圍之後，請選取下一 **步**。

## <a name="resource-accounts"></a>資源帳戶

所有自動話務員都必須有相關聯的資源帳戶。  第一層自動總機至少需要一個具有關聯服務號碼的資源帳戶。 您可以根據需要，將多個資源帳戶指派給自動助理，每個帳戶都有個別的服務號碼。

![資源帳戶新增帳戶面板的螢幕擷取畫面。](media/auto-attendant-add-resource-account.png)

若要新增資源帳戶，請選取 **新增帳戶** ，然後搜尋您想要新增的帳戶。 選取 **新增**，然後 **選取** 新增 。

![顯示資源帳戶與已指派服務編號的資源帳戶清單螢幕擷取畫面。](media/auto-attendant-resource-account-assigned.png)

當您完成新增資源帳戶後，請選取 **提交** 以完成自動總機配置。

請參閱[管理Teams資源](manage-resource-accounts.md)帳戶以瞭解更多資訊。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話號碼傳輸 - 技術詳細資料

請參閱 [先決條件，](plan-auto-attendant-call-queue.md#prerequisites) 以便允許自動電話機在外部轉接通話。  另外：

- 對於具有通話方案授權或[](calling-plans-for-office-365.md)運算子[連線](operator-connect-plan.md)號碼的資源帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國家/地區代碼][區碼][電話號碼]) 。

- 對於具有授權和直接Microsoft Teams 電話線上語音路由策略的資源帳戶，外部傳輸電話號碼格式取決於會話邊界控制器[ (SBC](direct-routing-connect-the-sbc.md)) 設定。

顯示的外發電話號碼如下：

  - 針對通話方案與連線，會顯示原始來電者的電話號碼。
  - 針對直接路由號碼，傳送的數位是根據 SBC 上的 P-Identityed-identity (PAI) 設定，如下所示：
    - 如果設為已停用，會顯示原始來電者的電話號碼。 這是預設且建議的設定。
    - 如果設為啟用，會顯示資源帳戶電話號碼。

在混合商務用 Skype環境中，若要將自動通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。 使用者必須啟用企業語音並指派語音策略。 若要深入瞭解，請參閱[將電話自動轉接到 PSTN。](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

## <a name="auto-attendant-cmdlets"></a>自動傳話 Cmdlet

Windows PowerShell可讓您透過命令列以批次或程式設計的方式建立和管理自動助理。

下列 Cmdlet 允許您管理自動話務：

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
- [New-CsAutoAttendantCallHandlingAsociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

管理將用於通話佇列的使用者、資源帳戶、Microsoft Teams 電話授權、電話號碼、音訊檔案和支援的語言，還需要下列其他 Cmdlet：

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

電話數位指派：

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

有關使用 PowerShell 建立自動助理的逐步指南，請參閱使用[PowerShell Cmdlet](create-a-phone-system-auto-attendant-via-cmdlets.md)建立自動助理

## <a name="auto-attendant-diagnostic-tool"></a>自動助理診斷工具

如果您是系統管理員，您可以使用下列診斷工具來驗證自動話務員是否能夠接聽來電：

1. 選取 **[執行測試]** 以在 Microsoft 365 系統管理中心填入診斷。 

   > [!div class="nextstepaction"]
   > [執行測試：Teams自動助理](https://aka.ms/TeamsAADiag)

2. 在執行診斷窗格中，在使用者名稱或電子郵件欄位中輸入資源帳戶，然後選取 **執行測試**。

3. 測試會識別租使用者、策略或資源帳戶組組，防止自動話務員接聽來電，並提供步驟以修正已識別的任何問題。

## <a name="related-topics"></a>相關主題

[以下是您取得Teams 電話](./here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
