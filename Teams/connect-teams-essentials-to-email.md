---
title: 連線 Microsoft Teams使用 (AAD識別) 至現有的電子郵件系統
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何使用 Google Workspace 等Microsoft Teams將 (AAD身分識別) 至現有的電子郵件系統
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 682f7bcd4e90e96534e954cd0e22c6f5952db08b
ms.sourcegitcommit: 563567ab140d5802756170c846dade3645d0b9e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284791"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>連線 Microsoft Teams使用 (AAD識別) 至現有的電子郵件系統

本指南提供使用日曆將 Microsoft Teams基本 (AAD身分) 連結至現有電子郵件系統的組組步驟。

Microsoft Teams基本 (AAD身分) 功能，將會議、Teams、通話和共同合作等功能彙集在一起。 Teams 基本功能 (AAD 身分識別) 可以連接到現有的電子郵件系統，以提供整合式體驗，例如將所有 Teams 通知都放入現有的電子郵件信箱、Teams 中所有的日曆事件，以及使用現有電子郵件地址登錄 Teams。

連接後，您可以在信箱和信箱中查看已排程會議的回應，以及共同Microsoft Teams。 您也可以使用 Google Workspace 等協力廠商會議Teams來查看和互動來自您日曆的傳入會議。

## <a name="prerequisites"></a>必要條件

本文中的組組步驟會涉及自動轉Exchange Online。 根據預設，反垃圾郵件外發策略會停用自動轉轉。 必須啟用此政策，Teams基本功能到現有的信箱和日曆系統。

若要啟用自動轉轉：

1. 請前往 Microsoft 365 Defender入口網站<https://security.microsoft.com/>
2. 在左側導航功能表 **下**，前往在 & 中&原則反垃圾郵件的電子郵件和共同  >    >    >  ****&原則
3. 在反 **垃圾郵件政策** 頁面上，從清單中選取 **(預設) 垃圾郵件** 外發策略
4. 在出現的原則詳細資料飛出中，選取編輯 **保護設定** 以修改自動向前規則。
5. 在 **轉轉規則下**，將自動轉轉條件變更為 **啟用 -** 轉轉，並儲存您的變更。

:::image type="content" source="media/essentials-antispam.png" alt-text="顯示 Microsoft Defender 入口網站反垃圾郵件輸出原則飛出與 On 的影像，轉轉是在轉轉規則下啟用的條件。" :::

若要深入瞭解如何設定外發垃圾郵件政策，請流覽設定外發垃圾郵件篩選 - Office 365 | [Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>連線 Teams內部部署Exchange Online基本Exchange基本功能

您可以使用混合式方法Teams基本 (AAD) 提供的所有功能，來設定 Microsoft Teams 與 Exchange Online 之間的Exchange連接。

若要讓內部部署信箱的日曆存取能夠使用，請遵循為 Teams 內部部署信箱的 Teams Exchange 日曆存取[- Microsoft Tech](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009) Community

若要在Microsoft Teams 會議室混合式環境中部署Exchange，請流覽使用內部部署 Microsoft Teams 會議室 部署 Exchange [- Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>連線 Teams日曆的協力廠商電子郵件系統的基本功能

如果您不想將組織的信箱切換至 Microsoft 365，您可以將 Teams 基本功能連結至現有的協力廠商電子郵件和日曆系統。 此連結可讓您在Teams系統內接收通知，同時檢視現有的會議邀請和 Microsoft Teams。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>連線 Teams Google Workspace 範例中，使用虛名網域將基本功能 (至第三) 

下一節將說明如何使用Microsoft Teams ，例如 Google Workspace，將郵件連結至現有的電子郵件系統。 您將保持目前電子郵件系統不變，將所有電子郵件轉Exchange Online，篩選日曆類型之電子郵件以外的所有專案，以達成此連接。 如此一來，電子郵件的日曆會自動出現在Teams接受為暫定和非日曆類型電子郵件的日曆中。

系統會轉Microsoft 365 Google Workspace 中產生的所有電子郵件，讓使用者Teams提醒和通知。 使用者身分標識 ，例如使用者的主要電子郵件，可以重複。 也可以單一登入，但不需要。 使用者應該能夠從協力廠商Teams或協力廠商Teams會議。 其他Teams功能會如預期一樣使用。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="描繪 EXO 與 Gmail 之間郵件流程圖表的影像":::

這些範例仰賴 連線 PowerShell V2 模組的[Exchange Online ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) [PowerShell 命令。](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) 如果您在執行 連線-ExchangeOnline 時收到錯誤，請確保您已遵循使用[安裝 EXO V2](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true)模組安裝模組的建議指示。 當您Connect-ExchangeOnline認證提示時，請務必使用租使用者系統管理員帳戶。

**步驟一：設定新的租使用者Microsoft 365網域**

1. 請前往 系統管理中心 <https://admin.microsoft.com> 。

2. 前往設定 **網**  >  **域**，然後選取 **新增網** 域以新增現有的網域。 如果您沒有新增網域，貴組織中的人員會使用 onmicrosoft.com 網域作為電子郵件地址，直到您這麼做。 在新增使用者之前，請務必先新增網域，這樣您就不需要設定兩次。

3. 請遵循使用 TXT 記錄驗證中的步驟，以 [TXT 記錄驗證網域](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)。

4. 當系統提示時，選取 Microsoft 365 **設定 DNS**。

5. 當系統提示時，請保留現有的 MX 記錄，而不進行變更。

6. 更新現有的 SPF TXT 記錄以包含Microsoft 365。

7. 按照下列步驟手動設定[DKIM， (](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)識別郵件) DKIM Microsoft 365郵件。

8. 請重新Microsoft 365 系統管理中心 <https://admin.microsoft.com/AdminPortal/> 以啟用 DKIM

9. 在左側的流覽面板中 **，選取設定**  >  **網域**

10. 使用核取方塊，選取您現有的非 Microsoft 網域 (例如：JohannaL@contosolandscapting2.m365master.com) 網域清單。

11. 選取具有三 **個垂直點的按鈕** 以開啟功能表。

12. 從功能表中，選取 **設定為預設值**

13. **確認在顯示以** 將現有網域設為預設值的視窗中設為預設值。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="將網域設定為預設值的確認對話方塊影像":::

    若要進一步引導將網域新Microsoft 365，請遵循新增網域至[Microsoft 365。](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)

**步驟 2：新增使用者並指派Teams基本版授權**

1. 前往系統管理中心新增 <https://admin.microsoft.com> 個別使用者

2. 前往使用者  >  **活動使用者**，然後選取新增 **使用者**

3. 在設定 **基本功能** 窗格中，填入基本使用者資訊，然後選取下 **一步**。
    - **名字：** 填寫名字和姓氏、顯示名稱和使用者名稱。
    - **域：** 選擇使用者帳戶的網域。 例如，如果使用者的使用者名稱是 Jakob，且網域 contoso.com，他們將使用 jakob@contoso.com。
    - **密碼設定：** 選擇使用自動產生密碼，或為使用者建立您自己的強式密碼。  決定是否要新增使用者時傳送電子郵件中的密碼。

4. 在指派 **產品授權** 窗格中，選取使用者的位置和適當的授權。 如果您沒有任何可用的授權，您仍然可以新增使用者並購買更多授權。 選取下一步。

5. 如果您想要 **讓此使用者** 成為系統管理員，請展開在選擇性設定窗格中的角色。展開 **設定檔資訊** 以新增使用者的其他相關資訊。

6. 選取 **下** 一步，檢查新使用者的設定，必要時進行任何其他變更，然後選取完成 **新增**，然後關閉。

若要同時新增多個使用者，請遵循新增使用者並指派授權的建議步驟[，Microsoft 365系統管理員|Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**步驟三：設定 Google 工作區**

***設定電子郵件的雙傳遞至Microsoft 365和帶狀附件：***

1. 請遵循 Google 設定雙傳遞的步驟： <https://support.google.com/a/answer/9228551?hl=en>

2. 新增路由Office 365

    - 請前往 Google 系統管理 <https://admin.google.com> 主控台) 
    - 前往 Gmail > Google Workspace >應用程式>主機。
    - 輸入路由名稱。  (例如，Microsoft 365) 
    - 選擇 '單一主機'，然後輸入為網域指定的 MX Microsoft 365 (例如：ContosoLandscaping2-m365master-com.mail.protection.outlook.com) 

    **在內部部署/Exchange郵件時解決 ATTR35 回應代碼的智慧主機Exchange Online：**
    - 選擇 '單一主機'，然後輸入租使用者的初始網域為智慧主機的 MX 記錄。 初始網域的格式為 GUID.onmicrosoft.com。 GUID 是一個唯一值，會提供給每個組織，作為註冊服務的一部分。 GUID 是 128 位的整數 (16 位元組) 可在需要唯一識別碼的所有電腦和網路使用。
    - 您可以使用命令列：nslookup -type MX GUID.onmicrosoft.com 解決 MX 記錄 (例如：contosolandscaping2.mail.protection.outlook.com) 
    - 選擇 **埠：25**
    - 繼續使用建議的選項

3. 設定路由Office 365

    - 開啟 **Google 系統管理主控台** ， <https://admin.google.com>

    - 前往 **應用程式 Google**  >  **工作區**  >  **Gmail**  >  **路由**

    - 在路由 **選項卡** 上 **，選取設定**

    - 輸入 **規則** 的名稱。  (例如，Gmail Office 365) 

    - 若要 **影響電子郵件訊息**，請同時選取輸入和 **內部接收**

    - 在 **針對上述類型的郵件，選取** 修改 **郵件**

    - 在 **也傳遞至** 下，選取 **新增更多收** 件者，然後選取新增 **以新增次要郵件路由。**

    - 在 **「收件者」** 下，選取向下箭鍵 「」，然後選取 「 **進一步」。**

    - 選取 **變更路由。**

    - 從清單中，選取您先前建立次要郵件路由

    - 在 **附件下**，選取 **移除郵件中的附件**

    - 向下卷起並 **選取儲存**。

***在 Google 工作區中新增子域以接收來自Microsoft 365。***

  接下來，您將在信箱上建立轉Microsoft 365規則至您的子域。 選擇一個子域，在 Google Workspace 中用於接收來自 Microsoft 365 (的電子郵件，例如，g.contosolandscaping2.m365master.com) 

1. 從 **Google 系統管理主控台 (** admin.google.com) 

2. 前往帳戶  >  **網域**  >  **管理網域**

3. 選取 **新增網域**

4. 輸入您選取的功能變數名稱

5. 選取 **使用者別名網域**

6. 選取 **新增網域&開始驗證**

7. 等待驗證完成並重新整頁

8. 選取 **啟用 Gmail**

9. 選擇 **跳過 MX 記錄設定，** 然後選取下 **一步**

10. 在 [ **路由郵件** 至另一個伺服器 (，記下伺服器將郵件路由至 (aspmx.l.google.com) ，然後選取 [我使用另一個郵件 **伺服器**

***允許寄件者Microsoft 365垃圾郵件篩選***

1. 在 Google 工作區中傳送Microsoft 365，從該租使用者尋找適當的頁標題。

2. 開啟郵件，然後選取 **顯示原始郵件**

3. 選擇可唯一識別來自您租使用者的郵件Microsoft 365標題。  (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

4. 請前往 **Google 系統管理主控台**<https://admin.google.com>

5. 前往 **App**  >  **Google Workspace**  >  **Gmail**  >  **合規性**

6. 流覽至 **內容合規性****，然後選取** 設定

7. 為設定命名。 例如，允許清單Microsoft 365電子郵件。

8. 在 **影響檢查輸入的電子郵件** 訊息下

9. 在 **新增運算式，描述** 每封郵件中要搜尋的內容，選取下列任何一項是否 **與郵件相符**

10. 在 **運算式下**，選取 **新增** xi。 在 **新增設定下**，選擇進 **一步內容相符**

11. 在 **位置下** 選擇 **完整頁眉**

12. 在 **符合類型下** 選擇 **完整文字**

13. 在內容下，輸入唯一識別來自 Microsoft 365 租使用者的電子郵件標題 (例如，X-MS-Exchange-CrossTenant-id：92f60fc7-eab3-403b-9d7d-9d683bf0a4b5) 

14. 選取 **儲存**

15. 如果上述 **運算式** 相符，請執行下欄欄位>**修改郵件**，並檢查在垃圾郵件下針對此郵件執行旁路 **垃圾郵件篩選**。

16. 選取 **儲存**

**步驟四：設定Microsoft 365整合的設定**

*設定連接器以將郵件從 Microsoft 365路由至 Gmail：*

1. 請前往 **Microsoft 系統管理中心**<https://admin.microsoft.com/AdminPortal>

2. 選取 **左側流覽** 功能表中的全部顯示。

3. 在 **系統管理中心** 下，選取 **Exchange** 以在新Exchange中開啟系統管理中心

4. 在 Exchange **系統** 管理中心的左側流覽功能表中，選取郵件流程連接器，開啟溢出功能表  >  **** (...) 並選取新增連接器

5. 在新 **連接器視窗中** 的連接下，選取 Office 365 

6. 在 **連接下** 選取貴組織的電子郵件伺服器，然後選取下 **一步**

7. 輸入新 **連接器的名稱** ，例如： (Gmail 帳戶，) 下一 **步**

8. In the **Use of Connector** section, select **Only when I have a transport rule set up that redirects messages to this connector** and select **Next**.

9. 在路由區段，輸入適當的智慧郵件主機 (例如，aspmx.l.google.com) ，選取 **+** ，然後繼續下 **一步**。

10. 在安全性 **限制區** 段，選取下一步以接受 **預設設定**

11. 在驗證 **電子郵件** 區段，輸入 Gmail 系統的有效電子郵件地址 (例如 johannal@g.contosolandscaping2.m365master.com) ，選取加號 **(+) ，** 然後選取驗證

12. 等待驗證完成，如果成功，請按下一步

13. 在 **檢查連接器** 下，確認組式正確，然後按 Create Connector

14. 當您看到連接器建立的通知時，請按 **Done**

*將信箱Microsoft 365郵件轉寄到 Gmail*

1. 使用 Microsoft 365 系統管理 **中心** 更新每個信箱，或者您可以使用 **PowerShell** 腳本，例如：

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*設定Exchange Online到日曆傳輸規則*

1. 設定此設定會自動接受您的Teams邀請，而不需要使用者與邀請在 Outlook Web App 中互動。

2. 下列腳本可用來建立傳輸規則：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*停用Outlook 網頁版信箱的啟用*

1. 請遵循啟用或停用Outlook 網頁版[信箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)中的Exchange Online，以Outlook 網頁版信箱。

2. 您可以使用系統管理Outlook 網頁版 PowerShell 來停用Exchange **或 PowerShell。** 您可以使用下列 PowerShell 範例來停用Outlook 網頁版信箱的信箱：

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**步驟五：為Exchange Online設定網域**

此步驟可確保電子郵件會送到協力廠商系統，以最終解決。

1. 請前往 **Microsoft 系統管理中心**<https://admin.microsoft.com/AdminPortal>

2. 在左側流覽中，選取顯示 **全部**

3. 在 **系統管理中心** 下，**選取 Exchange** 以在新Exchange中開啟系統管理中心

4. 在 **Exchange系統** 管理中心中 **，從左側** 流覽功能表選取郵件流程，然後選取已 **接受的網域**

5. 點一下協力廠商系統所配置的功能變數名稱 (例如，contosoLandscaping2.m365master.com) 

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="顯示郵件Exchange系統管理中心設定的圖像。":::

6. 選取 **[內部轉場**，然後按一下 **[儲存**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="顯示保存內部轉場設定之行為的圖像。":::

**步驟六：建立規則以刪除所有傳入郵件至Exchange Online日曆除外**

1. 您可以在系統管理中心或 **PowerShell** Exchange此 **規則**。 您可以使用下列 **PowerShell 範例** 來建立規則：

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>連線 Teams Gmail 範例中，將協力廠商電子郵件的 (必要) 

您可以將消費者 Gmail 帳戶Teams至 Teams 基本功能，並主要依賴 G Suite Add On Teams，直接從 Google Workspace 排程[Teams並](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60)加入會議。 這讓您有機會使用螢幕分享、會議聊天、數位白板等來排程視像和音訊會議。

您將設定 Gmail 從郵件Exchange Online，以確保郵件在 Microsoft 365 Teams順利送達 Gmail。 若要完成此連接，可能需要停用安全性預設值，因此使用強唯一密碼不可或缺。 此案例不需要自訂網域，但如果您想要使用自訂網域，Microsoft 365在 Gmail 中進行配置。

:::image type="content" source="media/essentials-gmail.png" alt-text="在基本功能與 Gmail 之間Teams郵件流程的影像":::

**確定您設定了 Gmail 帳戶。**

如果您已經有現有的帳戶，可以繼續進行下一個步驟。 如果沒有，請流覽 [建立新 Google 帳戶](https://accounts.google.com/SignUp?hl=en) 以設定新的 Gmail 帳戶。

**2. 設定您的Microsoft 365租使用者**

*設定Teams AAD使用者*

1. 請遵循新增使用者[和指派授權](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 以新增多個使用者的指引

*設定身分識別保護*

1. 停用安全性預設值如果為使用中。

2. 為使用者設定多重要素驗證

3. 如果使用條件式存取，請務必讓 POP 存取信箱成為例外

*新增網域至Microsoft 365 系統管理中心 (選)*

1. 在流覽下，選取 設定 >網域，然後選取新增網域

2. 在適當的欄位中輸入您的功能變數名稱

3. 遵循畫面上的指示，以 TXT 記錄驗證網域

4. 當系統提示時，允許 Microsoft 設定 DNS

5. 完成指示以驗證 MX 記錄路由至Microsoft 365

6. 設定 SPF TXT 記錄以包含Microsoft 365

7. 完成針對資料進行 DKIM TXT 記錄Microsoft 365

8. 登出並登入系統管理中心，確認已啟用 DKIM

**3. 設定 Gmail**

1. 設定 Gmail 將郵件Exchange Online系統

2. 設定 Teams日曆附加元件

3. 啟用 Gmail 使用商務網域 (選項) 
