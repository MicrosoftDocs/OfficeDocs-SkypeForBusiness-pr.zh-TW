---
title: 管理音訊會議設定
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '請參閱Microsoft Teams將電話撥入式會議授權和會議 ID 指派給使用者及許多其他電話撥入式會議設定的步驟。 '
ms.openlocfilehash: e9a464df1d4c3eb01815a652b2e55c6c269b837d
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016615"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 管理貴組織的音訊會議設定

您可能更容易在單一位置查看Microsoft Teams的所有音訊會議設定。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>指派音訊會議授權

> [!NOTE]
> 您無法使用Teams指派授權。 您必須使用Microsoft 365 系統管理中心。 請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="to-assign-a-license-for-a-user"></a>指派授權給使用者

1. 使用公司或學校帳戶登入Microsoft 365。

2. 在Microsoft 365 系統管理中心左側導 **覽** 中，移至 [**使用者**  >  **作用中的使用者**]，然後從可用使用者清單中選取使用者或使用者。

    > [!NOTE]
    > 如果您要同時指派授權給最多 20 個使用者，您可以使用 **[選取檢視** ] 下拉式清單，然後選擇其中一個選項或建立您自己的檢視。 然後按一下 **[編輯**]， **按兩次 [下一步** ]，然後選取授權，然後按一下 [ **提交]**。  
  
3. 在 [產品授權] 下的 [動作] 窗格 **中**，按一下 [ **編輯]**。

4. 在 [ **產品授權]** 頁面上，開啟 **[音訊會議]** ，然後按一下 [ **儲存]**。 如需授權的詳細資訊，[請參閱Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

   > [!NOTE]
   > 指派授權之後，Microsoft 一開始可能不會以音訊會議提供者的形式出現在清單中。 如果發生這種情況，請登出系統管理中心，或按 CTRL+F5 重新整理瀏覽器視窗。
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>啟用或停用傳送給音訊會議使用者的電子郵件

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心啟用或停用

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格中，啟用或停用 **在使用者的電話撥入設定變更時自動傳送電子郵件給使用者**。

4. 按一下 [儲存]。

### <a name="enable-or-disable-using-windows-powershell"></a>使用 Windows PowerShell 啟用或停用

如需詳細資訊，請參閱[Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)。
  
## <a name="reset-the-meeting-conference-id"></a>重設會議 ID

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>使用系統管理中心重設會議 ID Microsoft Teams

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議] 底** 下，按一下 **[重設會議 ID]**。  

3. 在 [ **重設會議 ID？]** 視窗中，按一下 [ **重設]**。 如果已啟用傳送電子郵件給使用者，系統會自動建立會議 ID，並傳送一封含有新會議 ID 的電子郵件給使用者。 此功能預設為啟用。

請參閱 [重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。

## <a name="reset-a-conference-organizers-pin"></a>重設會議召集人的 PIN

使用者排程的每個會議都會獲指派一個唯一的會議 ID。 雖然會議 ID 會自動建立並指派給使用者，但有時候使用者可能不想使用此會議 ID，而您想要將它設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams系統管理中心重設會議召集人的 PIN

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議] 底** 下，按一下 [ **重設 PIN]**，然後按一下 [ **重設]**。
  
使用者在啟用音訊會議或重設 PIN 時，會收到含有 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件的功能，將不會傳送 PIN 重設電子郵件，而且您必須手動傳送 PIN 給使用者。 PIN 在重設之後只會顯示一次。 在重設之後顯示之後，PIN 就不會再顯示在使用者屬性上;相反地，將會顯示 **} 。
  
請參閱[重設音訊會議 PIN。](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>傳送含有音訊會議資訊的電子郵件給使用者

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>使用系統管理中心傳送電子郵件Microsoft Teams

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議] 底** 下，按一下 [ **以電子郵件傳送會議資訊]**。

    > [!NOTE]
    > 當您這麼做時，音訊會議 PIN 不會傳送給使用者。

請參閱 [傳送含有音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>設定邀請中包含的電話號碼

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>使用系統管理中心設定邀請電話號碼Microsoft Teams

請參閱[在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 您也可以將電話號碼新增至 *TeamsAudioconferencingpolicy* ，並將原則指派給使用者，藉此設定電話號碼。 新增到原則的付費和免付費電話號碼會優先于透過音訊會議設定窗格個別為使用者設定的電話號碼。 如果未將電話號碼新增至 *Teamsaudioconferencingpolicy*，則透過音訊會議設定窗格個別設定的電話號碼將會顯示在會議邀請Microsoft Teams。 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md) 有更多資訊。

## <a name="choose-audio-conferencing-bridge-settings"></a>選擇音訊會議橋接器設定

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>使用系統管理中心設定來電者加入會議時 Microsoft Teams的會議體驗

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定]** 窗格中，啟用或停用 **會議進入和結束通知**。

    此功能預設為啟用。 如果您停用此選項，當某人進入或離開會議時，預設已加入會議的使用者將不會收到通知。

4. 在 **[進入/結束宣告類型**] 底下，選擇 [ **音調** ] 或 [ **名稱] 或 [電話號碼]**。

    如果您選擇 **[名稱] 或 [電話號碼**]，您也可以選擇啟用或停用 **[要求來電者在加入會議前記錄他們的名稱]**。
    > [!NOTE]
    > 根據預設，外部參與者無法看到撥入式參與者的電話號碼。 如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。
5. 按一下 [儲存]。

請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
### <a name="set-the-pin-length-for-meetings"></a>設定會議的 PIN 長度

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格的 PIN 長度清單中，輸入您要的 **PIN** 位數，然後按一下 [ **儲存]**。

    PIN 碼必須介於 4 到 12 位數之間。 預設值為 5。

請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>啟用或停用傳送給音訊使用者的電子郵件

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格中，啟用或停用 **在音訊會議設定變更時自動傳送電子郵件給使用者**。

4. 按一下 [儲存]。

    您也可以移至使用者的音訊會議內容，然後按一下 [在 **電子郵件中傳送會議資訊**]，將具有音訊會議設定的電子郵件傳送給使用者。

    如果您這麼做，系統會傳送僅包含會議 ID 和會議電話號碼的電子郵件，但不會包含 PIN。

請參閱 [傳送含有音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音訊會議橋接器上查看及設定主要 (預設) 及次要 () 語言

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>使用系統管理中心查看主要和次要語言Microsoft Teams

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 從清單中選取電話號碼，然後按一下 [ **編輯]**。

3. 在 [ **預設語言** ] 和 [替代語言] 底下選擇您要 **的語言， (選用)**。

4. 按一下 [儲存]。

請參閱 [設定音訊會議的自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心查看音訊會議撥入號碼

1. 在左側導覽中，移至 **[會議**  >  **會議橋樑]**。

2. 從清單中選取電話號碼，然後按一下 [ **編輯]**。 您可以在這裡：

   - 檢視要用於音訊會議的電話號碼。

   - 檢視音訊會議自動語音應答所使用的位置和主要語言。

請 [參閱查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理Microsoft 365或Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理Microsoft 365或Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參閱[powerShell Microsoft Teams參照](/powershell/module/teams/?view=teams-ps)以取得詳細資訊。

## <a name="related-topics"></a>相關主題

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
