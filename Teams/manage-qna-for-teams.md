---
title: 在 Teams 會議中管理 Q&A
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
description: 瞭解 IT 系統管理員如何在 Teams Q&A 中設定、使用及管理 Q&A，以結構化的方式收集問題、組織討論、刪除個別訊息、使用可用的語言，以及瞭解資料生命週期以及資料保留和刪除原則。
ms.openlocfilehash: edcf1578b70bf39ccf330b7a328b7d0de7558263
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268628"
---
# <a name="manage-qa-in-teams-meetings"></a>在 Teams 會議中管理 Q&A

Q&A 可讓簡報者回答出席者的問題，並即時回答。 這項功能最適合大型結構化會議，例如「大會堂」、「網路研討會」、「萬事如意」和「訓練」。

本文說明如何管理 Q&A 和使用者層級原則，這表示召集人是否可以在會議中啟用 Teams Q&A。

## <a name="prerequisites"></a>必要條件

- 確認您尚未封鎖 [存取 Yammer 的 IP 和 URL。](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- 若要允許貴組織中的使用者將 Q&A 新增至 Teams 會議，您必須確認已在 Azure Active Directory 中啟用Office 365 Yammer 服務的登入。 請依照下列步驟確認已啟用登入：
  - 移至 **Azure AD 系統管理中心**  >  **所有服務**  >  **企業應用程式**  >  **Office 365 Yammer**  >  **內容。**
  - 如 **需 [使用者可以** 登入？] 選項，請視需要選取 [ **是** ]。
- 確認您尚未在[Teams 應用程式](/MicrosoftTeams/manage-apps)中封鎖 Q&A (Native) 應用程式

## <a name="who-can-use-qa"></a>誰可以使用 Q&A

Q&A 可由下列使用者類型使用：

- 一般使用者：在您的租使用者中具有 Microsoft 365 認證的使用者。
- 同盟使用者：具有 Microsoft 365 認證至不同租使用者的使用者。
- 來賓使用者：任何您新增至 Microsoft Teams、SharePoint 或 Azure Active Directory 的來賓。

> [!NOTE]
> Q&A 將無法供僅供超過會議容量的 [檢視出席者] 使用。

當系統管理員啟用 Q&A 時，擁有 [召集人角色](https://aka.ms/GetQnA) 的使用者可以在建立或更新會議時開啟 Q&A。 透過 Teams 和 Outlook 會議選項，召集人也可以將 Q&A 從先前新增來阻止出席者使用此功能的會議中移除。

## <a name="use-the-teams-admin-center-to-manage-qa"></a>使用 Teams 系統管理中心管理 Q&A

您的組織可能會要求限制哪些召集人可以開啟 Q&A。 您可以使用 Teams 系統管理中心來管理哪些召集人可以在大型會議中開啟 Q&A。
請依照下列步驟控制哪些召集人可以使用 Q&A：

1. 在 Teams 系統管理中心，移至 **會議**  >  [**會議原則**](/meeting-policies-participants-and-guests)
2. 選取現有的原則或建立新原則，並為它命名為「這些召集人沒有 Q&A」
3. 捲動至 **名為「參與者&來賓」** 的節，選取 [問題 **&解答體驗]** 設定中的 [停用]，然後儲存原則
4. 將原則指派給您想要避免設定 Q&A 的特定 M365 群組、使用者或訂閱

## <a name="use-powershell-to-manage-qa"></a>使用 PowerShell 管理 Q&A

您的組織可能會要求限制哪些召集人可以開啟 Q&A。 您可以使用 PowerShell 來管理哪些召集人可以在大型會議中開啟 Q&A。

啟用 Q&A 的 PowerShell 命令範例：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>在 Teams 中刪除 Q&A 中的個別訊息

若要刪除 Q&A 應用程式中張貼的問題或答案，請遵循下列步驟：

1. 以全域系統管理員身分登入 Exchange 管理員 中心。
2. 移至 **[收件者**  >  **信箱]**，並依名稱搜尋召集會議的使用者。
3. 選取會議召集人，然後按一下 **[管理信箱委派]**。 在 [**讀取及管理]** 區段中，選取 **[編輯**  >  **新增許可權]**。
4. 將自己新增為會議召集人的代理人，然後選取 [儲存]。
5. 開啟Outlook Web App (而不是桌面) 中的 [Outlook 行事曆]，然後選取 [**新增行事曆**]，然後選取 [**從目錄新增]**。
6. 搜尋會議召集人，並將他們的行事曆新增至 **[我的行事曆]**。 選取之使用者的會議現在會顯示在您的行事曆上。
7. 在行事曆中，尋找您要刪除內容的會議、開啟會議記錄，然後選取 **[與參與者聊天]**。 選取 [與參與者聊天] 會在 Teams 中開啟會議聊天。
8. 流覽至 Teams 應用程式行中的 Q&A 應用程式。
9. 尋找您要刪除的任何問題或解答，然後選取 [刪除]。
10. 刪除內容之後，請返回 Exchange 管理員中心，並移除您自己作為會議召集人的代理人。

> [!NOTE]
> 如果您在移除答案之前先刪除問題，問題的第一個答案就會變成問題。
>
> 若要避免發生此問題，請依序執行下列步驟：
>
> 1. 找出您要刪除的問題
> 2. 刪除問題的答案
> 3. 刪除問題

## <a name="available-languages-for-yammer-versus-teams"></a>適用于 Yammer 與 Teams 的可用語言

Q&A 會預設為使用者的 Teams 語言。 當 Teams 與 Yammer 使用的語言不同時，將會發生下列語言預設值：

- 最接近的主要語言：如果有的話，Yammer 會預設為最接近的主要語言。 例如，Yammer 不提供加拿大法文 (fr-CA) 版本，因此它會改為以法文 (fr-FR) 顯示內容。
- 不支援的語言：如果 Yammer 完全不提供該語言，Yammer 預設會) 美國英文 (。

## <a name="ediscovery"></a>電子文件探索

適用于 Q&A 的 eDiscovery 與其他任何 Yammer 內容的 eDiscovery 運作方式相同。

- 如果您在租使用者的 Teams 應用程式中使用 Teams Q&A，不論您的 Yammer 網路設定或存在，此內容都可以在 eDiscovery 中使用。 若要將 eDiscovery 用於標準 Yammer 內容，您的 Yammer 網路必須處於 [原生模式](/yammer/configure-your-yammer-network/overview-native-mode)。
- 當您執行 eDiscovery 時，您可以判斷郵件是在 Yammer 中產生，還是透過 Teams 中的 Q&A 產生。 在 [檔案中繼資料] 區段中，您可以在 [專案類別] 欄位中找到該資訊。
- 如果您的組織使用由 Yammer 提供的 Teams Q&A，Q&A 所產生的內容會被視為 Yammer 內容，且可被搜尋。 如需 Microsoft 365 應用程式中電子檔探索的詳細資訊，請參閱 [Microsoft 365 中的電子檔探索解決方案。](/microsoft-365/compliance/ediscovery)
- 如果會議召集人啟用匿名張貼，則會將問題出席者文章內嵌到召集人電子檔探索的信箱中。

## <a name="data-storage"></a>資料儲存空間

Q&建立為會議一部分的郵件會儲存為 Yammer 郵件。 這些訊息會儲存在 Yammer 中，並供電子檔探索使用。
檔案一律儲存在 SharePoint 中，可處理所有資料的剩餘原則和位置。

下列指導方針說明如何儲存傳訊資料：

- Q&A 內容可透過 eDiscovery 搜尋，並在使用者層級Advanced eDiscovery。
- 郵件資料 (包含訊息內容) 會根據客戶的 Yammer 網路位置) ，預設儲存在 北美洲 或 EU (。
- 對於沒有現有 Yammer 網路的租使用者，Q&A Yammer 網路會在美國 Yammer 區域中建立。 貴組織的 Q&A 郵件一律會儲存在美國。
- 與 OneNote 索引標籤類似，從會議中移除 Q&A 並不會刪除會議資料。 從會議移除 Q&A 只會移除會議資料的存取權。 如果您新增 Q&A 索引標籤，您會再次看到所有會議交談。

## <a name="gdpr-for-qa-in-teams"></a>Teams 中 Q&A 的 GDPR

當您透過Microsoft 365 系統管理中心完成資料主體要求時，系統會自動將使用者的連絡人資訊從 Q&A 中的所有內容中移除。

## <a name="data-lifecycle-for-qa-in-teams"></a>Teams 中 Q&A 的資料週期

Teams 中 Q&A 所產生資料的生命週期取決於您在合規性中心的 Yammer 資料保留設定。 如果您透過 Azure Active Directory 實刪除會議中所有收到 Q&A 訊息複本的使用者，Yammer 會在使用者刪除後的 30 天內刪除該會議的 Q&A 內容複本。

## <a name="retention-and-deletion"></a>保留和刪除

保留內容會遵循 Yammer 的保留原則，無論您是否為 Yammer 和 Teams 設定了不同的原則。

> [!NOTE]
> 如果您的 Yammer 網路不是原生模式，在這裡建立的原則只會套用至 Teams Q&A 資料。 在原生模式中，所有 Yammer 使用者都位於 Azure Active Directory (Azure AD) ，所有群組都是 Microsoft 365 群組，所有檔案都會儲存在 SharePoint Online 中。

## <a name="faq"></a>常見問題集

**問：如何?匯出 Q&A 內容？**

**答：** Q&A 內容會儲存在Microsoft 365 合規性中心中，並透過 eDiscovery 存取。 未來的反覆運算將包含會議重點報告和會議召集人的匯出功能。

**問：Q&A 是否支援 Microsoft 365 Multi-Geo 功能？**

**答：** Q&A 目前不支援 Microsoft 365 Multi-Geo 功能。 Q&A 資料預設會儲存在 北美洲 或 EU (視客戶的 Yammer 網路位置) 而定。

**問：我可以在哪裡深入瞭解結構化會議？**

**答：** 請遵循以下 [最佳做法](/MicrosoftTeams/quick-start-meetings-live-events) ，在 Microsoft Teams 中成功主持大型會議。

**問：透過 Teams App Store 設定 Q&A 與使用會議選項有何不同？**

**答：** 我們已經簡化透過會議選項啟用 Q&A。自 2022 年 8 月起，Teams App Store 中的 Q&A 應用程式將不再受到支援，因此 Q&A 只能透過 [會議選項] 啟用。 如果您是透過 Teams App Store 啟用 Q&A 的會議召集人，請移除 Q&A 應用程式，而只透過 [會議選項] 啟用。

**問：為什麼我在會議中看到兩個 Q&A 圖示？**

**答：** 您會在會議中看到兩個 Q&A 圖示，因為 Q&A 也是透過 [會議選項] 啟用的。 請使用下列指示移除透過 Teams App Store新增的 Q&A 應用程式。 請針對您先前透過 Teams App Store 新增 Q&A 的所有會議執行此動作。

**如何移除從 Teams App Store 新增的 Q&A 應用程式。**

1. 在 Teams 電腦版上，加入您先前新增 Q&A 的會議。

2. 在頂端面板中，選取 Teams 會議視窗中第二個出現的 Q&A 圖示， 這是透過 Teams App Store新增的 Q&A 體驗。

3. 選取的 Q&A 索引標籤開啟時，按一下省略號，然後按一下 [移除]。 這會移除透過 Teams App Store 新增的 Q&A 體驗。

4. 按一下 [移除] 以永久移除透過 Teams App Store 新增的 Q&A 體驗。

> [!NOTE]
> 只有透過 Teams App Store 新增的 Q&A 應用程式才會有可移除 Q&A 應用程式的省略號。 透過 [會議選項] 啟用的 Q&A 體驗不會有省略號，也無法從這裡移除。

就是這樣！ 現在只有一個 Q&A 體驗 ， 由會議選項提供。 透過 Teams App Store 新增的 Q&A 應用程式會移除。
