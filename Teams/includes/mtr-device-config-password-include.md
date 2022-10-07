
與任何 Microsoft 365 帳戶一樣，新建立的資源帳戶密碼設定為在一段時間後自動到期。 不過，如果資源帳戶密碼過期，其登入的Teams 會議室裝置將無法再次登入到期日。 

若要避免重設資源帳戶的密碼，然後再次登入每個Teams 會議室裝置，您可以關閉帳戶的密碼過期。
  
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
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
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
    
    如需 Active Directory PowerShell 的詳細資料，請參閱 [ActiveDirectory](/powershell/module/activedirectory)。

2. 使用下列語法將密碼設為永不過期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此範例會將帳戶 ConferenceRoom01@contoso.com 的密碼設為永不過期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---