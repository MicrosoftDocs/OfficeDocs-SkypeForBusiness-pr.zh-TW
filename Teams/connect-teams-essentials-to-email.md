---
title: 將 Microsoft Teams 基本版 (AAD 身分識別) 連線到具有行事曆的現有電子郵件系統
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何使用 Google Workspace 等行事曆，將 Microsoft Teams 基本版 (AAD 身分識別) 連線到現有的電子郵件系統
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acdd613044e5e7f0ac7db857ca734f276522c919
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377591"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>將 Microsoft Teams 基本版 (AAD 身分識別) 連線到具有行事曆的現有電子郵件系統

本指南提供將 Microsoft Teams 基本版 (AAD 身分識別) 連線至具有行事曆之現有電子郵件系統的組態步驟。

Microsoft Teams 基本版 (AAD 身分識別) 透過會議、聊天、通話和共同作業，將 Teams 的最佳功能整合在一起。 Teams 程式集 (AAD 身分識別) 可以連線到您現有的電子郵件系統，以提供整合式體驗，例如在現有電子郵件收件匣中擁有所有 Teams 通知、Teams 中的所有行事曆活動，以及使用您現有的電子郵件地址登入 Teams 的功能。

連線之後，您就可以在信箱和 Microsoft Teams 中看到已排程會議和邀請的回應，以便共同作業。 您也可以使用 Teams 和協力廠商會議軟體，例如 Google Workspace，檢視行事曆內送的會議並與之互動。

## <a name="prerequisites"></a>必要條件

本文中的組態步驟涉及從Exchange Online自動轉寄專案的程式。 根據預設，反垃圾郵件輸出原則會停用自動轉寄。 必須啟用此原則，才能將 Teams 程式集連線到現有的信箱和行事曆系統。

若要啟用自動轉寄：

1. 移至Microsoft 365 Defender入口網站：<https://security.microsoft.com/>
2. 在左側導覽功能表底下，移 **至 [原則] 區段中的Email &**  >  共同作業原則 **&規則**  >  **威脅原則**  >  **反垃圾郵件**]
3. 在 [**反垃圾郵件原則**] 頁面上，從清單中選 **取 [反垃圾郵件輸出原則 (預設)**
4. 在出現的原則詳細資料飛出視窗中，選取 **[編輯保護設定** ] 以修改自動向下規則。
5. 在 [ **轉寄規則]** 底下，將自動轉寄條件變更為 [開 **啟 – 轉寄] 並** 儲存您的變更。

:::image type="content" source="media/essentials-antispam.png" alt-text="圖像顯示 [Microsoft Defender入口網站反垃圾郵件輸出原則飛出視窗，其中包含 [轉寄規則] 下的 [開啟]、[轉寄] 條件。" :::

若要深入瞭解如何設定外寄垃圾郵件原則，請流覽[設定外寄垃圾郵件篩選 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>使用 Exchange 內部部署將 Teams 程式集連線至Exchange Online

您可以使用混合式方法來設定 Microsoft Teams 與 Exchange 內部部署Exchange Online之間的連線，以享受 AAD (所有 Teams 程式集) 所提供的功能。

若要讓內部部署信箱的行事曆存取功能正常運作，請遵循設定[Exchange 內部部署信箱的 Teams 行事曆存取權](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)中提供的指導方針 - Microsoft Tech Community

若要在混合式環境中部署 Exchange 內部部署Microsoft Teams 會議室，請流覽[使用 Exchange 內部部署Microsoft Teams 會議室 - Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>使用行事曆將 Teams 程式集連線到協力廠商電子郵件系統

如果您不打算將貴組織的信箱切換到 Microsoft 365，您可以將 Teams 程式集連線到現有的協力廠商電子郵件和行事曆系統。 此連線可讓您在檢視 Microsoft Teams 中的現有會議邀請和行事曆活動時，在現有電子郵件系統中接收 Teams 通知。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>使用虛名網域將 Teams 程式集連線至協力廠商電子郵件 (Google Workspace 範例) 

下列區段將示範如何將 Microsoft Teams 連線到具有行事曆的現有電子郵件系統，例如 Google Workspace。 若要完成此連線，請保持目前的電子郵件系統不變，將所有電子郵件轉寄至Exchange Online，篩選行事曆類型的電子郵件以外的所有專案。 如此一來，行事曆電子郵件會自動出現在已接受為暫訂且非行事曆類型的電子郵件中。

在 Microsoft 365 中產生的所有電子郵件都會轉寄到 Google Workspace，讓使用者取得 Teams 提醒和通知。 使用者身分識別，例如使用者的主要電子郵件，可以重複。 單一登入也有可能，但並非必要。 使用者應該可以從協力廠商行事曆或 Teams 行事曆加入 Teams 會議。 另一個 Teams 功能將會如預期般運作。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="描述 EXO 和 Gmail 之間郵件流程圖的影像":::

這些範例仰賴屬於[PowerShell V2 Exchange Online](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps)一部分的[Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) PowerShell 命令。 如果您在執行 Connect-ExchangeOnline 時收到錯誤訊息，請確定您已遵循使用安裝 [EXO V2 模組](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module)來安裝模組的建議指示。 當Connect-ExchangeOnline提示您輸入認證時，請務必使用租使用者系統管理員帳戶。

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>步驟 1：設定新的 Microsoft 365 租使用者網域

1. 移至系統管理中心。 <https://admin.microsoft.com>

2. 移至 **[設定**  >  **網域]**，然後選取 [**新增網域**] 以新增您現有的網域。 如果您不新增網域，貴組織中的人員會使用 onmicrosoft.com 網域做為其電子郵件地址，直到您新增為止。 請務必先新增您的網域，再新增使用者，這樣您就不需要設定兩次。

3. 依照使用 [TXT 記錄驗證中的步驟，以 TXT 記錄驗證網](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)域。

4. 出現提示時，選 **取 [不允許 Microsoft 365 設定 DNS]**。

5. 出現提示時，不變更現有的 MX 記錄。

6. 更新現有的 SPF TXT 記錄以包含 Microsoft 365。

7. 依照下列步驟手動 [設定 DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)，設定 Microsoft 365 的網域金鑰識別郵件 (DKIM) 。

8. 重新登入Microsoft 365 系統管理中心 <https://admin.microsoft.com/AdminPortal/> ，以啟用 DKIM

9. 在左側導覽面板中，選取 **[設定**  >  **網域]**

10. 使用核取方塊，從目前的網域清單中選取您現有的非 Microsoft 網域 (例如：TomislavK@thephone-company.com) 。

11. 選取有 **三個垂直點的** 按鈕以開啟功能表。

12. 從功能表中，選 **取 [設為預設值]**

13. 在顯示為預設值的視窗中，**確認設為默** 認值。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="將網域設為預設值的確認對話方塊圖像":::

    如需將網域新增至 Microsoft 365 的更多指導方針，請依照將 [網域新增至 Microsoft 365 中](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)所述的步驟進行。

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>步驟 2：新增使用者並指派 Teams 程式集授權

1. 移至系統管理中心， <https://admin.microsoft.com> 以新增個別使用者

2. 移至 **[使用者**  >  **作用中使用者]**，然後選 **取 [新增使用者]**

3. 在 [ **設定基本功能** ] 窗格中，填寫基本使用者資訊，然後選取 [ **下一步]**。
    - **名字：** 填寫名字和姓氏、顯示名稱和使用者名稱。
    - **域：** 選擇使用者帳戶的網域。 例如，如果使用者的使用者名稱是 Jakob，且網域已 contoso.com，則會使用 jakob@contoso.com 登入。
    - **密碼設定：** 選擇使用自動產生密碼，或為使用者建立自己的強式密碼。  判斷您是否要在新增使用者時傳送電子郵件密碼。

4. 在 [ **指派產品授權]** 窗格中，選取使用者的位置和適當的授權。 如果您沒有任何可用的授權，您仍然可以新增使用者並購買更多授權。 選取 [下一步]。

5. 在 **[選用設定** ] 窗格中，如果您想要讓此使用者成為系統管理員，請展開 [ **角色** ]。展開 **設定檔資訊** 以新增使用者的其他相關資訊。

6. 選 **取 [下一步**]，檢閱新使用者的設定，視需要進行任何其他變更，然後選取 [ **完成新增**]，然後關閉。

若要同時新增多個使用者，請依照[新增使用者和指派授權 - Microsoft 365 系統管理員|Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>步驟 3：設定 Google Workspace

***設定將電子郵件雙傳送至 Microsoft 365，並去除附件：***

1. 依照 Google 設定雙遞送的步驟進行： <https://support.google.com/a/answer/9228551?hl=en>

2. 新增Office 365路由

    - 前往) 的 <https://admin.google.com> Google 管理員 主機
    - 移至 Google Workspace > App > Gmail >主機。
    - 輸入路由名稱。  (例如，Microsoft 365) 
    - 選擇 [單一主機]，然後輸入 Microsoft 365 中針對網域指定的 MX 記錄 (例如：ContosoLandscaping2-m365master-com.mail.protection.outlook.com) 

    **當郵件傳送到 Exchange 內部部署/Exchange Online時解決 ATTR35 回應碼的智慧主機方法：**
    - 選擇 [單一主機]，然後輸入租使用者初始網域的 MX 記錄做為智慧主機。 初始網域的格式為 GUID.onmicrosoft.com。 GUID 是提供給每個組織的唯一值，做為其在服務中註冊的一部分。 GUID 是 128 位的整數 (16 位元組) ，只要需要唯一識別碼，就可以在所有電腦和網路上使用。
    - 您可以使用命令列：nslookup -type MX GUID.onmicrosoft.com 來解決 MX 記錄 (例如：contosolandscaping2.mail.protection.outlook.com) 
    - 選擇 **[埠：25]**
    - 繼續使用建議的選項

3. 設定Office 365路由

    - 開啟 **Google 管理員 主機**，<https://admin.google.com>

    - 移至 **Apps**  >  **Google Workspace**  >  **Gmail**  >  **路由**

    - 在 [ **路由] 索引** 標籤上，選 **取 [設定]**

    - 輸入規則的 **名稱** 。  (例如，Gmail 轉Office 365) 

    - 若 **要影響電子郵件訊息**，請選取 [ **輸入** ] 和 [  **內部接收]**

    - 在 **[針對上述類型的郵件] 底** 下，選取 **[修改郵件]**

    - 在 [ **也交付給**] 底下，選取 **[新增更多收件者]** ，然後選取 **[新增] 以新增次要郵件路由。**

    - 在 **[收件者] 底** 下，選取向下箭號 「」，然後選取 [ **進階]。**

    - 選 **取 [變更路線]。**

    - 從清單中，選取您先前建立的次要郵件路由

    - 在 [ **附件] 底** 下，選 **取 [從郵件移除附件]**

    - 向下捲動並選取 [ **儲存]**。

***在 Google 工作區中新增您的子域以接收來自 Microsoft 365 的電子郵件。***

  接下來，您將在 Microsoft 365 信箱上建立轉寄規則到您的子域。 選擇要在 Google Workspace 中使用的子域來接收來自 Microsoft 365 的電子郵件 (例如，g.contosolandscaping2.m365master.com) 

1. 從 **google 管理員 主機** (從 admin.google.com) 開始

2. 移至 **帳戶**  >  **網域**  >  **管理網域**

3. 選 **取 [新增網域]**

4. 輸入您選取的功能變數名稱

5. 選 **取使用者別名網域**

6. 選 **取 [新增網域&開始驗證]**

7. 等待驗證完成並重新整理頁面

8. 選 **取 [啟用 Gmail]**

9. 選擇 **[略過 MX 記錄設定]** ，然後選取 [ **下一步]**

10. 在 [ **將郵件傳送到另一個伺服器** ] 對話方塊中，記下伺服器將郵件路由至 (例如，aspmx.l.google.com) 並選取 **[我使用另一個郵件伺服器]**

***允許來自 Microsoft 365 的電子郵件略過垃圾郵件篩選***

1. 在 Google 工作區上傳送電子郵件給使用者，從 Microsoft 365 租使用者尋找適當的頁首。

2. 開啟郵件，然後選取 **[顯示原始郵件]**

3. 選擇可唯一識別來自 Microsoft 365 租使用者之郵件的電子郵件標題。  (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

4. 移至 **Google 管理員 主機**，<https://admin.google.com>

5. 移至 **應用程式**  >  **Google Workspace**  >  **Gmail**  >  **合規性**

6. 流覽至 **[內容合規性** ]，然後選取 **[設定]**

7. 為設定命名。 例如，Allowlist Microsoft 365 電子郵件。

8. 在 **[電子郵件訊息] 底下影響** 勾選輸入

9. 在 [ **新增描述您要在每封郵件中搜尋之內容的運算式** ] 底下，選取 **下列任一郵件是否符合**

10. 在 **[運算式] 底** 下，選取 **[Add** xi]。 在 [ **新增設定]** 底下，選擇 [ **進階內容比對]**

11. 在 **[位置]** 下選擇 **[完整頁首]**

12. 在 **[符合類型] 下** 選擇 **[全文]**

13. 在內容底下，輸入可唯一識別來自您 Microsoft 365 租使用者之電子郵件的電子郵件標題 (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

14. 選取 **[儲存]**

15. 在 **上述運算式符合時，請執行下列** 欄位>**修改郵件**]，然後核取 [垃圾郵件] 底下的 [**略過垃圾郵件篩選****]**。

16. 選取 **[儲存]**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>步驟 4：設定整合的 Microsoft 365 設定

*設定連接器以將郵件從 Microsoft 365 路由至 Gmail：*

1. 移至 **Microsoft 管理員 中心**，<https://admin.microsoft.com/AdminPortal>

2. 選取左側導覽功能表中的 [ **全部顯示** ]。

3. 在 **[管理員中心**] 底下，選取 **[Exchange**] 以在新索引標籤中開啟 Exchange 系統管理中心

4. 在 **Exchange 系統管理中心的** 左側導覽功能表中，選取 **[郵件流程**  >  **連接器**]，開啟溢出功能表 (...) 然後選取 [新增連接器]

5. 在新連接器視窗中的 [**聯** 機] 底下，選 **取 [Office 365**

6. 在 [ **連線] 底** 下選取您組織的電子郵件伺服器，然後選取 [ **下一步]**

7. 輸入新連接器的 **名稱** (例如：至 Gmail) 然後繼續 **下一步**

8. 在 [ **使用連接器** ] 區段中， **選取 [只有當我設定傳輸規則將郵件重新導向至此連接器時]，** 然後選取 [ **下一步]**。

9. 在 [路由] 區段中，輸入適當的智慧郵件主機 (例如，aspmx.l.google.com) ，選 **+** 取 ，然後繼續 **[下一步]**。

10. 在 [**安全性限制**] 區段中，選取 [**下一步**] 以接受預設設定

11. 在 [ **驗證電子郵件] 區段** 中，輸入 Gmail 系統的有效電子郵件地址 (例如，johannal@g.contosolandscaping2.m365master.com) 選取 **加號 (+)**，然後選取 **[驗證]**

12. 等待驗證完成，如果成功，請按下一步

13. 在 [ **檢閱連接器**] 底下，確認設定正確無誤，然後按 [建立連接器]

14. 當您看到連接器建立的通知時，請按 **[完成]**

*將郵件從 Microsoft 365 信箱轉寄到 Gmail：*

1. 使用 **Microsoft 365 系統管理中心** 來更新每個信箱，或者您可以使用 **PowerShell** 腳本，例如：

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Connect-ExchangeOnline 疑難排解：**

    您在執行 Connect-ExchangeOnline 時遇到錯誤嗎？ 這可能是貴組織自動電子郵件轉寄規則的結果。 根據預設，自動轉寄功能會停用。 若要將 Teams 程式集連線至 Google Workspace，必須啟用規則。

    輸入下列腳本：

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    之後，執行下列命令：

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*設定行事曆傳輸規則Exchange Online直接執行：*

1. 設定此設定會自動接受行事曆邀請，使其顯示在 Teams 行事曆中，而不需要使用者在 Outlook Web App 中與邀請互動。

2. 下列腳本可用於建立傳輸規則：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*停用信箱Outlook 網頁版：*

1. 請依照在[Exchange Online 中啟用或停用信箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)Outlook 網頁版以停用信箱Outlook 網頁版中的指示進行。

2. 您可以使用 Exchange 管理員 中心或 **PowerShell** **停用Outlook 網頁版**。 您可以使用下列 PowerShell 範例來停用所有信箱的Outlook 網頁版：

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>步驟 5：設定內部轉送Exchange Online網域

此步驟可確保電子郵件會傳送到協力廠商系統以獲得最終解決方案。

1. 移至 **Microsoft 管理員 中心**，<https://admin.microsoft.com/AdminPortal>

2. 在左側流覽中，選取 [ **全部顯示]**

3. 在 **[管理員中心] 底** 下，選取 **[Exchange**] 以在新索引標籤中開啟 Exchange 系統管理中心

4. 在 **Exchange 系統管理中心**，從左側導覽功能表中選取 **[郵件流程** ]，然後選取 [ **公認的網域]**

5. 點選協力廠商系統中設定的功能變數名稱 (例如，contosoLandscaping2.m365master.com) 

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="顯示郵件流程之 Exchange 系統管理中心設定的影像。 ":::

6. 選取 **[內部轉送**]，然後按一下 [ **儲存]**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="顯示儲存內部轉送設定之動作的影像。":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>步驟 6：建立規則以刪除行事曆以外的所有輸入郵件Exchange Online

1. 您可以在 **Exchange 管理員 中心** 或 **PowerShell** 中設定此規則。 您可以使用下列 **PowerShell** 範例來建立規則：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>將 Teams 程式集連線至未使用虛名網域的協力廠商電子郵件 (Gmail 範例) 

您可以將消費者 Gmail 帳戶連線至主要信賴 Teams [G Suite Add](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) On 的 Teams 基本版，藉此直接從 Google Workspace 排程並加入 Teams 會議。 這可讓您透過螢幕共用、會議聊天、數位白板等功能來排程視訊和音訊會議。

您將設定 Gmail 從 Exchange Online 提取電子郵件，以確保在 Microsoft 365 和 Teams 中產生的郵件成功送達 Gmail。 您可能需要停用安全性預設值，才能完成此連線，因此使用強式唯一密碼是不可或缺的。 此案例不需要自訂網域，但如果您想要使用自訂網域，可以在 Microsoft 365 中設定，以便在 Gmail 中使用。

:::image type="content" source="media/essentials-gmail.png" alt-text="在 Teams 程式集和 Gmail 之間標注郵件流程的影像":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. 確定您已設定 Gmail 帳戶

如果您已經有帳戶，您可以繼續下一個步驟。 如果沒有，請流覽 [建立新的 Google 帳戶](https://accounts.google.com/SignUp?hl=en) 以設定新的 Gmail 帳戶。

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. 設定您的 Microsoft 365 租使用者

*設定 Teams AAD 使用者：*

1. 請依照新增[使用者並指派授權](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 以新增多個使用者的指導方針進行

*設定身分識別保護：*

1. 如果為使用中，則停用安全性預設值。

2. 為使用者設定多重要素驗證

3. 如果使用條件式存取，請務必針對 POP 存取信箱設定例外狀況

*將網域新增至Microsoft 365 系統管理中心 (選用) ：*

1. 在 [導覽] 底下，選取 [設定>網域]，然後選取 [新增網域]

2. 在適當的欄位中輸入您的功能變數名稱

3. 依照畫面上的指示使用 TXT 記錄驗證網域

4. 出現提示時，允許 Microsoft 設定 DNS

5. 完成指示以驗證 MX 記錄路由至 Microsoft 365

6. 將 SPF TXT 記錄設定為包含 Microsoft 365

7. 完成設定 Microsoft 365 DKIM TXT 記錄的指示

8. 登出並重新登入管理員中心，確認已啟用 DKIM

#### <a name="3-configure-gmail"></a>3. 設定 Gmail

1. 設定 Gmail 將Exchange Online郵件取入其系統

2. 設定 Teams 行事曆增益集

3. 啟用 Gmail 使用商務網域 (選用) 
