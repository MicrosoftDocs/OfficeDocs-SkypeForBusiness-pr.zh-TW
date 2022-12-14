在 Microsoft Teams 中，每個自動語音應答或通話佇列都需要資源帳戶。 資源帳戶也可能會被指派電話號碼。 您可以將電話號碼指派給自動語音應答和通話佇列，讓 Teams 外部的來電者可以連線到自動語音應答或通話佇列。

本文說明如何建立資源帳戶，並準備好搭配自動語音應答和通話佇列使用。

在開始執行本文中的程式之前，請確定您已執行下列步驟：

- [取得Microsoft Teams 電話資源帳戶授權](#obtain-microsoft-teams-phone-resource-account-licenses)
- [取得電話號碼](#obtain-phone-numbers)

> [!NOTE]
> 用於自動語音應答和通話佇列的資源帳戶在登入時會停用，而且必須維持不變。 這些帳戶無法使用聊天和目前狀態。

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>取得Microsoft Teams 電話資源帳戶授權

每個資源帳戶都需要授權，才能使用自動語音應答和通話佇列，稱為 **Microsoft Teams 電話資源帳戶** 授權。 使用 Teams Phone 的訂閱會自動獲得 **Microsoft Teams 電話資源帳戶** 授權的免費配置，如果需要更多授權，也可以購買額外的 **Microsoft Teams 電話資源帳戶** 授權。 如需如何取得這些授權的詳細資訊，請[參閱Microsoft Teams 電話資源帳戶授權]](../teams-add-on-licensing/virtual-user.md)。

本文稍後將說明如何 [指派授權給資源帳戶](#assign-a-license)。

如果您購買 **Teams 電話標準方案** 或 **Teams Phone 搭配通話方案** 套件組合授權，**Teams 電話資源帳戶** 授權已在您的帳戶中。

若要查看您是否已擁有 **Teams Phone 資源帳戶** 授權，請使用具有全域系統管理員許可權 [的帳戶登入Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。 然後，移至 [[帳單>您的產品]](https://admin.microsoft.com/Adminportal/Home#/subscriptions)。 如果您有 **Teams Phone 資源帳戶** 授權，這些授權會顯示為 **Microsoft Teams 電話資源帳戶]**。

1. 開[啟Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，並以全域系統管理員的使用者登入。這通常是您用來註冊 Microsoft 365 的帳戶。
2. 在左側功能窗格中，移至 [**帳單**  >  **購買服務**](https://admin.microsoft.com/Adminportal/Home#/catalog)  >  **附加元件**  >  **查看所有附加元件產品**。
3. 捲動到結尾以尋找 **Microsoft Teams 電話資源帳戶** 授權。 選取 **[詳細資料**]，然後選取 **[購買]**。
4. 在授權購買頁面上，選取您想要的授權數目。 您需要針對您計畫設定的每個自動語音應答和通話佇列設定一個授權。 我們建議您選取至少五個授權，以便日後輕鬆設定更多自動語音應答和通話佇列，而不需要立即購買更多授權。
5. 取消核取 **[自動指派給所有沒有授權的使用者]**。
6. 選 **取 [立即取出]**。
7. 確認您的訂單，選取 **[下一步**]，然後 **選取 [下單]**。

費用為零，但您仍需依照下列步驟取得授權。

### <a name="obtain-phone-numbers"></a>取得電話號碼

自動語音應答和通話佇列的電話號碼是選用的。 對於任何您想要直接透過電話號碼連線的自動語音應答或通話佇列，您必須擁有具有相關聯電話號碼的資源帳戶。

資源帳戶可以使用付費或免付費電話號碼。 您可以向其他電信業者要求新的號碼或移轉現有的號碼。

可套用至資源帳戶的可接受電話號碼包括：

- **通話方案服務號碼：** 若要使用通話方案取得服務號碼，請參閱 [取得服務電話號碼](../getting-service-phone-numbers.md)。
- **直接路由號碼：** 若要取得直接路由號碼，請參閱 [啟用使用者直接路由](/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice)。
- **運算子連接號碼：** 若要取得運算子連接號碼，請參閱 [設定運算子連線](/microsoftteams/operator-connect-configure#set-up-phone-numbers)。

若要從其他電信業者移轉號碼，請參閱 [將電話號碼移轉至 Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

## <a name="create-a-resource-account"></a>建立資源帳戶

您可以在 Teams 系統管理中心建立資源帳戶。

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。 
2. 展開 **[語音**]，然後選取 [ **資源帳戶]**。
3. 選取 [新增 **]**。
4. 在 [ **新增資源帳戶]** 窗格中，填寫 **[顯示名稱**]、[ **使用者名稱**] 和 [ **資源] 帳戶類型**。 資源帳戶類型可以是 **自動語音應答** 或 **通話佇列**，視您使用此資源帳戶的方式而定。
5. 選取 [儲存 **]**。

## <a name="assign-a-license"></a>指派授權

針對每個資源帳戶，您必須指派 **Microsoft Teams 電話資源帳戶** 授權。

1. 登入[Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。 
2. 展開 **[使用者**]，然後選取 [ **作用中的使用者]**。
3. 選取您要指派授權的資源帳戶。 資源帳戶的使用者窗格隨即出現。
4. 在 [**授權與應用程式] 索** 引標籤 **的 [授權] 底** 下，選 **取 [Microsoft Teams 電話資源帳戶]**。
5. 選 **取 [儲存變更]**。

## <a name="assign-a-phone-number"></a>指派電話號碼

如果您打算使用資源帳戶搭配需要電話號碼的自動語音應答或通話佇列，請將號碼指派給資源帳戶。

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。
2. 展開 **[語音**]，然後選取 [ **資源帳戶]** 頁面。
3. 選取您要指派電話號碼的資源帳戶，然後選取 **[指派/取消指派]**。
4. 在 **[電話號碼類型]** 下拉式清單中，選擇您要使用的號碼類型。
5. 在 [ **已指派的電話號碼] 方** 塊中，搜尋您要使用的號碼，然後選取 [ **新增]**。 請務必包含國碼 (例如 +1 250 555 0012) 。
6. 選取 [儲存 **]**。

若要將直接路由或混合式號碼指派給資源帳戶，您必須使用 PowerShell：

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```
