---
title: 設定 Teams Phone Mobile
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
description: 深入瞭解如何設定 Teams Phone Mobile。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f05eeb70808d39b721d1b33ba252c8257433c4a
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584176"
---
# <a name="configure-teams-phone-mobile"></a>設定 Teams Phone Mobile

如需參與Microsoft Teams 電話行動裝置方案的電信業者清單，以及可提供服務的國家或地區，請參閱[Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/teams-phone-mobile)。

本文將說明如何設定 Teams Phone Mobile。 在設定 Teams Phone Mobile 之前，請務必閱讀 Teams [Phone Mobile 方案](operator-connect-mobile-plan.md) ，以取得權益、先決條件和授權的相關資訊。

## <a name="enable-an-operator"></a>啟用運算子

您可以在 Teams 系統管理中心啟用、編輯及移除運算子。 在左側功能窗格中，移至 **[語音>運算子]**。

若要啟用運算子：

1. 選擇支援 Teams Phone Mobile 的電信業者。 在 [ **所有運算子]** 索引標籤下，依地區或服務篩選可用的電信業者，以尋找支援 Teams Phone Mobile 的正確電信業者。 然後選取您要啟用的運算子。

2. 在 [ **運算子設定] 底** 下，選取您要使用所選運算子啟用的國家/地區。

3. **提供連絡資訊。** 您的連絡資訊，包括全名和電子郵件地址，將會自動與您的電信業者共用。 您可以稍後變更這項資訊。 此外，您必須提供公司規模，而且您也可以選擇提供電話號碼。 電信業者會使用此資訊與您連絡，提供更多有關 Teams Phone Mobile 的詳細資料。

4. 接受資料傳輸通知。

5. 選 **取 [新增為我的運算子** ] 以儲存。

## <a name="set-up-phone-numbers"></a>設定電話號碼

如果您想要將現有的公司付費 SIM 卡電話號碼新增至 Teams，請連絡您的電信業者以確保您擁有合格的 Teams Phone Mobile 訂閱，他們就可以將您的號碼上傳至 Teams。 電信業者完成訂單後，您可以將這些數位指派給使用者。 

若要尋找您電信業者的網站，請參閱 [Microsoft 365 Teams Phone Mobile 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

您必須提供您的租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱 [尋找您的 Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id.md)。 如果您的地區和電信業者支援無線語音訂閱，您可能要將現有的電話機號碼或有線號碼移轉到無線語音訂閱。 

設定電話號碼的方式取決於您要為新使用者設定號碼，或是從 Microsoft 通話方案、運算子連線或直接路由移動現有號碼。

- [取得新 Teams 使用者的數位](#acquire-numbers-for-new-teams-users)。  

- [將號碼從通話方案移至 Teams Phone Mobile](#move-numbers-from-calling-plans-to-teams-phone-mobile)。  

- [將號碼從運算子連線移至 Teams Phone Mobile](#move-numbers-from-operator-connect-to-teams-phone-mobile)。  

- [將號碼從直接路由移至 Teams Phone Mobile](#move-numbers-from-direct-routing-to-teams-phone-mobile)。  


### <a name="assign-numbers-to-emergency-addresses"></a>將號碼指派給緊急位址

緊急位址是透過 Microsoft Teams 端點/用戶端存取時，與數位相關聯的靜態位置。 一旦您在 Teams 系統管理中心建立緊急位址，您指派位址或稍後變更位址的方式將取決於您的電信業者。

若要將號碼指派給 Microsoft Teams 端點使用的緊急位址，您的電信業者將會實作下列三種案例的其中之一：

- 運算子會將緊急位址指派給電話號碼，並允許您稍後在 Teams 系統管理中心變更。

- 電信業者不會指派位址，也可讓您將緊急位址指派給 Teams 系統管理中心的電話號碼。

- 運算子會將緊急位址指派給電話號碼，而且不允許您變更。 在此案例中，您需要連絡您的電信業者，對電話號碼及其指派的緊急位址進行變更。

透過啟用 SIM 卡的智慧型手機的原生撥號器撥打電話時，您的電信業者可能會使用地理座標或處理通話的儲存格塔，以大約緊急位置取得協助。

如需緊急電話的詳細資訊，請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md) 和 [規劃及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="acquire-numbers-for-new-teams-users"></a>取得新 Teams 使用者的數位

若要取得新 Teams 使用者的數位，請遵循下列步驟：

1. **指派電話系統授權和 Teams Phone Mobile 附加元件授權。** 您可以從Microsoft 365 系統管理中心或使用 PowerShell 指派電話系統授權和 Teams Phone Mobile 附加元件授權給使用者。 如需詳細資訊，請參閱 [指派 Teams 附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **將透過 Teams Phone Mobile 取得的電話號碼指派的使用者必須處於 TeamsOnly 模式。** 如果您的組織處於 TeamsOnly 模式，則所有使用者都處於 TeamsOnly 模式。 

   若要檢查，請在 Teams 系統管理中心移至 **Teams > Teams 升級設定**。 如果您的組織處於群島模式，請檢查特定使用者是否處於 TeamsOnly 模式。 移至 [ **使用者** ]，然後選取使用者帳戶。 在 [ **帳戶] 索** 引標籤的 **[Teams 升級** ] 底下，共存模式應設定為 TeamsOnly。

3. **取得數位。** 移至您電信業者的網站，或連絡他們以訂購並取得已啟用 Teams Phone Mobile 服務的行動 SIM 卡電話號碼。 

   您的電信業者完成訂單之後，就會將啟用 SIM 卡的行動電話號碼上傳到您的租使用者。 您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 

4. **指派號碼。** 您可以從 Teams 系統管理中心或使用 PowerShell 指派號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>將號碼從通話方案移至 Teams Phone Mobile

1. 確定您有合格的 Microsoft 365 訂閱 Teams Phone Mobile 和 Teams Phone Mobile 附加元件授權。 您必須 [移除個別使用者要移動的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 

2. 請連絡您的電信業者，以啟用 SIM 卡的合格無線語音方案將您的號碼移轉至 Teams Phone Mobile。 

3. 電信業者完成移轉訂單後，您的電信業者會將號碼上傳至您的租使用者。  您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 

4. 您可以使用 Teams 系統管理中心或使用 PowerShell 來指派號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>將號碼從運算子連線到 Teams Phone Mobile

1. 確定您有合格的 Microsoft 365 訂閱 Teams Phone Mobile 和 Teams Phone Mobile 附加元件授權。 您必須 [移除個別使用者要移動的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 請連絡您現有的運算子連線提供者，以移除租使用者的電話號碼。

2. 請連絡您的電信業者，以啟用 SIM 卡的合格無線語音方案將您的號碼移轉至 Teams Phone Mobile。 

3. 電信業者完成移轉訂單後，您的電信業者會將號碼上傳至您的租使用者。 您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 

4. 您可以使用 Teams 系統管理中心或使用 PowerShell 來指派號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>將號碼從直接路由移至 Teams Phone Mobile   

若要將號碼從直接路由移至 Teams Phone Mobile，您必須完成下列步驟：

1. [判斷現有直接路由號碼是否已在線上或內部部署指派](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises)。

2. [將號碼從直接路由移轉到 Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile)。

2. [移除與使用者相關聯的線上語音路由原則](#remove-the-online-voice-routing-policy-associated-with-your-user)。

3. [取得電話號碼](#acquire-phone-numbers)。

4. [指派電話號碼](#assign-phone-numbers)。

下列各節將更詳細描述這些步驟。

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>判斷現有直接路由號碼是否已在線上或內部部署指派。

移除現有直接路由號碼的方式，取決於號碼是內部部署還是線上指派。

1. 首先，執行下列 Teams PowerShell 命令，檢查使用者是否已獲指派直接路由號碼。 NumberType 應該是 DirectRouting：

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. 執行下列 Teams PowerShell 命令，判斷號碼是否已在線上或內部部署指派：

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   如果 OnPremLineUri 已填入 E.164 電話號碼，電話號碼會在內部部署中指派並同步處理至 Microsoft 365。

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>將號碼從直接路由移轉到 Teams Phone Mobile

若要移轉數位，請遵循下列步驟。  

> [!Important]
> 在移轉期間，電話號碼將會退出服務。 開始移轉之前，請先與您的 Teams Phone Mobile 電信業者協調。

- **若要移轉指派給 Teams Phone Mobile 的現有線上直接路由號碼**，請連絡您的電信業者。 若要尋找您電信業者的網站，請參閱 [Microsoft 365 Teams Phone Mobile 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 在同意的日期和時間，您的電信業者會將您的號碼從直接路由移轉到 Teams Phone Mobile。 這可能牽涉到移除從租使用者移轉的電話號碼，然後再次將它新增為與 Teams Phone Mobile 相關聯的新電話號碼。

- **若要將內部部署指派的直接路由號碼移轉到 Teams Phone Mobile**，請執行下列商務用 Skype Server PowerShell 命令：

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  若要檢查內部部署號碼是否已移除，以及變更是否已從內部部署同步至 Microsoft 365，請執行下列 Teams PowerShell 命令：

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

變更同步處理到 Microsoft 365 線上目錄之後，預期的輸出結果為：

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

若要檢查電話號碼是否已移除，請執行下列 Teams PowerShell 命令：

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> 移除程式生效所需的時間取決於您的設定。 移除電話號碼最多可能需要 10 分鐘，在少數情況下，最多可能需要 24 小時。 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>移除與使用者相關聯的線上語音路由原則

取消指派號碼之後，請執行下列 Teams PowerShell 命令，移除與您的使用者相關聯的線上語音路由原則：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>取得電話號碼

請連絡您的電信業者，以啟用 SIM 卡的合格無線語音方案將您的號碼移轉至 Teams Phone Mobile。

您的電信業者完成訂單之後，就會將號碼上傳至您的租使用者。 您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 

#### <a name="assign-phone-numbers"></a>指派電話號碼

您可以使用 Teams 系統管理中心或使用 PowerShell，將 Teams Phone Mobile 號碼指派給使用者。 如需詳細資訊，請參閱 [指派號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。


## <a name="manage-your-operators"></a>管理您的運算子

您可以從 [ **我的運算子]** 索引標籤檢視您的運算子及其狀態，並針對您的選擇進行下列變更：  

- 依國家/地區管理電信業者服務
- 暫停運算子
- 移除運算子

> [!NOTE]
> 移除貴組織或國家/地區的電信業者之前，您必須先移除指派給組織或國家/地區使用者的所有電話號碼，並連絡電信業者以釋出號碼。

## <a name="release-numbers"></a>版本號碼

若要從 Teams 系統管理中心釋出電話號碼，請移至 **[電話號碼]** 頁面並選取號碼。

- 如果電話號碼未指派給使用者，請選取 [ **發行]**。

- 如果電話號碼已指派給使用者，您將需要取消指派號碼。 選取 **[編輯**]，然後 **[移除使用者]**。 儲存變更之後，選取 **[發行]**。

## <a name="manage-user-incoming-calling-policies"></a>管理使用者來電原則

您可以使用 Teams 系統管理中心或使用 PowerShell 來管理使用者的來電原則。 根據預設，Teams Phone Mobile 使用者的來電會先在使用者啟用 SIM 卡的行動裝置上撥打 Teams 應用程式。 

- 如果使用者的來電喜好設定為 Teams 應用程式，所有來電都會同時在啟用 SIM 卡的智慧型手機和任何其他裝置上的 Teams 端點上撥打 Teams 應用程式。 

- 如果使用者的來電喜好設定為原生撥號器，所有來電都會在啟用 SIM 卡的智慧型手機上撥打原生撥號，同時在其他裝置上響鈴所有其他 Teams 端點。 

### <a name="use-the-teams-admin-center"></a>使用 Teams 系統管理中心

若要使用 Teams 系統管理中心管理使用者的來電原則：

1. 在 [語音] 索引標籤底下，選取 **[行動原則]**。 

2. 若要新增新的行動原則，請按一下 [ **新增]**。

3. 選取名稱、新增原則描述，然後從 [ **選取行動撥號器** ] 下拉式清單選項中選擇下列其中一項：

   -  **Microsoft Teams** 會先在啟用 SIM 卡的智慧型手機上撥打 Teams 應用程式。 

   - **原生撥號器** 可先在啟用 SIM 卡的智慧型手機上撥打原生撥號。

4. 將原則指派給使用者。 請參閱 [指派原則](assign-policies-users-and-groups.md)。


### <a name="use-powershell"></a>使用 PowerShell

1. 連線到您的租使用者：Connect-MicrosoftTeams。
 
2. 為來電建立原則，讓原生撥號器或 Teams 應用程式先響鈴。  (您可以選擇原則名稱;此範例使用 TeamsFirst 和 NativeFirst.)  

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. 授與原則給使用者： 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. 檢查使用者原則： 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. 檢查所有行動策略選項： 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








