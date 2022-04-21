---
title: 變更音訊會議橋接器上的電話號碼
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解將新的服務電話號碼指派給會議橋接器所需的步驟，以擴充使用者的涵蓋範圍。
ms.openlocfilehash: 25af462ec7e531bdbaec01ee2a8b37c43376a48e
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016645"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>變更音訊會議橋接器的電話號碼

當您購買 **音訊會議** 授權時，Microsoft 會為您的組織主控您的音訊會議橋接器。 音訊會議橋接器會提供來自不同位置的撥入電話號碼，讓會議召集人和參與者可以使用電話加入商務用 Skype或Microsoft Teams會議。
  
除了已指派給會議橋接器的電話號碼之外，您還可以從其他位置取得用於音訊會議) 的 [額外服務號碼](./getting-service-phone-numbers.md) (付費和免付費電話號碼，然後將它們指派到會議橋接器，以便擴大使用者的涵蓋範圍。
  
> [!NOTE]
> 若要能夠指派/取消指派會議橋接器的電話號碼，電話號碼必須是「*服務*」號碼。 您可以在Microsoft Teams系統管理中心流覽至 **[語音**  >  **電話號碼**]，然後查看 [**數位類型**] 欄，以查看它的數位類型。 Microsoft 365或Office 365通訊點數必須先設定，使用者才能使用免付費電話號碼撥入橋接器。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>將新的服務電話號碼指派到會議橋接器的步驟

> [!NOTE]
> 除了圖說文字之外，所有這些步驟都必須在系統管理中心Microsoft Teams執行。

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步驟 1 - 將新的電話號碼指派給音訊會議橋接器

1. 在左側功能窗格中，移至 **[語音**  >  **電話號碼。**

2. 從清單中選取電話號碼，然後按一下 [ **編輯]**。

3. 在 [**編輯]** 頁面的 [**指定物件**] 底下，展開下拉式清單，然後選取 **[會議橋接器**  >  **]**。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步驟 2 ： 變更會議橋接器的預設電話號碼 (選用) 

會議橋接器的預設電話號碼會定義由會議中的參與者或召集人撥打撥出電話時所使用的來電者 ID。

只有服務付費電話號碼可以設定為會議橋接器的預設號碼; **服務免付費電話號碼無法設定為會議橋接器的預設號碼**。 如果您要指派服務付費電話號碼，而您想要將它設為音訊會議橋接器的新預設號碼，請執行下列步驟：

1. 在左側功能窗格中，移至 **[會議**  >  **會議] 橋接器**。

2. 醒目提示您要設為預設的服務付費電話號碼。

3. 選 **取 [設為預設值]**。

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步驟 3 ： 變更使用者會議邀請中包含的預設電話號碼， (選擇性) 

請參閱[在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 您也可以將電話號碼新增至 *TeamsAudioconferencingpolicy* ，並將原則指派給使用者，藉此設定電話號碼。 新增到原則的付費和免付費電話號碼會優先于透過音訊會議設定窗格個別為使用者設定的電話號碼。 如果未將電話號碼新增至 *Teamsaudioconferencingpolicy*，則透過音訊會議設定窗格個別設定的電話號碼將會顯示在會議邀請Microsoft Teams。 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md) 有更多資訊。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步驟 4 - 使用會議移轉服務更新使用者的現有會議邀請 (選擇性) 

在接下來的兩個步驟中，您必須開始Windows PowerShell。
  
如果您已更新部分或所有使用者會議邀請中所包含的預設電話號碼，您可以選擇性地更新已傳送給貴組織使用者的會議邀請，再使用會議移轉服務變更其預設電話號碼。 如需詳細資訊，請參閱 [設定會議移轉服務 (MMS) ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 針對在步驟 2 中變更預設電話號碼的使用者，執行會議移轉服務 (MMS) 。 若要這麼做，請執行下列命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 您也可以檢視會議移轉狀態。 在 [  *擱置*  中] 或 [ *進行中*  ] 狀態中沒有任何作業時，所有會議都會重新排程。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消指派會議橋接器的服務電話號碼時的步驟

當您從會議橋接器取消指派電話號碼時，使用者將無法再使用該電話號碼加入任何會議。 由於電話號碼正在變更，因此請務必更新所有可能擁有電話號碼做為預設號碼的使用者， (如果有) ，請在取消指派電話號碼至音訊會議橋接器之前更新現有的會議邀請。

如果移除電話號碼而不更新使用者及其會議，則其現有的會議邀請可能包含無法加入其會議的電話號碼。

若要執行前三個步驟，您必須開始Windows PowerShell。 若要瞭解如何執行此動作，請按一下[[想知道如何管理Windows PowerShell？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步驟 1 - 將電話號碼取消指派為預設號碼的使用者

針對將該號碼取消指派為預設號碼的所有使用者，取代預設付費或免付費電話號碼，並開始重新排程其會議的程式。 若要這麼做，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >您也可以在Microsoft Teams系統管理中心變更預設的付費或免付費使用者數目。 不過，這不會自動重新排程他們的會議。

 如需詳細資訊，請參閱[在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)或[在 商務用 Skype Online 中設定邀請中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 視貴組織的規模而定，這可能需要一些時間來完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>步驟 2 - 使用 Windows PowerShell 檢視會議移轉狀態

一旦未在 [ *擱置* ] 或 [ *進行中* ] 狀態中執行任何作業，所有會議都會重新排程。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

如需會議移轉服務的詳細資訊，請參閱 [設定會議移轉服務 (MMS) ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步驟 3 - 從音訊會議橋接器取消指派舊電話號碼

使用Unregister-CsOnlineDialInConferencingServiceNumber Cmdlet 從會議橋接器取消註冊付費或免付費電話號碼

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

注意：若要尋找會議橋接器識別碼，請執行下列 PowerShell：Get-CsOnlineDialInConferencingBridge。

   > [!IMPORTANT]
   > 從音訊會議橋接器未指派電話號碼之後，使用者就無法再使用電話號碼來加入新的或現有的會議。

### <a name="save-time-and-automate"></a>節省時間並自動化

若要透過自動化此程式來節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。

  - 若要變更使用者的預設免付費號碼，請執行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet，根據使用者的原始預設號碼或其位置來變更預設付費或免付費電話號碼。

    > [!NOTE]
    > 若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencingBridge**。

  - 若要為所有使用者設定預設的免付費電話號碼，但不需8005551234，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將所有8005551234為預設免付費電話號碼的使用者的預設免付費電話號碼變更為8005551239，並自動重新排程其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要設定美國所有使用者的預設免付費電話號碼，以8005551234並自動重新排程其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上述位置必須符合Microsoft 365 系統管理中心中設定之使用者 () 的連絡人資訊。

## <a name="troubleshooting"></a>疑難排解

### <a name="the-unassign-button-isnt-available"></a>無法使用 [取消指派] 按鈕

您想要取消指派號碼，但按鈕無法使用，而當您將游標暫留在數位上時，系統會將您重新導向至連絡支援服務，並顯示下列訊息：「無法從橋接器取消指派預設號碼或共用號碼。 若要取消指派專用付費電話號碼，請連絡客戶支援。」

若要取得有關橋接器 () 的詳細資訊，請執行下列 Powershell：

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

除了身分識別、名稱和地區等其他資訊外，結果也應該包含 DefaultServiceNumber。

**範例** 中，to unassign， the DefaultServiceNumber 「8005551234」

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>關於Windows PowerShell

您可以使用Windows PowerShell來管理使用者，以及使用者是或不允許他們執行的動作。 Windows PowerShell可協助您使用單點系統管理來管理Microsoft 365或Office 365，並商務用 Skype Online，簡化您的日常工作，尤其是當您有多個工作要執行的時候。 若要開始使用Windows PowerShell，請參閱下列主題：

- [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell在速度、簡易性和生產力方面有許多優點，而非只使用Microsoft 365 系統管理中心，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：

- [使用 Windows PowerShell 管理Microsoft 365或Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

- [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [使用 Windows PowerShell 執行一般商務用 Skype線上管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相關主題

[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)
