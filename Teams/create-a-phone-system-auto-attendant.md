---
title: 設定 Microsoft Teams 的自動 Attendant
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 瞭解如何設定和測試 Microsoft Teams 的自動 Attendant。
ms.openlocfilehash: 4809965eaad0f8cd81b59823d3890bd895998906
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919027"
---
# <a name="set-up-an-auto-attendant"></a>設定自動 Attendant

自動有聲人員可打電話給貴組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 為貴組織建立自動 Attendant。

按照本文中的程式進行之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動撥打和通話[](plan-auto-attendant-call-queue.md#getting-started)佇列的規劃，並遵循入門步驟。

自動語音回應可以根據來電者的輸入，將電話直接撥打至下列其中一個目的地： <a name="call-routing-options" ></a>

- **組織中可以接聽** 語音通話的人，這是貴組織的人。 這可以是線上使用者，或使用商務用 Skype Server 託管于內部部署的使用者。
- **語音應用程式** - 另一個自動語音語音機或通話佇列。  (選擇此目的地.) 
- **外部電話號碼** - 任何電話號碼。  (外部[移轉技術詳細資料，) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **語音** 信箱 - 與所指定的 Microsoft 365 群組相關聯的語音信箱。
- **運算子** - 自動 Attendant 所定義的運算子。 定義運算子是選擇性的。 運算子可以定義為此清單中的其他任何目的地。

當您設定自動語音機時，系統會提示您在各種階段選擇其中一個選項。

若要設定自動語音留言，請在 Teams 系統管理中心展開[語音 **，按一下自動** 語音語音，然後按一下 [**新增**。

## <a name="general-info"></a>一般資訊

![名稱、運算子、時區、語言和語音輸入的自動語音留言設定螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. 在頂端的方塊中輸入自動參與人員的名稱。

2. 如果您要指定運算子，請指定該運算子的通話目的地。 這是選擇性選項 (，但建議您) 。 您可以設定 **運算子** 選項，讓來電者離開功能表，與指定的人員通話。

3. 指定此自動 Attendant 的時區。 如果您為後半小時另外建立一個通話流程，時區會用於 [計算上班時間](#call-flow-for-after-hours)。

4. 指定此自動翻譯人員的語言。 這是系統產生語音提示時所會使用的語言。

5. 選擇是否要啟用語音輸入。 啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。 例如，來電者可以說「一」以選取對應到按鍵 1 的功能表選項，或說出「銷售」以選取名為「銷售」的功能表選項。

6. 按一下 [ **下一步**。

## <a name="call-flow"></a>通話流程

![問候語訊息設定螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

選擇當自動回應接聽電話時，是否要播放問候語。

如果您選取了 **播放音訊檔案，** 您可以使用上傳檔案按鈕來上傳儲存為音訊的錄製問候語訊息。Wav。MP3 或 .WMA 格式。 錄製內容不能大於 5 MB。

如果您選取了輸入問候語訊息，當自動 (接聽電話時，系統就會讀出您輸入的文字) 最多 1000 個字元。

![通話路由設定螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

選擇通話路由方式。

如果您選取了中斷 **連接**，自動電話機會掛斷通話。

如果您選取重新 **導向通話**，您可以選擇其中一個通話路由目的地。

如果您選取了播放 **功能表選項**，您可以選擇播放音訊檔案或輸入問候語，然後選擇功能表選項和目錄搜尋。

### <a name="menu-options"></a>功能表選項

![撥號鍵選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

針對撥號選項，您可以將電話鍵盤上的 0-9 鍵指派給其中一個通話路由目的地。  (系統 (重複 \*)  (上) 的按鍵，且無法重新指派。) \#

金鑰映射表不必是連續的。 例如，建立一個功能表時，有按鍵 0、1 和 3 對應到選項，而 2 個按鍵則沒有使用。

建議您將 0 鍵與運算子進行比對操作 。如果您已經進行一項安裝，建議您將 0 鍵與運算子進行比對。 如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。

請為每個功能表選項指定下列專案：

- **撥號鍵** - 電話鍵盤上的按鍵，可存取此選項。 如果可以使用語音輸入，來電者也可以說出這個號碼來存取選項。

- **語音** 命令 - 定義來電者可給予存取此選項的語音命令 ，如果已啟用語音輸入。 它可以包含多個字詞，例如「客戶服務」或「營運與訂單」。 例如，來電者可以按 2，說「兩」或說「銷售」以選取對應到 2 鍵的選項。 系統也會以服務確認提示的文字到語音轉場呈現此文字，例如「將通話轉接至銷售」。

- **重新導向** 至 - 來電者選擇此選項時所使用的通話路由目的地。 如果您要重新導向至自動有回應或通話佇列，請選擇與其相關聯的資源帳戶。

### <a name="directory-search"></a>目錄搜尋

如果您將撥號鍵指派給目的地，我們建議您針對目錄搜尋選擇 **None。** 如果來電者嘗試使用指定給特定目的地的金鑰撥打名稱或分機，他們可能會在您輸入完名稱或分機前，意外路由至目的地。 建議您為目錄搜尋建立個別的自動 Attendant，並透過撥號鍵讓主要自動 Attendant 連結連至該人員。

如果您未指派撥號鍵，請選擇一個目錄 **搜尋選項**。

**按名稱** 撥號 - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵盤上輸入。 任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，您可以使用 Dial 的名稱找到。  (您可以在撥號範圍頁面上設定哪些人不在目錄中) [](#dial-scope)

**分機號碼** - 如果您啟用此選項，來電者可以撥打分機號碼，與貴組織的使用者聯繫。 任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，而且可以使用 **分機號碼撥號。**  (您可以在撥號範圍頁面上設定哪些人不在目錄中) [](#dial-scope)

若要提供撥號指定分機功能的使用者，其擴充功能必須做為 Active Directory 或 Azure Active Directory 中定義的下列其中一個電話屬性的一部分來[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)指定 (請參閱個別或大量新增使用者以瞭解更多資訊。) 

- OfficePhone
- HomePhone
- 行動/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

在使用者電話號碼欄位中輸入分機所需的格式為：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"
- 範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- 範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

您可以在 [Microsoft 365](https://admin.microsoft.com/) 系統管理中心或 Azure [Active Directory](https://aad.portal.azure.com)系統管理中心設定擴充功能。 最多可能需要 12 小時，才能讓自動參與人員與通話佇列使用變更。

> [!NOTE]
> 如果您想要同時使用撥號者名稱及撥號者分機功能，您可以指派主自動 Attendant 上的撥號鍵，以撥打名稱啟用的自動 **attendant。** 您可以在該自動 attendant 中，指派 1 鍵按鍵 (該按鍵沒有關聯的字母，) 撥打 **分機** 自動 attendant。

選取目錄 **搜尋選項後** ，請按一下 [下一 **步**。

## <a name="call-flow-for-after-hours"></a>數小時後的通話流程

![小時之後日與時間設定螢幕擷取畫面](media/auto-attendant-business-hours.png)

您可以針對每個自動 Attendant 設定上班時間。 如果未設定上班時間，則一天中所有的天和小時會被視為上班時間，這是因為預設會設定 24/7 排程。 您可以設定上班時間與一天中的時間，未設定為上班時間的所有小時會被視為後半小時。 您可以為後半小時設定不同的來電處理選項和問候語。

根據您為自動撥打的號碼和通話佇列的配置，您可能只需要使用直接電話號碼指定自動電話機的後半小時通話路由。

如果您想要為後半小時來電者進行個別的通話路由，請指定每天的上班時間。 例如 **，按一下 [新增時間** 以指定指定一天的多組時數，以指定午餐時間。

指定上班時間之後，再選擇數小時的通話路由選項。 這些選項與上述指定的上班時間通話路由選項相同。

完成 **時** 按一下 [下一步。

## <a name="call-flows-during-holidays"></a>在假日期間通話流程

![假日和假日問候語設定螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

您的自動助理可以針對您設定的每個假日安排 [通話流程](set-up-holidays-in-teams.md)。 您最多可以將 20 個排程的假日加到每個自動 Attendant 中。

1. 在 [假日通話設定> 頁面上，按一下 [ **新增**。

2. 輸入此假日設定的名稱。

3. 從 **假日下** 拉選，選擇您想要使用的假日。

4. 選擇您想要使用的問候語類型。

    ![假日通話動作設定螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. 選擇您是否要中斷 **連接** 或 **重新導向** 通話。

6. 如果您選擇重新導向，請選擇通話的通話路由目的地。

7. 按一下 **[儲存]**。

![已列出假日的假日設定螢幕擷取畫面](media/auto-attendant-holiday-call-settings.png)

針對每一個額外的假日，根據需要重複此程式。

當您新增所有的假日時，按一下 [下一 **步**。

## <a name="dial-scope"></a>撥號範圍

![撥號範圍包含與排除選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

撥號 *範圍* 會定義當來電者使用電話撥入式名稱或按分機號碼時，哪些使用者可以在目錄中使用。 根據預設 **，所有線上使用者** 會包含貴組織的所有使用者，這些使用者都是線上使用者，或是使用商務用 Skype Server 託管于內部部署。

您可以在包含或排除下選取自訂使用者群組，並選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。  例如，您可能會想要將貴組織高主管排除在撥號目錄中。  (如果使用者同時位於這兩個清單中，他們將從目錄.) 

> [!NOTE]
> 新使用者最多可能需要 36 小時，才能將名稱列在目錄中。

設定完撥號範圍之後，請按一下 [下一 **步**。

## <a name="resource-accounts"></a>資源帳戶

所有自動 attendants 都必須有相關聯的資源帳戶。  第一層自動出席者至少需要一個擁有相關聯服務號碼的資源帳戶。 如果您想要的話，您可以將數個資源帳戶指派給自動 Attendant，每個帳戶都有個別的服務號碼。

![資源帳戶新增帳戶面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

若要新增資源帳戶，請按一下 [ **新增** 帳戶，然後搜尋您想要新增的帳戶。 按一下 **[新增**，然後按一下 [ **新增**。

![顯示有已指派服務編號之資源帳戶清單的螢幕擷取畫面](media/auto-attendant-resource-account-assigned.png)

完成新增服務帳戶後，請按一下 **[提交**。 這會完成自動 attendant 的安裝。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話號碼轉接 - 技術詳細資料

請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以允許自動 Attendant 將電話轉接至外部。  另外：

- 對於有通話方案號碼的資源[](calling-plans-for-office-365.md)帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國碼][區碼][電話號碼]) 。

- 針對具有直接路由號碼的資源帳戶，外部轉接電話號碼格式會設定在會話邊界控制器上 ([SBC) ](direct-routing-connect-the-sbc.md) 設定。

顯示的電話號碼會以以下方式判斷：

  - 針對通話方案號碼，會顯示原始來電者的電話號碼。
  - 針對直接路由號碼，傳送的號碼是根據 SBC (PAI) 設定，如下所示：
    - 如果設為停用，則會顯示原始來電者的電話號碼。 這是預設且建議使用的設定。
    - 如果設為已啟用，則會顯示資源帳戶電話號碼。

在商務用 Skype 混合式環境中，若要將自動參與通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。 使用者必須啟用企業語音，並指派語音策略。 若要深入瞭解，請參閱自動 [將電話轉接到 PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)的自動 Attendant 通話。

### <a name="create-an-auto-attendant-with-powershell"></a>使用 PowerShell 建立自動 Attendant

您也可以使用 PowerShell 來建立及設定自動 Attendant。 以下是管理自動 attendant 時所需的 Cmdlet：

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendant一idays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnline在一起](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendant一idays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendant一idays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
