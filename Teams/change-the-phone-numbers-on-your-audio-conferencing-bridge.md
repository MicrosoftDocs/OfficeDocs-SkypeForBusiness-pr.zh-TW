---
title: 在音訊會議橋接器上變更電話號碼
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解為會議橋接器指派新服務電話號碼以擴大使用者範圍所需的步驟。
ms.openlocfilehash: f39a963759e768f4fab70d2a06e6d90b480699e0
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536714"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>變更音訊會議橋接器的電話號碼

當您購買 **音訊會議授權** 時，Microsoft 會為貴組織託管您的音訊會議橋接器。 音訊會議橋接器會提供不同位置的撥入電話號碼，讓會議召集人和參與者可以使用電話商務用 Skype或Microsoft Teams會議。
  
除了已指派給會議橋接器的電話號碼之外，您還可以從其他位置取得用於音訊會議) 的其他服務號碼 [ (](./getting-service-phone-numbers.md) 付費和免付費號碼，然後將這些號碼指派給會議橋接器，以便擴大使用者的涵蓋範圍。
  
> [!NOTE]
> 若要指派/取消指派會議橋接器的電話號碼，電話號碼必須是'*服務*'號碼。 您可以在系統管理中心流覽至 Voice 電話號碼，並查看Microsoft Teams類型欄  >  ****，來查看 **號碼** 的類型。 Microsoft 365或Office 365通訊信用額度必須先設定，使用者才能使用免付費號碼撥入橋接器。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>將新服務電話號碼指派給會議橋接器的步驟

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步驟 1 - 將新電話號碼指派給音訊會議橋接器

 **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格中，前往語音電話  >  **號碼**。

2. 從清單中選取電話號碼，然後按一下 [ **編輯**。

3. 在編輯 **頁面上****，展開下** 拉式清單的下拉式清單，然後選取 **會議橋接器**  >  **的 Apply**。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步驟 2 - 變更會議橋接器的預設電話號碼 (選項) 

會議橋接器的預設電話號碼會定義參與者或召集人從會議內撥打外寄電話時，會使用的本機號碼。

只有服務付費號碼可以設定為會議橋接器的預設號碼; **服務免付費號碼無法設定為會議橋接器的預設號碼**。 如果您要指派服務付費號碼，並想將其設定為音訊會議橋接器的新預設號碼，請執行下列步驟：

 **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格中，前往 **會議**  >  **會議橋接器**。

2. 強調您想要設定為預設值的服務付費號碼。

3. 選取 **設定為預設值**。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步驟 3 - 變更使用者會議邀請中包含的預設電話號碼， () 

使用者的預設電話號碼是排程會議時包含在會議邀請中的號碼。 有關詳細資訊 ，包括新使用者預設電話號碼的指派方式，請參閱在 Microsoft Teams 中設定邀請中包含的[電話號碼，](set-the-phone-numbers-included-on-invites-in-teams.md)或在 商務用 Skype Online 中設定邀請[中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

 **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽窗格上，前往 **[使用者** ，然後按一下清單中所需使用者的顯示名稱。

2. 在音訊 **會議旁邊**，按一下 [ **編輯>**。

3. 在 **[付費號碼** 或 **免付費** 號碼> 下，從下拉式清單中選擇號碼，然後按一下 [ **申請**。

在已採用變更之後，新的預設電話號碼會包含在下次安排新會議的召集人的會議邀請中。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步驟 4 - 使用會議移移服務更新使用者的現有會議邀請 (選項) 

接下來兩個步驟，您必須開始Windows PowerShell。
  
如果您更新了部分或所有使用者的會議邀請中包含的預設電話號碼，您可以選擇更新已寄給貴組織使用者的會議邀請，然後再使用會議移移服務變更其預設電話號碼。 有關其他資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
- 針對在步驟 2 中變更 (使用者) MMS 帳戶執行會議移移服務。 若要這麼做，請執行下列命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 您也可以查看會議移移狀態。 在擱置或進行中狀態中沒有任何作業時，所有會議都會 *重新排期*。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消為會議橋接器未指定服務電話號碼的步驟


當您從會議橋接器取消分配電話號碼時，使用者將無法使用該電話號碼加入任何會議。 由於電話號碼正在變更，因此必須更新所有可能以電話號碼做為預設號碼 (如果有) 的使用者，並更新他們現有的會議邀請，再從音訊會議橋接器未指定電話號碼。

如果移除電話號碼而不更新使用者及其會議，他們現有的會議邀請可能包含無法加入其會議的電話號碼。

在前三個步驟中，您必須開始Windows PowerShell。 若要瞭解如何執行此操作，請按一下 [想要瞭解如何使用[Windows PowerShell？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步驟 1 - 更新電話號碼被未指定為其中一個預設號碼的使用者

為號碼未未指定為預設號碼的所有使用者取代預設付費或免付費號碼，並開始重新排程會議程式。 若要這麼做，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >您也可以在系統管理中心變更預設付費或免付費Microsoft Teams使用者。 不過，這不會自動重新排期他們的會議。 
 
 有關其他資訊，請參閱在 Microsoft Teams 中設定邀請中包含的電話號碼，[或在](set-the-phone-numbers-included-on-invites-in-teams.md)商務用 Skype [Online 中設定商務用 Skype電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > 視貴組織的大小，這可能需要一些時間才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>步驟 2 - 使用 Windows PowerShell

一旦沒有在擱置或進行中狀態中的作業，所有會議都會 *重新* 排期。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

有關會議移移服務的資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步驟 3 - 從音訊會議橋接器取消分配舊電話號碼

使用 Unregister-CsOnlineDialInConferencingServiceNumber Cmdlet 從會議橋接器取消註冊付費或免付費號碼

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```
注意：若要尋找會議橋接器識別碼，請執行下列 PowerShell：Get-CsOnlineDialInConferencing Bridge。


   > [!IMPORTANT]
   > 從音訊會議橋接器中未指定電話號碼之後，使用者就無法再使用電話號碼加入新的或現有的會議。

### <a name="save-time-and-automate"></a>節省時間並自動化

若要自動化此程式以節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlets。

- 使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet 變更特定使用者的預設付費或免付費號碼。

  - 若要變更使用者的預設免付費號碼，請執行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet，根據使用者的原始預設號碼或位置來變更預設的付費或免付費使用者數目。

    > [!NOTE]
    > 若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencing Bridge**。

  - 若要為沒有付費電話號碼的所有使用者設定預設的免付費8005551234，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將所有擁有免費電話號碼的使用者的預設免付費8005551234變更為預設免付費號碼，8005551239並自動重新排定其會議，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要將位於美國的所有使用者的預設免付費號碼設為自動8005551234，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上述使用的位置必須符合使用者在 (中) 的連絡人Microsoft 365 系統管理中心。

## <a name="troubleshooting"></a>疑難排解

**無法使用取消分配按鈕**

您想要取消分配號碼，但該按鈕卻無法使用，如果將游標停留在該號碼上，系統會重新導向您，以下列訊息連連支援人員：「無法從橋接器取消分配預設號碼或共用號碼。」 _若要取消分配專用付費號碼，請聯絡支援人員_。」。

若要取得橋接器和 () 詳細資訊，請執行下列 Powershell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

結果，除了身分識別、名稱和地區等其他資訊之外，也應該包含 DefaultServiceNumber。

**範例**，若要取消分配，DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>關於 Windows PowerShell

有了Windows PowerShell，您可以管理使用者及其目前或不允許執行哪些工作。 Windows PowerShell單一系統管理Microsoft 365或 Office 365 和 商務用 Skype Online，可簡化您的日常工作，尤其是當您有多個工作需要執行時。 若要開始使用Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相關主題
[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)
