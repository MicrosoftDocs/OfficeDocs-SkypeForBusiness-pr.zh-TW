---
title: 變更音訊會議橋接器上的電話號碼
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解為會議橋接器指派新服務電話號碼以擴大使用者範圍所需的步驟。
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918749"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>變更音訊會議橋接器的電話號碼

當您購買 **音訊會議授權** 時，Microsoft 會為貴組織主持音訊會議橋接器。 音訊會議橋接器會提供不同位置的撥入電話號碼，讓會議召集人和參與者可以使用他們使用電話加入商務用 Skype 或 Microsoft Teams 會議。
  
除了已指派給會議橋接器的電話號碼外，您還可以取得其他位置用於音訊會議的其他服務號碼 [ (](/microsoftteams/getting-service-phone-numbers) 付費和免付費號碼) ，然後將這些號碼指派到會議橋接器，這樣您才能擴大使用者的涵蓋範圍。
  
> [!NOTE]
> 為了能夠指派/取消指派會議橋接器的電話號碼，電話號碼必須是'*服務*'號碼。 您可以流覽至 Microsoft Teams 系統管理中心的語音電話號碼，並查看數位類型欄，查看  >  ******號碼** 類型。 使用者必須先設定 Microsoft 365 或 Office 365 通訊信用額度，才能撥打免付費電話進入橋接器。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>將新服務電話號碼指派給會議橋接器的步驟

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步驟 1 - 將新電話號碼指派到音訊會議橋接器

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格上，**前往語音**  >  **電話號碼**。

2. 從清單中選取電話號碼，然後按一下 **[編輯**。

3. 在編輯 **頁面上**，在已指派 **至** 下展開下拉式清單，然後選取會議 **橋接器**  >  **的適用選項**。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步驟 2 - 變更會議橋接器的預設電話號碼， (選項) 

會議橋接器的預設電話號碼會定義參與者或會議內的召集人撥打外寄通話時所會使用的本機號碼。

只有服務付費電話號碼可以設定為會議橋接器的預設號碼; **服務免付費號碼無法設定為會議橋接器的預設號碼**。 如果您要指派服務付費電話號碼，並想將其設為音訊會議橋接器的新預設號碼，請執行下列步驟：

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格上，前往 **會議**  >  **橋接器**。

2. 強調顯示要設定為預設值的服務付費電話號碼。

3. 選取 **設定成預設值**。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步驟 3 - 變更會議邀請中包含的預設電話號碼， (選擇性) 

使用者的預設電話號碼是當使用者排程會議時，包含在其會議邀請中的號碼。 有關詳細資訊，包括如何為新使用者指派預設電話號碼，請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 邀請中包含的電話號碼，或設定商務用 Skype Online 邀請中包含的 [電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格上，前往[使用者，然後按一下清單中所需使用者的顯示名稱。

2. 在音訊 **會議旁邊，** 按一下 [ **編輯**。

3. 在 **付費電話號碼** 或 **免付費** 電話號碼下，從下拉式清單中選擇要撥打的號碼，然後按一下 [ **申請**。

在變更適用之後，新的預設電話號碼將會包含在下次安排新會議的會議邀請中。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步驟 4 - 更新使用會議移移服務的現有會議邀請， (選擇性) 

接下來的兩個步驟中，您必須啟動 Windows PowerShell。
  
如果您更新了會議邀請中部分或所有使用者的預設電話號碼，您可以選擇性地更新已在使用會議移移服務變更使用者的預設電話號碼之前，已寄給貴組織使用者的會議邀請。 有關其他資訊，請參閱[設定會議移 (MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
- 針對在步驟 2 變更 (使用者) MMS 應用程式執行會議移移服務。 若要這麼做，請執行下列命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 您也可以查看會議移移狀態。 在擱置或進行中狀態沒有作業時，所有會議都會 *重新排排*。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消會議橋接器的服務電話號碼的未指定步驟


當您從會議橋接器取消未指定電話號碼時，使用者將再無法使用此電話號碼加入任何會議。 由於電話號碼正在變更，因此更新所有可能會以電話號碼作為預設號碼的使用者 (如果有任何) ，以及更新其現有的會議邀請，再取消音訊會議橋接器中的電話號碼的呼叫，這一點非常重要。

如果移除電話號碼而不更新使用者及其會議，則他們現有的會議邀請可能包含無法加入其會議的電話號碼。

在前三個步驟中，您必須啟動 Windows PowerShell。 若要瞭解如何執行這項操作，請按一下 [想知道如何使用 [Windows PowerShell 進行管理嗎？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步驟 1 - 更新將電話號碼取消被當做預設號碼之一的使用者

對於將取消未指定作為預設號碼的所有使用者，取代預設付費或免付費電話號碼，並開始進行排程會議程式。 若要這麼做，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >您也可以在 Microsoft Teams 系統管理中心變更預設的付費或免付費使用者數目。 不過，這不會自動重新排期其會議。 
 
 其他資訊請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 邀請中包含的電話號碼，或設定商務用 Skype Online 邀請 [中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 視貴組織的規模大小不同，這可能需要一些時間才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>步驟 2 - 使用 Windows PowerShell 查看會議移移狀態

在擱置或進行中狀態沒有作業時，所有會議都會 *重新排排*。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

有關會議移移服務詳細資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步驟 3 - 取消在音訊會議橋接器中管理舊電話號碼

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽區中，前往 **語音**  >  **電話號碼**。

2. 如果電話號碼是免付費電話號碼，請從清單中選取電話號碼，然後按一下 [ **釋放**。 如果電話號碼是付費電話號碼，請聯絡 Microsoft [支援服務](https://go.microsoft.com/fwlink/?linkid=2091806) ，讓電話號碼取消未指定。

3. 如果電話號碼是免付費電話號碼，請在 **確認** 視窗中按一下 [是。

   > [!IMPORTANT]
   > 取消音訊會議橋接器中的電話號碼之後，使用者就無法再加入新的或現有的會議。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>驗證 Windows PowerShell 已準備就緒

 這些步驟檢查您執行的是 Windows PowerShell 3.0 版或更新版本。

1. 輸入 **Windows**  >  **PowerShell 的開始功能表**。

2. 在 _Windows PowerShell_ 視窗中輸入 **Get-Host** 以檢查版本。

3. 如果您沒有 3.0 版或更新版本，則需要下載並安裝 Windows PowerShell 的更新。 請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下載並更新 Windows PowerShell 至 4.0 版。
當系統提示時，請重新開機電腦。

4. 您也需要安裝商務用 Skype Online 的 Windows PowerShell 模組，可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位的電腦，可從商務用 Skype Online 的 [Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)的 Microsoft 下載中心下載。
如果系統提示，請重新開機電腦。

如果您需要瞭解更多，請參閱在單一 Windows PowerShell 視窗中，連接至所有 [Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>啟動 Windows PowerShell

 **啟動 Windows PowerShell 會話**

1. 從Windows  >  **PowerShell** 的開始功能表。

2. 在 **Windows PowerShell** 視窗中，以以下方式連接至 Microsoft 365 或 Office 365：

> [!NOTE]
> 商務用 Skype Online Connector 目前屬於最新 Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開版本，則不需要安裝商務用 Skype Online Connector。

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> 第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需要執行 **Import-Module** 命令。
如果您需要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連線到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或是使用 Windows PowerShell 連線到商務用[Skype Online。](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)

### <a name="save-time-and-automate"></a>節省時間並自動化

若要將這項程式自動化以節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。

  - 若要變更使用者的預設免付費電話號碼，請執行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet 來根據使用者的原始預設號碼或位置來變更預設付費或免付費數目。

    > [!NOTE]
    > 若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencingBridge。**

  - 若要將所有使用者的預設免付費電話號碼設為 8005551234，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將擁有 8005551234 作為預設免付費電話號碼的所有使用者的預設免付費號碼變更為 8005551239，並自動重新排約其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要將位於美國的所有使用者的預設免付費號碼設為 8005551234，並自動重新排定會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上述使用的位置必須與 Microsoft 365 系統管理 (所) 之使用者的連絡人資訊相符。

## <a name="troubleshooting"></a>疑難排解

**沒有可用的取消未指定按鈕**

您想要取消號碼，但按鈕無法使用，而當游標停留在該號碼上方時，您會被重新導向至客戶支援，並收到下列訊息：「預設號碼或共用號碼無法從橋接器取消呼叫。 _若要取消付費專用電話號碼，請與支援人員聯繫。」。_

若要取得有關橋接器或 () ，請執行下列 PowerShell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果除了身分識別、名稱和地區等其他資訊外，也應該包含 DefaultServiceNumber。

**要** 取消分配的範例，DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>關於 Windows PowerShell

您可以使用 Windows PowerShell 來管理使用者，以及使用者可以或不允許他們執行哪些操作。 Windows PowerShell 可以單一系統管理點，來協助管理 Microsoft 365 或 Office 365 和商務用 Skype Online，以簡化您的日常工作，尤其當您需要執行多項工作時。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell 在速度、簡化及生產力方面有許多優點，是僅用 Microsoft 365 系統管理中心所長，例如當您要一次為許多使用者變更設定時。 在下列主題中瞭解這些優點：

  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)
