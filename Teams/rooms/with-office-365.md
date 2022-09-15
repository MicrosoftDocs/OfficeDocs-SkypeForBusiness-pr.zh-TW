---
title: 建立會議室和共用 Teams 裝置的資源帳戶
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本文，瞭解如何建立會議室和共用裝置的資源帳戶，包括Microsoft Teams 會議室、Surface Hub 上的Teams 會議室，以及 Teams 的快捷方式顯示器。
ms.openlocfilehash: 213cd2019aa23c296706c70a66e3e873f7527ee9
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706630"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>建立及設定會議室和共用 Teams 裝置的資源帳戶

本文提供針對共用空間和裝置建立資源帳戶的步驟，其中包含在 Windows 上設定Microsoft Teams 會議室的資源帳戶、在 Android 上Teams 會議室、在 Surface Hub 上Teams 會議室，以及在 Teams 顯示器上設定快捷方式的步驟。

Microsoft 365 資源帳戶是專用於特定資源的信箱和 Teams 帳戶，例如會議室或投影機。 這些資源帳戶可以使用您在建立時定義的規則自動回應會議邀請。 例如，如果您有會議室等一般資源，您可以為該會議室設定資源帳戶，該會議室會根據其行事曆可用性自動接受或拒絕會議邀請。 

每個資源帳戶在單一Microsoft Teams 會議室安裝或 Teams 顯示快捷方式實作中都是唯一的。

> [!NOTE]
> 如果使用 Microsoft Teams 面板，Teams 會議室資源帳戶會同時登入Teams 會議室和關聯的 Teams 面板。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **商務用 Skype** <br><br>
> 如果您需要啟用資源帳戶來處理商務用 Skype，請參閱[使用 商務用 Skype Server 部署Microsoft Teams 會議室](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>開始之前

### <a name="requirements"></a>需求

視您的環境而定，您需要一或多個角色才能建立資源帳戶。

|**環境**|**必要角色**|
|-----|-----|
|Azure Active Directory  <br/> |全域系統管理員或使用者系統管理員  <br/> |
|Active Directory  <br/> |Active Directory 企業版系統管理員、網域系統管理員或具有建立使用者的委派許可權。 Azure Active Directory Connect 同步處理許可權。  <br/> |
|Exchange Online  <br/> |全域系統管理員或 Exchange 系統管理員   <br/> |
|Exchange Server  <br/> |Exchange 組織管理或收件者管理   <br/> |

如果您要為Teams 會議室建立資源帳戶，UPN 必須符合資源帳戶的 SMTP 位址。 部署Teams 會議室之前，請參閱[Microsoft Teams 會議室需求](requirements.md)。

### <a name="what-license-do-you-need"></a>您需要什麼授權？

在您建立 Microsoft 365 資源帳戶之前，請先查看它需要哪種授權：

- **Teams 會議** 如果您想要建立資源帳戶與共享裝置的關聯，例如 Microsoft Teams 會議室或 Teams 顯示器與快捷桌會議，並使用它來加入 Teams 會議，讓出席者可以使用它來透過它呈現視訊和音訊，您需要會議室授權。 如需有關會議室授權的詳細資訊，請參閱 [Teams 會議室授權](rooms-licensing.md)。

- **PSTN 通話** 如果您希望資源撥打或接聽外部電話號碼的電話， (稱為公用交換電話網路或 PSTN 通話) ，您需要 Microsoft 365 電話系統或Microsoft 365 商務語音授權。 您只需要完成下列概觀中的步驟 1。 然後，如需詳細資訊，請參閱 [Microsoft Teams 附加](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 元件授權。

- 如果您只使用資源帳戶預約資源，請邀請資源 &mdash; 加入會議，並讓資源自動接受或拒絕您不需要指派授權給資源帳戶的邀請 &mdash; ，而且您只需要完成下列概觀中的步驟 1。  

## <a name="overview"></a>概觀

**步驟 1 -** [建立新的資源帳戶](#create-a-resource-account)。 或者，如果會議室信箱已經存在，而您想要將其轉換為資源帳戶，您可以 [修改現有的 Exchange 會議室信箱](?tabs=existing-account#create-a-resource-account)。

**步驟 2 -**  然後， [設定您的 Teams 會議帳戶](#configure-mailbox-properties) 。

**步驟 3 -**  如果資源帳戶要與共享裝置相關聯，例如 Teams 會顯示快捷方式， [請關閉密碼到期日](#turn-off-password-expiration)。

**步驟 4 -**  最後， [指派會議室授權](#assign-a-meeting-room-license) ，讓帳戶可以存取 Microsoft Teams。

建立及設定資源帳戶之後，請參閱 [後續步驟](#next-steps) 以檢閱其他設定工作，包括通訊群組、網路功能和通話。

## <a name="create-a-resource-account"></a>建立資源帳戶

> [!TIP]
> 為您的資源帳戶命名時，建議您使用電子郵件地址開頭的標準命名慣例。 這有助於在 Azure Active Directory 中建立動態群組以輕鬆管理。 例如，您可以針對所有與Microsoft Teams 會議室相關聯的資源帳戶使用 「mtr-」。

> [!TIP]
> 建議您使用 Exchange Online 和 Azure Active Directory 建立所有資源帳戶。

使用下列其中一個索引標籤的方法建立資源帳戶：

#### <a name="in-microsoft-365-admin-center"></a>[**在 Microsoft 365 系統管理中心 中**](#tab/m365-admin-center)

1. 登入Microsoft 365 系統管理中心。

2. 為您的 Microsoft 365 租使用者提供系統管理員認證。

3. 移至左側面板中的 [ **資源** ]，然後選 **取 [會議室&設備]**。 如果左側面板中無法使用這些選項，您可能需要先選取 [ **全部顯示]** 。

4. 選取 **[新增資源** ] 以建立新的聊天室帳戶。 輸入帳戶的顯示名稱和電子郵件地址，選取 [ **新增**]，然後選取 [ **關閉]**。

5. 根據預設，資源帳戶是使用下列設定來設定：

    - 允許重複會議
    - 自動拒絕超出下列限制的會議
      - )  (天預約視窗：180
      - 工期 (小時) ：24
    - 自動接受會議邀請

    如果您想要變更它們，請在選取 **[關閉**] 前選取 **[編輯預約選項**]。 如果您之後想要變更它們，請移至 [**資源**  >  **會議室] &設備**，選取資源帳戶。 然後在 **[Booking 選項]** 底下，選取 **[編輯]**。

6. 移至 **[使用者**  >  **作用中使用者]**，然後選取您建立的會議室以開啟 [內容] 面板。

7. 接下來，將密碼指派給資源帳戶。 在面板中，選取 **[重設密碼]**。
 
8. 要求使用者變更共用裝置上的密碼會導致登入問題。 取消核取 **[要求此使用者在第一次登入時變更他們的密碼**]，然後選取 [ **重設密碼]**。

9. 在 [ **授權與應用程式]** 區段中，將 **[選取位置** ] 設定為要安裝裝置所在的國家或地區。 然後選取您要指派的授權，例如 [會議室]，然後選取 [ **儲存變更]**。 授權可能會因貴組織而異。

若要變更資源信箱的設定，請參閱 [設定信箱屬性](#configure-mailbox-properties) 或使用 Exchange 系統管理中心。

您可能也需要將頻寬原則或會議原則套用至此帳戶。 如需詳細資訊，請參閱 [後續步驟](#next-steps) 。

#### <a name="with-exchange-online"></a>[**使用 Exchange Online**](#tab/exchange-online)

1. 聯[機至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 根據預設，會議室信箱沒有相關聯的帳戶。 當您建立會議室信箱，以便透過 Microsoft Teams 進行驗證時，請新增帳戶。

    如果您要建立新的資源信箱：
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    此範例會建立具有下列設定的新會議室信箱：

    - 帳戶：ConferenceRoom01@contoso.com
          
    - 名稱：ConferenceRoom01
        
     - 別名：ConferenceRoom01
        
     - 帳戶密碼：P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

如果您不是使用 Exchange 混合式設定，則可以繼續下一個步驟： [設定信箱屬性](#configure-mailbox-properties)。

如果您使用的是 Exchange 混合式設定，您必須為內部部署網域帳戶新增電子郵件地址。 如需詳細資訊，請參閱[同步處理內部部署和Office 365使用者帳戶目錄](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

#### <a name="with-exchange-server"></a>[**使用 Exchange Server**](#tab/exchange-server)

  1. 連線到 Exchange 管理命令介面。 [開啟 Exchange 管理命令介面](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ，或 [使用遠端 PowerShell 連線到您的 Exchange 伺服器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

   2. 若要建立新的會議室信箱：

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   此範例會建立具有下列設定的新會議室信箱：

   - 帳戶：ConferenceRoom01@contoso.com
  
   - 名稱：ConferenceRoom01

   - 別名：ConferenceRoom01

   - 帳戶密碼：P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**修改現有的 Exchange 會議室信箱**](#tab/existing-account)

若要修改現有的會議室信箱以成為資源帳戶，請使用下列語法：

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

此範例會針對具有「ConferenceRoom02」別名值的現有會議室信箱啟用帳戶，並將密碼設為 9898P@$$W 0rd。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

如果您使用的是 Exchange 混合式設定，您也需要為內部部署網域帳戶新增電子郵件地址。 如需詳細資訊，請參閱[同步處理內部部署和Office 365使用者帳戶目錄](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

如需詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果您要在 Surface Hub 上為 Teams 會議室建立此帳戶，您也應該在此帳戶上啟用 ActiveSync。 這可讓您直接從 Surface Hub 傳送電子郵件，以便用於白板等功能。 若要深入瞭解，請參閱 [將 ActiveSync 原則套用至 Surface Hub (裝置帳戶) ](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) 。

---

> [!IMPORTANT]
> 如果您只使用此資源帳戶預約空間，並自動接受或拒絕邀請，表示您已完成設定。 如果您使用此資源帳戶進行 PSTN 通話，請參閱 [Microsoft Teams 附加](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 元件授權以判斷它需要哪些授權。
>
> 只有當資源帳戶用於 Windows 上的Teams 會議室、Android 上的Teams 會議室、Surface Hub 上的Teams 會議室，或是使用桌上型電腦的 Teams 顯示器時，才能繼續下一節。

## <a name="configure-mailbox-properties"></a>設定信箱屬性

在 Exchange PowerShell 中，無論是線上或內部部署，請在會議室信箱上設定下列設定，以改善會議體驗：

- **AutomateProcessing： `AutoAccept`** 會議召集人會直接收到會議室保留決定，而不需要人為介入。

- **AddOrganizerToSubject： `$false`** 會議召集人不會新增至會議邀請的主旨。

- **DeleteComments： `$false`** 在內送會議邀請的郵件內文中保留任何文字。 這需要處理外部 Teams 和協力廠商會議，以提供 One Touch Join 體驗。

- **DeleteSubject： `$false`** 保留內送會議邀請的主旨。

- **ProcessExternalMeetingMessages： `$true`** 指定是否要處理來自 Exchange 組織外部的會議邀請。 外部 Teams 會議和第 [三方會議是必要的](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty： `$false`** 確保會議召集人傳送至原始會議邀請中的私人標幟維持指定。

- **AddAdditionalResponse： `$true`** AdditionalResponse 參數所指定的文字會新增至會議邀請。

- **AdditionalResponse：「這是 Microsoft Teams 會議室！」** 要新增至會議接受回復的其他文字。

此範例會在名為 ConferenceRoom01 的會議室信箱上設定這些設定：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

如需詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

## <a name="turn-off-password-expiration"></a>關閉密碼到期

如果資源帳戶密碼過期，裝置就不會在到期日之後登入。 之後就必須變更資源帳戶的密碼，然後在每個裝置上更新密碼。 若要避免此問題，您可以關閉密碼過期。
  
> [!NOTE]
> 設定 **密碼永不過期** 是共用 Microsoft Teams 裝置的需求。 如果您的網域規則禁止密碼未過期，您必須為每個 Teams 裝置資源帳戶建立例外狀況。

請依照下列其中一個索引標籤中的步驟關閉密碼到期：

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

首先，連線到 Active Directory PowerShell：

```PowerShell
   Connect-AzureAD
```

然後，請參閱 [設定永不過期的密碼](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire)。

此範例會將帳戶 ConferenceRoom01@contoso.com 的密碼設為永不過期。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 連線至 MSOnline PowerShell：

       ```PowerShell
       Connect-MsolService
       ```

       如需 Active Directory 的詳細資料，請參閱 [Azure Active Directory (MSOnline) ](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)。

2. 使用下列語法將密碼設為永不過期：

    ```PowerShell
    Set-MsolUser -UserPrincipalName <userPrincipalName> -PasswordNeverExpires $true
    ```

    此範例會將帳戶 ConferenceRoom01@contoso.com 的密碼設為永不過期。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (內部部署)**](#tab/active-directory1-password/)

1. 連線到 Active Directory PowerShell：

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    如需 Active Directory PowerShell 的詳細資料，請參閱 [ActiveDirectory](/powershell/module/activedirectory/)。

2. 使用下列語法將密碼設為永不過期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此範例會將帳戶 ConferenceRoom01@contoso.com 的密碼設為永不過期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>指派會議室授權

資源帳戶需要 Microsoft 365 或Office 365授權才能登入 Microsoft Teams。

> [!NOTE]
> Microsoft Teams 會議室 Basic 和 Microsoft Teams 會議室 Pro 是共用會議室裝置的兩種可用 SKU，包括Teams 會議室。 具有桌面功能的 Teams 顯示器需要會議室授權。 如需詳細資訊，請[參閱Microsoft Teams 會議室授權](rooms-licensing.md)。

若要使用Microsoft 365 系統管理中心指派授權，請參閱[指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。 若要使用 Azure AD 指派授權，請參閱下列其中一個索引標籤：

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. 連線至 Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     如需 Active Directory 的詳細資料，請參閱 [適用于圖形的 Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0&preserve-view=true)。
    
2. 使用 `Set-AzureADUser` Cmdlet 將使用位置指派給您的資源帳戶。 這會決定可用的授權 SKU。

    在此範例中，使用者位於 美國 (US) ：

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 然後，用來 `Get-AzureADSubscribedSku` 擷取 Microsoft 365 或Office 365組織的可用 SKU 清單。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 若要指派授權，請使用 `Set-AzureADUser` Cmdlet，並將授權 SKU ID 轉換 (請參閱步驟 2) 成 PowerShell 授權類型物件。 然後，將該物件指派給資源帳戶。 在下列範例中，授權 SKU ID 為 6070a4c8-34c6-4937-8dfb-39bbc6397a60，且已指派給帳戶 conferenceroom01@contoso.com：

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. 連線至 MSOnline PowerShell。

   ```PowerShell
   Connect-MsolService
   ```

    如需 Active Directory 的詳細資料，請參閱 [Azure Active Directory (MSOnline) 。](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)

2.  使用 `Set-MsolUser` Cmdlet 將使用位置指派給您的資源帳戶。 這會決定可用的授權 SKU。

    在此範例中，使用者位於美國 (美式) 。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    接著，您可以用來 `Get-MsolAccountSku` 擷取 Microsoft 365 或Office 365組織的可用 SKU 清單。

4. 若要指派授權，請使用 `Set-MsolUser` Cmdlet。 在此範例中，「contoso：MEETING_ROOM」授權已指派給帳戶 conferenceroom01@contoso.com：

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

若要驗證帳戶建立和授權指派，請使用您建立的帳戶登入任何 Teams 用戶端。

## <a name="next-steps"></a>後續步驟

### <a name="meeting-policies"></a>會議原則

您可能需要將自訂網路、頻寬或會議原則套用至此帳戶。 如需網路和頻寬原則的詳細資訊，請參閱 [音訊&視訊的會議原則設定](/microsoftteams/meeting-policies-audio-and-video)。 針對Teams 會議室，建議您將會議原則頻寬設定為 10 Mbps。

基於共同作業目的，請開啟PowerPoint Live、白板和共用筆記。 建議您啟用會議原則設定「立即在私人會議中開會」。 您可能會想要建立會議原則來調整Teams 會議室的參與者和來賓設定。 例如，檢閱大廳設定，例如哪些出席者自動准許會議。 如需 Teams 會議原則的詳細資訊，請參閱 [管理 Microsoft Teams 中的會議原則](/microsoftteams/meeting-policies-overview)。

### <a name="calling"></a>通話

啟用資源帳戶通話沒有唯一的需求。 您啟用資源帳戶的通話方式，與啟用一般使用者的方式相同。

> [!NOTE]
> 我們建議您將通話原則指派給裝置資源帳戶，藉此關閉共用裝置的語音信箱。 如需詳細資訊，請參閱 [Teams 中的通話和來電轉接](../teams-calling-policy.md) 。

### <a name="configure-distribution-groups-for-teams-calendar"></a>設定 Teams 行事曆的通訊群組

若要整理會議室位置，您可以將裝置資源帳戶新增至 Exchange 通訊群組。 例如，如果您在三個不同的地理位置設有辦公室，您可以建立三個通訊群組，並將適當的資源帳戶新增至每個位置。 如需詳細資訊，請參閱 [建立會議室清單](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list)。

### <a name="configure-places-for-outlook-calendar"></a>設定Outlook 行事曆地點
若要讓會議室位置顯示在 Outlook 會議室尋找工具中，您必須使用 exchange PowerShell Cmdlet Set-Place。 Set-Place不只填入 Outlook 中的 [會議室尋找工具]，還可讓您新增額外的中繼資料，例如會議室的容量或建置會議室的樓層。 如需詳細資訊，請參閱 [設定位置](/powershell/module/exchange/set-place)。

## <a name="related-articles"></a>相關文章

[設定Microsoft Teams 會議室帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
