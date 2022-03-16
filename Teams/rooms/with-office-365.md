---
title: 為會議室和共用裝置建立Teams帳戶
ms.author: czawideh
author: cazawideh
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請參閱本文，瞭解如何為會議室和共用裝置建立資源帳戶，包括 Microsoft Teams 會議室、Teams 會議室 Surface Hub，以及 Teams 顯示。
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514544"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>為會議室和共用裝置建立Teams帳戶

本文提供為共用空間和裝置建立資源帳戶的步驟，其中包含在 Windows、Android Teams 會議室、Surface Hub 上的 Teams 會議室 和 Teams 上設定 Microsoft Teams 會議室 資源帳戶的步驟。.

Microsoft 365資源帳戶是Teams專用帳戶，例如會議室或投影機。 這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。 例如，如果您有一般資源 ，例如會議室，您可以為會議室設定資源帳戶，根據會議室的日曆可用性，自動接受或拒絕會議邀請。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **商務用 Skype** <br><br>
> 如果您需要啟用資源帳戶以使用商務用 Skype，請參閱使用 Microsoft Teams 會議室[部署商務用 Skype Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>開始之前

### <a name="requirements"></a>需求

視您的環境，您需要一或多個角色來建立資源帳戶。

|**環境**|**必要的角色**|
|-----|-----|
|Azure Active Directory  <br/> |全域系統管理員或使用者系統管理員  <br/> |
|Active Directory  <br/> |Active Directory Enterprise系統管理員、網域系統管理員，或具有建立使用者的委派許可權。 Azure Active Directory 連線同步許可權。  <br/> |
|Exchange Online  <br/> |全域系統管理員或Exchange系統管理員   <br/> |
|Exchange Server  <br/> |Exchange管理或收件者管理   <br/> |

如果您要建立資源帳戶Teams 會議室，UPN 必須與資源帳戶的 SMTP 位址相符。 部署[Microsoft Teams 會議室之前](requirements.md)，請參閱Teams 會議室。

### <a name="what-license-do-you-need"></a>您需要哪些授權？

在建立資源Microsoft 365帳戶之前，請檢查其所需的授權類型：

- **Teams** 會議 如果您想要將資源帳戶與共享裝置建立關聯，例如 Microsoft Teams 會議室或 Teams 顯示器與桌面，並使用它加入 Teams 會議，讓出席者可以使用它來透過該裝置展示視音訊，您需要 會議室 授權。 有關會議室授權詳細資訊，請參閱Teams 會議室[授權](rooms-licensing.md)。

- **PSTN 通話** 如果您希望資源撥打或接聽外部電話號碼 (稱為公用交換電話網絡或 PSTN 通話) ，您需要Microsoft 365 電話系統或Microsoft 365 商務語音授權。 您只需要在下列概觀中完成步驟 1。 接著，請參閱[Microsoft Teams附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)以瞭解更多資訊。

- &mdash; &mdash; 如果您只使用資源帳戶來預約資源，請邀請資源加入您的會議，並自動接受或拒絕邀請，而您不需要指派授權給資源帳戶，而且您只需要完成下列概觀中的步驟 1。  

## <a name="overview"></a>概觀

**步驟 1 -** [建立新資源帳戶](#create-a-resource-account)。 或者，如果會議室信箱已存在，而您想要將它轉換成資源帳戶，您可以修改會議室信箱Exchange[現有的信箱](?tabs=existing-account#create-a-resource-account)。

**步驟 2 -** 接著，[將您的帳戶設定為](#configure-mailbox-properties)Teams會議。

**步驟 3 -** 如果資源帳戶要與共享裝置關聯，例如使用Teams顯示，請關閉 [密碼到期](#turn-off-password-expiration)。

**步驟 4 -** 最後，[指派會議室授權](#assign-a-meeting-room-license)，讓帳戶能夠存取Microsoft Teams。

建立及設定資源帳戶之後，請參閱下一[](#next-steps)個步驟，以檢查其他設定工作，包括通訊群組、網路功能及通話。

## <a name="create-a-resource-account"></a>建立資源帳戶

> [!TIP]
> 為資源帳戶命名時，建議您使用電子郵件地址開頭的標準命名慣例。 這有助於建立動態群組，以輕鬆管理Azure Active Directory。 例如，您可以針對所有與 Microsoft Teams 會議室 相關聯的資源帳戶使用 "一Microsoft Teams 會議室。

> [!TIP]
> 我們建議您使用 Exchange Online 和 Azure Active Directory。

使用下列其中一個選項卡的方法建立資源帳戶：

#### <a name="in-microsoft-365-admin-center"></a>[**在 Microsoft 365 系統管理中心**](#tab/m365-admin-center)

1. 請登錄Microsoft 365 系統管理中心。

2. 為您的租使用者提供Microsoft 365認證。

3. 前往左側 **面板** 中的資源，然後選取會議室 **&設備**。 如果左側面板中沒有這些選項，您可能需要先選取 **顯示** 全部。

4. 選取 **新增資源信箱** 以建立新的會議室帳戶。 輸入帳戶的顯示名稱和電子郵件地址，**選取新增，****然後選取關閉**。

5. 根據預設，資源帳戶會設定為下列設定：

    - 允許重複會議
    - 自動拒絕下列限制以外的會議
      - 預約視窗 (天) ：180
      - 最長 (小時) ：24
    - 自動接受會議邀請

    如果您想要變更，請在選取關閉之前，先選取設定排 **程選項**。 如果您想要稍後變更，請前往 **ResourcesRooms**  >  **&設備，** 選取資源帳戶。 接著，在 **預約選項** 下，選取 **編輯**。

6. 前往 **UsersActive**  >  **使用者**，然後選取您建立聊天室以開啟屬性面板。

7. 接下來，將密碼指派給資源帳戶。 在面板中，選取重 **設密碼**。
 
8. 要求使用者在共用裝置上變更密碼會造成登錄問題。 取消 **選取請此使用者第一次登錄時變更其密碼**，然後選取重 **設**。

9. In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed. 然後選取您想要指派授權 ，例如會議室，然後選取儲存 **變更**。 授權可能會視貴組織而異。

若要變更資源信箱的設定，請參閱設定信箱[屬性](#configure-mailbox-properties)或使用 Exchange管理中心。

您可能也需要將頻寬原則或會議原則適用于此帳戶。 請參閱 [下一個步驟](#next-steps) 以瞭解更多資訊。

#### <a name="with-exchange-online"></a>[**使用 Exchange Online**](#tab/exchange-online)

1. 連線[PowerShell Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 根據預設，會議室信箱沒有關聯的帳戶。 當您建立會議室信箱時，請新增帳戶，以便使用 Microsoft Teams。

    如果您要建立新資源信箱：
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    此範例會使用下列設定來建立新會議室信箱：

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

如果您不是使用混合式Exchange，您可以繼續下一個步驟，即設定[信箱屬性](#configure-mailbox-properties)。

如果您採用混合式Exchange，您必須為您的內部部署網域帳戶新增電子郵件地址。 請參閱[同步處理內部部署Office 365使用者帳戶目錄以](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)瞭解更多資訊。

#### <a name="with-exchange-server"></a>[**使用 Exchange Server**](#tab/exchange-server)

  1. 連線管理Exchange命令命令。 [開啟 Exchange管理命令殼](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或使用[遠端 PowerShell Exchange伺服器。](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

   2. 若要建立新會議室信箱：

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   此範例會使用下列設定來建立新會議室信箱：

   - 帳戶：ConferenceRoom01@contoso.com
  
   - 名稱：ConferenceRoom01

   - 別名：ConferenceRoom01

   - 帳戶密碼：P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**修改現有的會議室Exchange信箱**](#tab/existing-account)

若要修改現有的會議室信箱以成為資源帳戶，請使用下列語法：

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

此範例啟用具有別名值 ConferenceRoom02 的現有會議室信箱的帳戶，並且將密碼設定為 9898P@$$W 0rd。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

如果您採用混合式Exchange，您也需要為您的內部部署網域帳戶新增電子郵件地址。 請參閱[同步處理內部部署Office 365使用者帳戶目錄以](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)瞭解更多資訊。

有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果您要為帳戶上的聊天室Teams此Surface Hub，您也應該在此帳戶上啟用 ActiveSync。 這樣一來，您就可以直接從 Surface Hub 傳送電子郵件，這可用於 Whiteboard 等功能。 如需[深入瞭解，請參閱將 ActiveSync 原則 (Surface Hub) ](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)裝置帳戶。

---

> [!IMPORTANT]
> 如果您只使用此資源帳戶來預約空間，並自動接受或拒絕邀請，表示您已完成設定。 如果您使用此資源帳戶進行 PSTN 通話，[請參閱](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)Microsoft Teams附加元件授權，以決定它所需的授權。
>
> 只有在資源帳戶適用于 Windows Teams 會議室、android Teams 會議室、Teams 會議室 Surface Hub 上的 Teams 會議室 或具有Teams 桌面的 Teams 顯示時，才能繼續下一節。

## <a name="configure-mailbox-properties"></a>設定信箱屬性

在 Exchange PowerShell 中，無論是線上或內部部署，在會議室信箱上設定下列設定以改善會議體驗：

- **自動化處理： `AutoAccept`** 會議召集人可以直接收到會議室預約決定，而不需要人為介入。

- **AddOrganizerToSubject： `$false`** 會議召集人不會新增到會議要求的主題中。

- **DeleteComments： `$false`** 在傳入會議要求的郵件內文保留任何文字。 這是處理外部會議Teams協力廠商會議所必須的，才能提供 One Touch Join 體驗。

- **DeleteSubject： `$false`** 保留傳入會議要求的主題。

- **ProcessExternalMeetingMessages： `$true`** 指定是否要處理來自組織外部的會議Exchange要求。 外部會議Teams[協力廠商會議。](/microsoftteams/rooms/third-party-join)

- **RemovePrivateProperty： `$false`** 確保會議召集人在原始會議要求中所送出的私人標號維持為指定的狀態。

- **AddAdditionalResponse： `$true`** 額外Response 參數指定的文字會新加到會議要求中。

- **其他Response：「這是Microsoft Teams會議室！** 要新增到會議接受回應的其他文字。

此範例在名為 ConferenceRoom01 的會議室信箱上設定這些設定：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

## <a name="turn-off-password-expiration"></a>關閉密碼到期

如果資源帳戶密碼過期，裝置在到期日之後不會登錄。 然後必須變更資源帳戶的密碼，然後在每個裝置上更新密碼。 若要避免這種情況，您可以關閉密碼到期。
  
> [!NOTE]
> 設定 **密碼永不過期** 是共用裝置Microsoft Teams要求。 如果您的網域規則禁止密碼不會過期，您必須為每個裝置資源帳戶Teams例外。

請遵循下列其中一個選項卡中的步驟來關閉密碼到期：

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

首先，連線 Active Directory PowerShell：

```PowerShell
   Connect-AzureAD
```

接著，請參閱 [設定密碼永不過期](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire)。

此範例設定帳戶的密碼 ConferenceRoom01@contoso.com 永不過期。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 連線 MSOnline PowerShell：

       ```PowerShell
       Connect-MsolService
       ```

       有關 Active Directory 的詳細資訊，請參閱[Azure Active Directory (MSOnline) ](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

2. 使用下列語法將密碼設為永不過期：

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此範例設定帳戶的密碼 ConferenceRoom01@contoso.com 永不過期。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (內部部署)**](#tab/active-directory1-password/)

1. 連線 Active Directory PowerShell：

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    有關 Active Directory PowerShell 的詳細資訊，請參閱 [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps)。

2. 使用下列語法將密碼設為永不過期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此範例設定帳戶的密碼 ConferenceRoom01@contoso.com 永不過期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>指派會議室授權

資源帳戶需要授權Microsoft 365或Office 365才能Microsoft Teams。

> [!NOTE]
> Microsoft Teams 會議室標準版和Microsoft Teams 會議室進階版共用會議室裝置 ，包括 Teams 會議室。 使用桌面Teams時，需要會議室授權。 詳細資訊，請參閱Teams[會議室授權](rooms-licensing.md)。

若要使用授權指派Microsoft 365 系統管理中心，請參閱[指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。 若要使用 Azure AD指派授權，請參閱下列其中一個選項卡：

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. 連線Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     有關 Active Directory 的詳細資訊，請參閱[Azure Active Directory PowerShell Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0)。
    
2. 使用 Cmdlet 將 `Set-AzureADUser` 使用量位置指派給資源帳戶。 這決定可以使用哪些授權 SKUs。

    在此範例中，使用者位於美國 (美國) ：

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 然後，用於 `Get-AzureADSubscribedSku` 為貴組織或組織Microsoft 365 SKus Office 365清單。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 若要指派授權， `Set-AzureADUser` 請使用 Cmdlet，並將授權 SKU 識別碼 (步驟 2) PowerShell 授權類型物件。 然後，將該物件指派給資源帳戶。 在下列範例中，授權 SKU 識別碼為 6070a4c8-34c6-4937-8dfb-39bbc6397a60，且已指派給帳戶 conferenceroom01@contoso.com：

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

1. 連線 MSOnline PowerShell。

   ```PowerShell
   Connect-MsolService
   ```

    有關 Active Directory 的詳細資訊，請參閱[AZURE ACTIVE DIRECTORY (MSOnline) 。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  使用 Cmdlet 將 `Set-MsolUser` 使用量位置指派給資源帳戶。 這決定可以使用哪些授權 SKUs。

    在此範例中，使用者位於美國 (美國) 。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    然後，您可以使用來 `Get-MsolAccountSku` 為組織或組織Microsoft 365可用的 SKus Office 365清單。

4. 若要指派授權，請使用 `Set-MsolUser` Cmdlet。 在此範例中，「contoso：MEETING_ROOM」授權會指派給帳戶 conferenceroom01@contoso.com：

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

若要驗證帳戶建立和授權指派，請Teams您建立的帳戶來登錄任何用戶端。

## <a name="next-steps"></a>後續步驟

### <a name="network-and-bandwidth"></a>網路和頻寬

您可能需要將自訂網路、頻寬或會議原則適用于此帳戶。 有關網路和頻寬政策詳細資訊，請參閱音訊和視& [設定](/microsoftteams/meeting-policies-audio-and-video)。 針對Teams 會議室，建議您將會議策略頻寬設定為 10 Mbps。

為了共同合作，請開啟PowerPoint、白板和共用筆記。 您可能會想要建立會議策略，以調整參與者和來賓Teams 會議室。 例如，請閱閱大廳設定，例如哪些出席者會自動准許會議。 有關會議Teams，請參閱[管理會議Microsoft Teams](/microsoftteams/meeting-policies-overview)。

### <a name="calling"></a>通話

使用資源帳戶啟用通話沒有唯一的需求。 您啟用資源帳戶進行通話的方式與啟用一般使用者的方式相同。

> [!NOTE]
> 建議您將通話策略指派給裝置資源帳戶，以關閉共用裝置語音信箱。 請參閱[在電話Teams](../teams-calling-policy.md)呼叫和呼叫轉Teams以瞭解更多資訊。

### <a name="configure-distribution-groups"></a>設定通訊群組

若要組織會議室位置，您可以將裝置資源帳戶新Exchange通訊群組。 例如，如果您在三個不同的地理位置設有辦公室，您可以建立三個通訊群組，並為每個位置新增適當的資源帳戶。 若要詳細資訊，請參閱 [建立會議室清單](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list)。

## <a name="related-articles"></a>相關文章

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
