---
title: 在線上管理組織的音訊會議商務用 Skype設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '請參閱商務用 Skype線上步驟，將電話撥入式會議授權和會議 ID 指派給使用者，以及許多其他電話撥入式會議設定。 '
ms.openlocfilehash: 68deefd4092d05081ffe8a7aac9a1dc92ea36940
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726462"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>在線上管理組織的音訊會議商務用 Skype設定

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 如果您想要在 Teams 管理這些設定，請參閱在 Microsoft Teams 中管理組織的[音訊會議Microsoft Teams。](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)

您可以更輕鬆地在單一位置查看所有商務用 Skype會議設定。


## <a name="assign-an-audio-conferencing-license"></a>指派音訊會議授權

> [!NOTE]
> 您無法使用系統管理中心 **指派商務用 Skype授權**。 您必須使用Microsoft 365 系統管理中心。 請參閱[指派商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

 **為使用者指派授權**

1. 使用公司或學校帳戶來登錄。

2. 在系統管理中心的左側導覽中，前往使用者活動使用者，然後從可用使用者清單中選取  >  使用者。

    > [!NOTE]
    > 如果您同時將授權指派給最多 20 個使用者，您可以使用選取視圖下拉式清單，然後選擇其中一個選項，或建立您自己的視圖。 然後按一下 [**編輯，****下** 一步兩次，然後選取授權並 **按一下 [提交**> 。 您也可以使用 Powershell，將授權指派給Windows使用者。 有關指示和 PowerShell 腳本範例，請參閱指派[商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

3. 在 [產品授權」 下的 [動作 **窗格**> 中，按一下 **[編輯>**。

4. 在 [ **產品授權>** 頁面上，開啟 **音訊會議** ，然後按一下 [ **儲存**。 有關授權的更多內容，請參閱商務用 Skype[附加元件授權。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

> [!NOTE]
> 指派授權之後，Microsoft 一開始可能不會在清單中顯示為音訊會議提供者。 如果發生這種情況，請登出系統管理中心，或按 CTRL+F5 重新啟用瀏覽器視窗。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>啟用或停用發送給音訊會議使用者的電子郵件

![顯示標誌圖示商務用 Skype圖示。](../images/sfb-logo-30x30.png) **使用 商務用 Skype系統管理中心**

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心>商務用 Skype **流覽左側** 的 [**音訊會議**> 。

3. 在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。

4. 按一下 [儲存]。

    您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以 **電子郵件傳送會議資訊**。 會議邀請中包含會議 ID 和預設音訊會議電話號碼，但不包含 PIN。

    請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用Windows PowerShell**

- 您也可以使用以下Windows PowerShell執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 來管理貴組織的其他設定，包括電子郵件。

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>在電子郵件訊息中變更寄件者的連絡人資訊

您可以變更自動寄給使用者的電子郵件，包括實際的電子郵件地址和寄件者連絡人資訊的顯示名稱。 根據預設，電子郵件的寄件者為 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來變更電子郵件地址和顯示名稱。 若要變更傳送電子郵件給使用者的電子郵件地址，您必須：

- 在 _SendEmailFromAddress 參數中輸入_ 電子郵件地址。

- 在  _SendEmailFromDisplayName 參數中輸入電子郵件顯示_ 名稱。

- 將 _SendEmailOverride 參數_ 設為 _True_。

您可以進行變更，例如電子郵件的寄回電子郵件地址或電子郵件的顯示名稱，以使用者：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果您想要變更電子郵件地址資訊，您必須確定貴組織的輸入電子郵件政策允許來自自訂電子郵件地址的電子郵件。

您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來管理貴組織的其他設定，包括電子郵件。

請參閱 [當使用者的音訊會議設定變更時自動發送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change.md)。

## <a name="reset-the-meeting-conference-id"></a>重設會議 ID

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 **商務用 Skype系統** 管理中心，在左側流覽中，前往 [音訊會議>，然後按一下 [會議 **識別碼**》 下的 [動作窗格> 中的 [**重設**。

4. 在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。 如果已啟用傳送電子郵件給使用者，系統會自動建立會議 ID，並傳送一封具有新會議 ID 的電子郵件給使用者。 預設會啟用此功能。

    > [!IMPORTANT]
    >  建立新會議 ID 之後，來電者無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 使用者可以使用會議移商務用 Skype工具來更新現有的會議。 若要瞭解如何下載、安裝及執行 商務用 Skype 會議更新工具，請參閱：商務用 Skype 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的會議更新工具、商務用 Skype Online、會議移移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 商務用 Skype Online、會議移移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。

請參閱[為使用者重設會議 ID。](reset-a-conference-id-for-a-user.md)

## <a name="reset-a-conference-organizers-pin"></a>重設會議召集人的 PIN

使用者排程的每個會議都會獲得一個唯一的會議 ID。 雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。 您可以使用系統管理商務用 Skype和Windows PowerShell來查看、變更和重設其會議 ID。


1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心>商務用 Skype **流覽左側** 的 [**音訊會議**> 。

3. 按一下 **[** 使用者，然後選取要重設 PIN 的使用者。

4. 在 [動作窗格的 **PIN** 中，按一下 [ **重設**。

當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件，將不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。 PIN 在重設後只會顯示一次。 在重設後顯示 PIN 之後，PIN 就不會再顯示在使用者屬性上;而是會顯示 **** 。

請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin.md)。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>傳送包含音訊會議資訊的電子郵件給使用者

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心>商務用 Skype **流覽左側** 的 [**音訊會議**> 。

3. 按一下 **[** 使用者，然後選取要重設 PIN 的使用者。

4. 在 [動作」 窗格中，按一下 **[透過電子郵件傳送會議資訊。**

    > [!NOTE]
    > 當您這麼做時，音訊會議 PIN 不會發送給使用者。

請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="setting-the-phone-numbers-included-on-invites"></a>設定邀請中包含的電話號碼

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在左側流覽中，前往 **音訊會議**  >  **使用者**。 選取您想要為音訊會議啟用的使用者。

4. 在動作窗格中，您可以設定付費 **號碼** ，如果允許，也可以設定 **免付費號碼**。

5. 按一下 [儲存]。

請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。


## <a name="choosing-audio-conferencing-bridge-settings"></a>選擇音訊會議橋接器設定

**設定來電者加入會議時的會議體驗**


1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。

4. 在 **會議加入體驗下**，選取下列動作：

   - **啟用會議進入和離開通知的開啟** 這是預設選取的。 如果您清除此核取方塊，根據預設，已加入會議的使用者不會在有人進入或離開會議時收到通知。

     This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.

   - **要求來電者在加入會議前先錄製其名稱** 這是預設選取的。 如果您清除此核取方塊，不會要求來電者在加入會議之前先記錄他們的名稱。

5. 進行變更之後，請按一下 [**儲存。**
    
請參閱 [變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **設定會議的 PIN 長度**

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。

4. 在 **[安全性**」 下，在 PIN 長度清單中輸入PIN 的位數，然後按一下 [**儲存**。

    PIN 必須介於 4 到 12 位數之間。 預設值為 5。
    
請參閱 [變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **啟用或停用電子郵件，禁止將電子郵件發送給音訊使用者**

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心>商務用 Skype **流覽左側** 的 [**音訊會議**> 。

3. 在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。

4. 按一下 [儲存]。

    您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以 **電子郵件傳送會議資訊**。

    如果您這麼做，將會送出只包含會議 ID 和會議電話號碼的電子郵件，但不包含 PIN。

    請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音訊會議橋接器上查看 (預設) 次要 (替代) 語言


1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 商務用 Skype **系統** 管理中心，在左側流覽中，前往 [**音訊會議**，然後按一下 Microsoft **橋接器**。

4. 從清單中選取電話號碼，按一下 [動作窗格設定語言>，然後在 [設定語言>頁面上，按一下 [使用主要語言清單來查看支援的語言的完整清單。 

    您也可以設定當您選取 Microsoft 做為音訊會議提供者時支援的主要和次要語言。 在清單中選取的順序與向來電者呈現語言的順序相同。

請參閱 [設定音訊會議的自動語音語音處理語言](set-auto-attendant-languages-for-audio-conferencing.md)。

## <a name="see-audio-conferencing-dial-in-numbers"></a>請參閱音訊會議電話撥入號碼

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**
 
3. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**  >  **Microsoft 橋接器**。 您可以在這裡：

   - 查看音訊會議Microsoft 365或Office 365所設定的電話號碼。

   - 查看音訊會議自動語音機會使用的位置，以及主要和次要語言。

   - 選取啟用音訊會議時，會給予使用者的預設電話號碼。 不過，如果音訊會議橋接器的預設電話號碼變更，現有使用者的預設電話號碼不會變更。

您可以前往音訊 **會議** 使用者，然後選取使用者的屬性，以變更使用者的預設號碼，從貴組織中可用的號碼清單中選擇新  >  號碼。

請參閱 [查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers.md)。

## <a name="see-a-list-of-users-that-are-enabled"></a>查看已啟用的使用者清單

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 商務用 Skype **系統** 管理中心，在左側流覽中，前往音訊會議>**使用者。**

請參閱 [查看已啟用音訊會議的使用者清單](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

您可以在組織層級使用多個設定來管理Windows PowerShell。 這可輕鬆地將設定適用于所有使用者。

若要取得每個 Cmdlet 的更多協助，請參閱[商務用 Skype Cmdlet。](/previous-versions//mt228132(v=technet.10))

以下是組織層級設定：

- **設定進入/離開通知** 預設值 _為_$true。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **設定名稱錄製** 預設值 _為_$true。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **設定 PIN 長度** 預設值為 5。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **只從電話設定電話撥入會議** 預設 _$false。_
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **設定是否要傳送電子郵件給使用者** 預設值 _為_$true。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **設定是否要從其他帳戶傳送電子郵件** 預設值  _為_$false。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **在電子郵件上設定要寄給使用者的 From 位址** 預設值 _為_$null。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **設定電子郵件的** 顯示名稱預設值  _為_$null。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell
- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：

  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell使用系統管理中心時，系統在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 商務用 Skype[模組。](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>相關主題

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user.md)
