---
title: 在 [審核記錄] 中搜尋 Microsoft 團隊中的事件
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 瞭解如何從審核記錄中檢索 Microsoft 團隊資料。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88eda5d9acaeb876008b3eb35d38b348830cce48
ms.sourcegitcommit: 67466cde3ffd5c42d632300b8a2adf7aab7df5d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "43958408"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 [審核記錄] 中搜尋 Microsoft 團隊中的事件

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

審核記錄可協助您調查跨 Microsoft 365 服務的特定活動。 針對 Microsoft 團隊，以下是一些經過審核的活動：

- 小組建立
- 小組刪除
- 已新增頻道
- 已變更設定

如需經過審核之小組活動的完整清單，請參閱[團隊活動](#teams-activities)。

> [!NOTE]
> 來自專用通道的審核事件也會記錄為針對團隊和標準通道的活動。

## <a name="turn-on-auditing-in-teams"></a>在團隊中開啟審核

您必須先在[安全性 & 合規性中心](https://protection.office.com)開啟審核，然後才能查看審核資料。 如需有關開啟審核的協助，請參閱[開啟或關閉審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。

> [!IMPORTANT]
> 審核資料只能從您開啟 [審計] 的位置使用。

## <a name="retrieve-teams-data-from-the-audit-log"></a>從審核記錄中取得團隊資料

1. 若要取得審核記錄，請移至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在 [**搜尋**] 底下，選取 [**審核記錄搜尋**]。
2. 使用 [**搜尋**] 篩選您想要審核的活動、日期和使用者。
3. 將結果匯出至 Excel 以進行進一步分析。

> [!IMPORTANT]
> 審核資料只有在已開啟審核的情況下，才會顯示在審核記錄中。

審核記錄在審核記錄中保留和搜尋的時間長度取決於您的 Microsoft 365 或 Office 365 訂閱，以及指派給使用者的授權類型。 若要深入瞭解，請參閱[安全性 & 合規性中心服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。

## <a name="tips-for-searching-the-audit-log"></a>搜尋審核記錄的秘訣

以下是在審核記錄中搜尋[小組活動](#teams-activities)的秘訣。

![[審計記錄搜尋] 頁面的螢幕擷取畫面](media/audit-log-search-page.png)

- 您可以按一下 [活動名稱]，選取要搜尋的特定活動。 或者，您可以按一下組名來搜尋群組中的所有活動（例如檔案**和資料夾活動**）。 如果已選取活動，您可以按一下活動來取消選取。 您也可以使用 [搜尋] 方塊來顯示包含您所輸入之關鍵字的活動。<br>
    ![審核記錄搜尋的螢幕擷取畫面](media/audit-log-search.png)
- 若要顯示使用 Cmdlet 執行之活動的事件，請選取 [**活動**] 清單中的 [**顯示所有活動的結果**]。 如果您知道這些活動的作業名稱，請搜尋所有活動，然後在 [**活動**] 欄的方塊中輸入作業的名稱，以篩選結果。 若要深入瞭解，請參閱[步驟3：篩選搜尋結果](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results)。
- 若要清除目前的搜尋準則，請按一下 [**清除**]。 日期範圍會回到最近七天的預設值。 您也可以按一下 [**全部清除] 來顯示所有活動的結果**，以取消所有選取的活動。
- 如果找到5000結果，您可能會假設有超過5000個事件符合搜尋準則。 您可以縮小搜尋準則，並重新執行搜尋以傳回較少的結果，或者您可以選取 [**匯出結果** > ] 以**下載所有結果**來匯出所有搜尋結果。

請[觀看這段影片](https://www.youtube.com/embed/UBxaRySAxyE)，瞭解如何使用音訊記錄搜尋。 加入 Ansuman Acharya （一種小組的程式管理員），他示範如何進行審核記錄搜尋以尋找小組。

## <a name="use-cloud-app-security-to-set-activity-policies"></a>使用 Cloud App Security 設定活動原則

使用[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)整合，您可以設定[活動原則](https://docs.microsoft.com/cloud-app-security/user-activity-policies)，以利用 App 提供者的 api 強制執行多種自動化程式。 這些原則可讓您監視各個使用者所執行的特定活動，或追蹤特定類型的活動的意外速度。

設定活動偵測原則之後，就會開始產生通知。 警報只會在建立原則後發生的活動產生。 以下是一些範例案例，說明如何在雲端 App 安全性中使用活動原則來監視團隊活動。

### <a name="external-user-scenario"></a>外部使用者案例

從商務角度來看，您可能會想要記住的一個案例，就是將外部使用者新增至您的小組環境。 如果已啟用外部使用者，則監視其目前狀態是一個不錯的主意。  您可以使用[雲端 App 安全性](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)來找出潛在的威脅。

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserAddPolicy.png)

此原則的螢幕擷取畫面可讓您命名原則、根據您的業務需求來設定嚴重性、將其設定為（在此例中為單一的活動），然後建立將只會監視非內部使用者的參數，並將此活動限制在團隊中。

您可以在活動記錄中查看來自此原則的結果：

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserList.png)

您可以在這裡查看已設定的原則相符的專案，並視需要進行調整，或將結果匯出成在其他地方使用。

### <a name="mass-delete-scenario"></a>成批刪除案例

如前文所述，您可以監視刪除情況。 您可以建立可監視大量刪除小組網站的原則。 在這個範例中，警示式原則設定為在30分鐘內偵測小組大量刪除。 

![[原則建立] 頁面的螢幕擷取畫面，其中顯示設定大量小組刪除偵測原則的原則](media/TeamsMassDeletePolicy.png)

如螢幕擷取畫面所示，您可以針對此原則設定許多不同的參數來監視團隊刪除，包括嚴重性、單一或重複動作，以及將此限制為小組和網站刪除的參數。 您可以根據組織的需求，從範本中獨立完成此操作，或者您可能會根據貴組織的需求而建立範本來建立基礎。

建立適用于您企業的原則之後，您就可以在觸發事件時查看活動記錄中的結果：

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsMassDeleteList.png)

您可以篩選到已設定的原則，以查看該原則的結果。 如果您在活動記錄中取得的結果不滿意（可能是您看到許多結果，或是根本沒有反應），這可能會協助您微調查詢，使其更符合您的需求。

### <a name="alert-and-governance-scenario"></a>警示與管理案例

當觸發活動原則時，您可以設定通知並傳送電子郵件給系統管理員和其他使用者。 您可以設定自動化的管轄動作，例如暫停使用者，或讓使用者以自動方式再次登入。 這個範例說明觸發活動原則時，使用者帳戶如何暫停，並決定使用者在30分鐘內刪除兩個或多個小組。

![活動原則之警報與管轄動作的螢幕擷取畫面](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>使用 Cloud App Security 設定異常情況偵測原則

雲端 App 安全性中的[異常偵測原則](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)提供現成的使用者與實體行為分析（UEBA）和機器學習（ML），讓您可以立即在雲端環境中執行高級威脅偵測。 因為它們會自動啟用，所以新的異常偵測策略會提供立即的結果，這是針對您的使用者以及與您的網路連線的電腦和裝置所做的各種行為異常所造成的。 此外，新的原則還會從雲端 App 安全性偵測引擎公開更多資料，以協助您加速調查程式，並包含持續的威脅。

我們正在努力將團隊事件整合至異常情況偵測原則。 現在，您可以為其他 Office 產品設定異常情況偵測原則，並在與這些原則相符的使用者上採取動作專案。 

## <a name="teams-activities"></a>團隊活動

以下是在 Microsoft 365 審核記錄中針對團隊中的使用者和系統管理活動記錄的所有事件的清單。 此表格包含 [**活動**] 欄中顯示的易記名稱，以及當您匯出搜尋結果時，出現在審計記錄的詳細資訊和 CSV 檔案中的對應作業名稱。

|好記的名稱  |一道|說明 |
|---------|---------|---------|
|已在小組中新增 bot   |BotAddedToTeam        |使用者在小組中新增 bot。        |
|已新增頻道   |ChannelAdded         |使用者將頻道新增至小組。         |
|已新增連接器  |ConnectorAdded          |使用者在頻道中新增連接器。        |
|已新增成員    |MemberAdded         |小組擁有者將成員新增至團隊、頻道或群組聊天。         |
|[新增] 索引標籤    |TabAdded         |使用者在頻道中新增一個索引標籤。        |
|已變更頻道設定    |ChannelSettingChanged         |當小組成員執行下列活動時，就會記錄 ChannelSettingChanged 操作。 針對這些活動中的每個動作，會在審核記錄搜尋結果的 [**專案**] 欄中顯示已變更之設定（以括弧顯示）的描述。 <ul><li>變更小組頻道的名稱（**頻道名稱**）</li><li>小組頻道的變更描述（**頻道描述**）</li> </ul>      |
|已變更的組織設定   |TeamsTenantSettingChanged         |當由 Microsoft 365 系統管理中心的全域系統管理員執行下列活動時，就會記錄 TeamsTenantSettingChanged 操作。 這些活動會影響整個組織的團隊設定。 若要深入瞭解，請參閱[管理貴組織的團隊設定](enable-features-office-365.md)。 <br>針對這些活動中的每一個專案，在審核記錄搜尋結果的 [**專案**] 欄中，會顯示已變更之設定（在括弧中顯示）的描述。<ul><li>為組織（**Microsoft 團隊**）啟用或停用團隊。</li><li>啟用或停用 Microsoft 團隊與商務用 Skype （**商務用 skype 互通性**）之間的互通性。</li><li>在 Microsoft 團隊用戶端（**組織結構視圖**）中啟用或停用組織結構視圖。</li><li>啟用或停用小組成員排程私人會議的能力（[**私人會議排程**]）。</li><li>啟用或停用小組成員排程頻道會議的能力（[**頻道會議排程**]）。</li><li>啟用或停用團隊會議中的視頻通話（**Skype 會議的影片**）。</li><li>啟用或停用組織中的 [Microsoft 團隊聚會] 中的螢幕共用（**Skype 會議的螢幕共用**）。</li><li>啟用或停用新增動畫影像（稱為 Giphy）至團隊交談（**動畫影像**）的功能。</li><li>變更組織的內容評等設定（[**內容分級**]）。 內容分級會限制交談中可以顯示的動畫影像類型。</li><li>啟用或停用小組成員將來自網際網路的自訂影像（稱為自訂 meme）新增至小組交談的能力（**來自網際網路的可自訂圖像**）。</li><li>啟用或停用小組成員將可編輯影像（稱為貼紙）新增至小組交談的能力（**可編輯的影像**）。</li><li>啟用或停用小組成員在 Microsoft 團隊聊天和頻道中使用機器人的能力（**全組織機器人）**。</li><li>啟用 Microsoft 團隊的特定 bot。 這不會包含 T Bot，在為組織啟用機器人時（**個別 bot**），也可以使用「團隊說明」提供的機器人。</li><li>啟用或停用小組成員新增副檔名或索引標籤的功能（[**延伸] 或 [** 索引標籤]）。</li><li>啟用或停用 Microsoft 團隊專用 bot 的側載（**bot 的側面載入**）。</li><li>啟用或停用使用者傳送電子郵件至 Microsoft 團隊頻道（**頻道電子郵件**）的功能。</li></ul>|
|已變更團隊成員的角色    |MemberRoleChanged         |小組擁有者會變更團隊成員的角色。 下列值代表指派給使用者的角色類型。 <br><br>**1** -表示擁有者角色。<br>**2** -表示成員角色。<br>**3** -表示來賓角色。<br><br>Members 屬性也包括貴組織的名稱，以及該成員的電子郵件地址。        |
|已變更團隊設定    |TeamSettingChanged        |當小組擁有者執行下列活動時，就會記錄 TeamSettingChanged 操作。 針對這些活動中的每一個專案，在審核記錄搜尋結果的 [**專案**] 欄中，會顯示已變更之設定（在括弧中顯示）的描述。<ul><li>變更團隊的存取類型。 團隊可以設定為私人或公用（**團隊存取類型**）。 當團隊是私人（預設設定）時，使用者只能透過邀請存取團隊。 當團隊公開時，任何人都可以發現。</li><li>變更團隊的資訊分類（[**小組分類**]）。 例如，您可以將團隊資料分類為高業務效應、中型企業影響或低企業影響。</li><li>變更團隊名稱（**團隊名稱**）。</li><li>變更小組描述（[**小組描述**]）。</li><li>對團隊設定所做的變更。 若要存取這些設定，小組擁有者可以以滑鼠右鍵按一下團隊，選取 [**管理團隊**]，然後按一下 [**設定**] 索引標籤。針對這些活動，已變更之設定的名稱會顯示在審核記錄搜尋結果的 [**專案**] 欄中。</li></ul>         |
|已建立小組    |TeamCreated         |使用者建立團隊。         |
|已刪除的頻道     |ChannelDeleted         |使用者從小組中刪除頻道。         |
|已刪除的小組  |TeamDeleted            |小組擁有者會刪除小組。      |
|已從團隊中移除機器人   |BotRemovedFromTeam         |使用者移除小組中的 bot。       |
|已移除連接器     |ConnectorRemoved         |使用者移除頻道的連接器。         |
|已移除成員    |MemberRemoved        |小組擁有者會從團隊、頻道或群組聊天中移除成員。         |
|已移除索引標籤    |TabRemoved         |使用者從頻道中移除索引標籤。         |
|已更新連接器    |ConnectorUpdated         |使用者修改了頻道中的連接器。         |
|[更新] 索引標籤   |TabUpdated         |使用者修改了頻道中的索引標籤。         |
|已登入團隊的使用者     |TeamsSessionStarted         |使用者登入 Microsoft 團隊用戶端。 這個事件不會捕獲權杖重新整理活動。         |

## <a name="office-365-management-activity-api"></a>Office 365 管理活動 API

您可以使用 Office 365 管理活動 API 來取得小組事件的相關資訊。 若要深入瞭解團隊的管理活動 API 架構，請參閱[團隊架構](https://docs.microsoft.com/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api)。

## <a name="related-topics"></a>相關主題

- [在 Microsoft 365 規範中心搜尋審核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)