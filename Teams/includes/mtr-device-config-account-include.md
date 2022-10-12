
每個Microsoft Teams 會議室裝置都需要自己的資源帳戶。 資源帳戶是Teams 會議室裝置登入的帳戶，也是貴組織中使用者邀請預約 Teams 會議室的帳戶。

當您建立資源信箱時，您可以指定是否要允許週期性會議、讓會議室自動接受邀請、未來要幾天接受邀請等等。

> [!TIP]
> 為您的資源帳戶命名時，建議您使用電子郵件地址開頭的標準命名慣例。 這有助於在 Azure Active Directory 中建立動態群組以輕鬆管理。 例如，您可以針對所有與Microsoft Teams 會議室相關聯的資源帳戶使用 「mtr-」。

> [!TIP]
> 建議您使用 Exchange Online 和 Azure Active Directory 建立所有資源帳戶。

使用下列其中一個索引標籤的方法建立資源帳戶：

#### <a name="in-microsoft-365-admin-center"></a>[**在 Microsoft 365 系統管理中心 中**](#tab/m365-admin-center)

1. 登入Microsoft 365 系統管理中心。

2. 為您的 Microsoft 365 租使用者提供系統管理員認證。

3. 移至左側面板中的 [ **資源** ]，然後選 **取 [會議室&設備]**。 如果左側面板中無法使用這些選項，您可能需要先選取 [ **全部顯示]** 。

4. 選取 **[新增資源** ] 以建立新的資源帳戶。 輸入帳戶的顯示名稱和電子郵件地址，然後選取 [ **儲存]**。

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

您可能也需要將頻寬原則或會議原則套用至此帳戶。 您可以在稍後的步驟中設定信箱原則。

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
