---
title: 在商務用 Skype Online 中管理我組織的音訊會議設定
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '若要將電話撥入式會議授權及會議 ID 指派給使用者和許多其他電話撥入式會議設定，請參閱商務用 Skype Online 步驟。 '
ms.openlocfilehash: f5597ae2b857569b7890d81577e4fd4252da5106
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962701"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>在商務用 Skype Online 中管理我組織的音訊會議設定

> [!NOTE]
> 如果您想要在小組中管理這些設定，請參閱[在 Microsoft 團隊中管理組織的音訊會議設定](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)。

在單一位置查看商務用 Skype 的所有音訊會議設定可能會更容易。


## <a name="assign-an-audio-conferencing-license"></a>指派音訊會議授權

> [!NOTE]
> 您無法使用**商務用 Skype 系統管理中心**指派授權。 您必須使用 Microsoft 365 系統管理中心。 請參閱[指派商務用 Skype 授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

 **指派使用者的授權**

1. 使用您的公司或學校帳戶登入 Office 365。

2. 在系統管理中心的左側導覽中，移至 [**使用者** > 作用中的**使用者**]，然後從可用使用者清單中選取使用者。

    > [!NOTE]
    > 如果您要同時指派授權給20個以上的使用者，您可以使用 [**選取視圖**] 下拉式清單，然後選擇其中一個選項，或建立您自己的 [視圖]。 然後按一下****[編輯 **]，接著**兩次，選取授權，然後按一下 [**提交**]。 您也可以使用 Windows Powershell，將授權指派給多個使用者。 如需指示與範例 PowerShell 腳本，請參閱[指派商務用 Skype 授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

3. 在 [**產品授權**] 底下的 [動作] 窗格中，按一下 [**編輯**]。

4. 在 [**產品授權**] 頁面上，開啟 [**音訊會議**]，然後按一下 [**儲存**]。 如需授權的詳細資訊，請參閱[商務用 Skype 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

> [!NOTE]
> 指派授權之後，Microsoft 可能不會在清單中以音訊會議提供者的形式開始。 如果發生這種情況，請登出系統管理中心，或按 CTRL + F5 重新整理瀏覽器視窗。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>啟用或停用傳送給音訊會議使用者的電子郵件

![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。

3. 在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。

4. 按一下 [**儲存**]。

    您也可以移至使用者的音訊會議屬性，然後按一下 [透過**電子郵件傳送會議資訊**]，以語音會議設定傳送電子郵件給使用者。 會議 ID 和預設的音訊會議電話號碼包含在會議邀請中，但不包含在 PIN 中。

    請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**

- 您也可以使用 Windows PowerShell 並執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    您可以使用 [[設定] CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)來管理貴組織的其他設定，包括電子郵件。

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>變更傳送給使用者的電子郵件訊息中的寄件者連絡人資訊

您可以對自動傳送給使用者的電子郵件進行變更，包括實際的電子郵件地址和寄件者連絡人資訊的顯示名稱。 根據預設，電子郵件的寄件者是 Office 365，但是您可以使用 Windows PowerShell 和[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來變更電子郵件地址和顯示名稱。 若要對傳送電子郵件給使用者的電子郵件地址進行變更，您必須：

- 在_SendEmailFromAddress_參數中輸入電子郵件地址。

- 在_SendEmailFromDisplayName_參數中輸入電子郵件的顯示名稱。

- 將_SendEmailOverride_參數設定為_True_。

您可以執行下列動作，對傳送給使用者的電子郵件進行變更，例如電子郵件的寄件者電子郵件地址或電子郵件的顯示名稱：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果您想要變更電子郵件地址資訊，您必須確認貴組織的輸入電子郵件原則允許來自自訂電子郵件地址的電子郵件。

您可以使用[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來管理貴組織的其他設定，包括電子郵件。

請參閱[在使用者的音訊會議設定變更時自動傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change.md)。

## <a name="reset-the-meeting-conference-id"></a>重設會議 ID

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議**]，並在 [**會議 ID**] 底下的 [動作] 窗格中，按一下 [**重設**]。

4. 在 [**重設會議 ID？** ] 視窗中，按一下 **[是]**。 如果已啟用傳送電子郵件給您的使用者，系統會自動建立會議 ID，並以新的會議 ID 傳送電子郵件給使用者。 預設為啟用。

    > [!IMPORTANT]
    >  在建立新的會議 ID 之後，不能讓呼叫者使用舊的會議 id。 您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。 使用者可以使用商務用 Skype 會議遷移工具來更新現有的會議。 若要瞭解如何下載、安裝及執行商務用 Skype 會議更新工具，請參閱：[適用于商務用 skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[商務用 Skype Online、會議遷移工具（64位）](https://go.microsoft.com/fwlink/?LinkID=626047)，以及[商務用 Skype online、會議遷移工具（32位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。

請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user.md)。

## <a name="reset-a-conference-organizers-pin"></a>重設會議召集人的 PIN

使用者排程的每個會議都會指派唯一的會議 ID。 雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或者您的使用者無法記住或遺失其會議 ID。 您可以使用商務用 Skype 系統管理中心和 Windows PowerShell 來查看、變更及重設其會議 ID。


1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。

3. 按一下 [**使用者**]，然後選取您要重設 PIN 的使用者。

4. 在 [動作] 窗格的 [**釘**選] 底下，按一下 [**重設**]。

當使用者啟用音訊會議或 PIN 重設時，會收到一封電子郵件及其 PIN。 但如果您已停用自動傳送電子郵件，就不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。 PIN 只會在重定後顯示一次。 在重設之後，PIN 就不會再顯示在使用者屬性上;相反，* * * * * 將會顯示。

請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin.md)。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>使用音訊會議資訊傳送電子郵件給使用者

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。

3. 按一下 [**使用者**]，然後選取您要重設 PIN 的使用者。

4. 在 [動作] 窗格中，按一下 [透過**電子郵件傳送會議資訊**]。

    > [!NOTE]
    > 當您這麼做時，音訊會議 PIN 不會傳送給使用者。

請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="setting-the-phone-numbers-included-on-invites"></a>設定邀請中包含的電話號碼

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在左側導覽中，移至 [**音訊會議** > **使用者**]。 選取您想要啟用音訊會議的使用者。

4. 在 [動作] 窗格中，您可以設定**付費電話號碼**，並在允許的情況下撥打免費**電話號碼**。

5. 按一下 [**儲存**]。

請參閱[設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。


## <a name="choosing-audio-conferencing-bridge-settings"></a>選擇 [音訊會議橋接] 設定

**設定呼叫者加入會議時的會議體驗**


1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。

4. 在 [**會議加入體驗**] 底下，選取下列動作：

   - [**啟用會議專案] 和 [結束通知] 以開啟**預設會選取此選項。 如果您清除此核取方塊，當有人進入或離開會議時，預設已加入會議的使用者就不會收到通知。

     當使用者使用商務用 Skype 應用程式加入會議，且在會議的 [Skype 會議**選項**] 功能表中修改 [**使用者進入或離開**] 設定時，可以在會議上進行設定。

   - **要求呼叫者在加入會議前記錄他們的名稱**預設會選取此選項。 如果您清除此核取方塊，則不會要求呼叫者在加入會議前記錄他們的名稱。

5. 進行變更之後，按一下 [**儲存**]。
    
請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **設定會議的 PIN 長度**

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。

4. 在 [**安全性**] 底下的 [ **pin 長度**] 清單中，輸入您想要的 pin 數位位數，然後按一下 [**儲存**]。

    PIN 必須在4到12位數之間。 預設值為5。
    
請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **啟用或停用傳送電子郵件給音訊使用者的電子郵件**

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。

3. 在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。

4. 按一下 [**儲存**]。

    您也可以移至使用者的音訊會議屬性，然後按一下 [透過**電子郵件傳送會議資訊**]，透過音訊會議設定傳送電子郵件給使用者。

    如果您這樣做，就會傳送一封電子郵件，其中只包含會議 ID 和會議電話號碼，但不會包含該 PIN。

    請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音訊會議橋中查看及設定主要（預設）和次要（替代）語言


1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議**]，然後按一下 [ **Microsoft 橋接器**]。

4. 從清單中選取電話號碼，按一下 [動作] 窗格中的 [**設定語言**]，然後在 [**設定語言**] 頁面上，按一下 [使用**主要語言**] 清單來查看支援之語言的完整清單。

    您也可以設定當您選取 Microsoft 作為音訊會議提供者時所支援的主要和次要語言。 您在清單中選取的順序與向呼叫者呈現語言的順序相同。

請參閱[設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing.md)。

## <a name="see-audio-conferencing-dial-in-numbers"></a>請參閱音訊會議撥入號碼

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器**]。 您可以在這裡進行下列動作：

   - 查看由 Office 365 設定用來進行音訊會議的電話號碼。

   - 查看音訊會議自動語音應答將使用的位置，以及主要和次要語言。

   - 選取在使用者啟用音訊會議時，系統會提供給使用者的預設電話號碼。 不過，如果音訊會議橋接的預設電話號碼變更了，現有使用者的預設電話號碼就不會變更。

您可以移至**音訊會議** > **使用者**，然後選取使用者的屬性，以變更使用者的預設號碼，方法是從您組織中可用的號碼清單中選擇新號碼。

請參閱[音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers.md)。

## <a name="see-a-list-of-users-that-are-enabled"></a>查看已啟用的使用者清單

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議**]>，然後移至 [**使用者**]。

請參閱[查看已啟用音訊會議的使用者清單](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

您可以使用 Windows PowerShell 在組織層級管理幾個設定。 這可讓您輕鬆地將設定套用到所有的使用者。

若要取得每個 Cmdlet 的詳細說明，請參閱[商務用 Skype Online Cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。

以下是組織層級設定：

- **設定進入/結束通知**預設值為 [ _$true_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **設定名稱錄製**預設值為 [ _$true_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **設定 PIN 長度**預設值為5。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **僅從手機設定撥入會議**預設 _$false_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **設定是否要將電子郵件傳送給使用者**預設值為 [ _$true_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **設定是否要從不同的帳戶傳送電子郵件**預設值為 [ _$false_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **在傳送給使用者的電子郵件上設定 [寄件者位址**]預設值為 [ _$null_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **設定傳送給使用者的電子郵件顯示名稱**預設值為 [ _$null_]。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell 的速度、簡潔性及生產率都有許多優點，只是使用系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

    商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。

## <a name="related-topics"></a>相關主題

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user.md)


