---
title: 變更音訊會議橋接器的電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 當您購買音訊會議授權時，Microsoft 會為您的組織託管您的音訊會議橋。 音訊會議橋會從不同位置提供撥入電話號碼，讓會議召集人與參與者都能使用電話加入商務用 Skype 或 Microsoft 團隊會議。
ms.openlocfilehash: 7476f7831ce830c8719940ae555dcd461e19ab2c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684106"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>變更音訊會議橋接器的電話號碼

當您購買**音訊會議**授權時，Microsoft 會為您的組織託管您的音訊會議橋。 [音訊會議橋接器] 會從不同位置提供撥入電話號碼，讓會議召集人與參與者都能使用電話加入商務用 Skype 或 Microsoft 團隊會議。
  
除了已指派給您會議橋接器的電話號碼之外，您還可以從其他位置[取得其他服務號碼](/microsoftteams/getting-service-phone-numbers)（用於音訊會議的免付費電話號碼和免付費電話號碼），然後將它們指派給會議橋接器，您就可以擴大使用者的覆蓋範圍。
  
> [!NOTE]
> 若要能夠指派/取消指派會議橋接器的電話號碼，電話號碼必須是「*服務*」號碼。 您可以流覽到舊版入口網站中的**語音** > **電話號碼**，然後在 [**數位類型**] 欄中查看編號類型。 您必須先設定 Office 365 通訊點數，使用者才能在免費電話號碼撥入橋接器。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>將新的服務電話號碼指派到您的會議橋接器時的步驟

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步驟 1-將新的電話號碼指派給您的音訊會議橋

1. 使用您的公司帳戶登入 Office 365。

2. 移至**Microsoft 365 系統管理中心** > 的系統**管理中心** > **小組 & Skype** > **傳統版入口網站** > **語音** > **電話號碼**。

3. 從清單中選取電話號碼，然後在 [動作] 窗格中，按一下 [**指派**]。

4. 在 [**指派**] 頁面上，按一下 [**儲存**]。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步驟 2-變更您的會議橋接器的預設電話號碼（選用）

您的會議橋接器的預設電話號碼定義由參與者或召集人從會議中傳送出站通話時所使用的本機號碼。

只有服務付費電話號碼可設為您的會議橋接器的預設號碼;**服務免付費電話號碼不能設定為會議橋接器的預設號碼**。 如果您是指派服務付費電話號碼，而您想要將它設為您音訊會議橋接器的新預設號碼，請執行下列步驟：

1. 使用您的公司帳戶登入 Office 365。

2. 移至**Microsoft 365 系統管理中心** > **的管理中心** > **團隊 & Skype** > **會議** > **橋接**器。

3. 醒目提示您要設定為預設值的服務付費電話號碼。

4. 選取 [**設成預設值**]。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步驟 3-變更使用者的會議邀請中所包含的預設電話號碼（選用）

使用者在排程會議時包含在會議邀請上的預設電話號碼。 如需詳細資訊，包括如何指派 defaul 電話號碼給新的使用者，請參閱[設定 Microsoft 團隊邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)，或[在商務用 Skype Online 中設定邀請中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。
  
1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至**Microsoft 365 系統管理中心** > 的**管理中心** > **小組 & Skype** > **舊版入口網站** > **音訊會議** > **使用者**，然後選取清單中的使用者。

3. 按一下 [動作] 窗格中的 [**編輯**]。

4. 在 [**預設的付費電話號碼**] 或 [**預設免付費電話號碼**] 底下，選取清單中的數位，然後按一下 [**儲存**]。

儲存變更之後，新的預設電話號碼將會包含在召集人的會議邀請上（在您下一次排程新會議時）。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步驟 4-使用會議遷移服務更新使用者的現有會議邀請（選用）

在接下來的兩個步驟中，您將需要啟動 Windows PowerShell。
  
如果您更新了部分或所有使用者的會議邀請中 inlcuded 的預設電話號碼，您可以選擇性地更新已傳送給組織中的使用者的會議邀請，在其預設電話號碼變更之後，再使用會議遷移服務。 如需其他資訊，請參閱[設定會議遷移服務（MMS）](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 針對在步驟2中變更預設電話號碼的使用者，執行會議遷移服務（MMS）。 若要這樣做，請執行下列命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 您也可以查看會議的遷移狀態。 當沒有任何作業處於*擱置*或*進行中*的狀態時，就會重新排定所有會議。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>當您取消指派會議橋接器的服務電話號碼時的步驟


當您從會議橋中取消指派電話號碼時，使用者將無法再加入任何使用該電話號碼的會議。 因為電話號碼已變更，所以您必須將所有可能有電話號碼的使用者更新為預設號碼（如果有的話），並更新現有的會議邀請，才能從音訊會議橋中取消指派電話號碼。

如果移除電話號碼但未更新使用者及其會議，則其現有的會議邀請可能包含無法加入會議的電話號碼。

在前三個步驟中，您將需要啟動 Windows PowerShell。 若要瞭解如何執行此動作，請按一下 [[想要知道如何使用 Windows PowerShell 進行管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell) ]

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步驟 1-更新將電話號碼取消指派成其中一個預設號碼的使用者

針對所有要取消指派電話號碼的使用者，將預設的付費或免付費電話號碼取代為預設號碼，並開始重新安排其會議的程式。 若要這樣做，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >您也可以在商務用 Skype 系統管理中心變更預設的付費或免付費使用者數目。 不過，這不會自動重新排程會議。 
 
 如需其他資訊，請參閱[在 Microsoft 團隊中設定邀請所包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)，或[在商務用 Skype Online 中設定邀請中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 視貴組織的規模而定，這可能需要一些時間才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>步驟 2-使用 Windows PowerShell 來查看會議遷移狀態

當沒有任何作業處於*擱置*或*進行中*的狀態時，將會重新排定所有會議。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

如需會議遷移服務的詳細資訊，請參閱[設定會議遷移服務（MMS）](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步驟 3-從音訊會議橋中取消指派舊的電話號碼

1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至**Microsoft 365 系統管理中心** > **管理中心** > **小組 & Skype** > **舊版入口網站** > **語音** > **電話號碼**。

3. 如果電話號碼是免費電話號碼，請從清單中選取電話號碼，然後在 [動作] 窗格中，按一下 [**取消指派**]。 如果電話號碼是付費號碼，請與[Microsoft 支援](https://go.microsoft.com/fwlink/?linkid=2091806)人員聯繫，以取消指派電話號碼。

4. 如果電話號碼是付費 fre 號碼，請在確認視窗中按一下 **[是]** 。

   > [!IMPORTANT]
   > 從音訊會議橋中取消指派電話號碼之後，使用者將無法再使用電話號碼加入新的或現有的會議。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>確認 Windows PowerShell 已準備就緒

 這些步驟會檢查您執行的是 Windows PowerShell 版本3.0 或更高版本。

1. 輸入 [**開始] 功能表** > **Windows PowerShell**。

2. 在**Windows PowerShell**視窗中輸入「_取得主機_」，以檢查版本。

3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。
出現提示時，請重新開機電腦。

4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 只有64位電腦支援此模組，而且可以從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
如果出現提示，請重新開機電腦。

如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>啟動 Windows PowerShell

 **啟動 Windows PowerShell 會話**

1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。

2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。
如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[使用 Windows PowerShell 連線到商務用 Skype Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。

### <a name="save-time-and-automate"></a>節省時間並自動執行

若要透過自動化此程式來節省時間，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688)或**CsOnlineDialInConferencingUserDefaultNumber** Cmdlet。

- 使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。

  - 若要變更使用者的預設免付費電話號碼，請執行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用**CsOnlineDialInConferencingUserDefaultNumber** Cmdlet 根據原始預設號碼或其位置來變更預設的付費或免付費使用者數目。

    > [!NOTE]
    > 若要尋找 BridgeID，請使用**CsOnlineDialInConferencingBridge**。

  - 若要為所有不含1至8005551234的使用者設定預設免付費電話號碼，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將將8005551234作為預設免付費電話號碼的所有使用者的預設免付費電話號碼變更為8005551239，並自動重新安排其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要將美國所有使用者的預設免付費電話號碼設定為8005551234，並自動重新安排其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上面所用的位置需要符合在 Microsoft 365 系統管理中心設定的使用者連絡人資訊。

## <a name="troubleshooting"></a>疑難排解

**[取消指派] 按鈕呈現灰色**

您想要取消指派某個數位，但該按鈕在 hoovering 時是灰顯的，而且如果您是透過其進行，您就會以下列訊息來重定向至連絡人支援： [_預設] 或 [共用號碼] 可以́t 從橋中取消指派。若要取消指派專用的付費電話號碼，請聯絡支援人員。_

若要取得橋接器的詳細資訊，請執行下列 Powershell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果，除了身分識別、名稱和區域之類的其他資訊，也應該包含 DefaultServiceNumber。

**例如**，若要取消指派 DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>關於 Windows PowerShell

您可以使用 Windows PowerShell 來管理使用者，以及不允許他們執行的動作。 Windows PowerShell 可協助您使用單一管理點來管理 Office 365 和商務用 Skype Online，尤其是當您有多個工作需要執行時。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)
