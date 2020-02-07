---
title: Teams 中的生命週期管理方案 - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 了解如何在 Teams 中規劃生命週期管理功能的實作。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 783ae4f1c293a51b5f9838d4ffa3039731c0c867
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837353"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Teams 中的生命週期管理方案

Teams 提供的豐富工具組可以在您組織中實作共同作業的生命週期管理流程。 本文將指引 IT 專業人員，透過正確的問題來判斷其生命週期管理的需求，以及使用符合需求的工具。 

生命週期管理的規劃至關重要，因為這表示您正在建立的方案可以更有效率地完成工作。 大部分的專案都包含有開始、中期和結束等階段。 Teams 也一樣，但是因為專案的建構和使用方法五花八門，以至於不容易判斷專案目前進行到其生命週期的哪個階段。 對生命週期管理進行規劃，有助於您隨著組織專案的各個階段進程加以追蹤。

> [!Tip]
> 請觀賞下列一段影片以深入了解 Microsoft Teams 中的生命週期：[Microsoft Teams 中的控管、管理和生命週期](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>生命週期的概念

下列概念和定義全都會影響您對生命週期管理所做的決定。

**團隊**

_團隊_是促進共同作業的人員、內容和工具的集合。 團隊會定義其成員，以及會套用到這些成員的權限和原則。 Teams 的建置基礎為 Office 365 群組，因此 Office 365 群組成員資格的變更會同步至團隊。 和其他 Office 365 群組一樣，Teams 會在 Office 365 內自動佈建 Exchange 信箱、SharePoint 網站、OneNote 筆記本和其他資產。 [深入了解 Office 365 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

**頻道**

頻道是團隊實際完成工作的共同作業空間。 每個頻道代表整個團隊中不同的主題或工作流程。 針對每個頻道，系統會自動在 SharePoint 網站上建立一個資料夾，儲存該頻道共用的所有檔案，讓使用者能夠輕鬆尋找及處理他們所關注的文件。 您也可以使用與特定工作流程相關的應用程式來擴充頻道，例如，您可以將 Power BI 儀表板新增至頻道，追蹤專案某一層面的成功。

**團隊存取類型**

這些設定決定誰可以加入團隊：

-   _私人_團隊限團隊擁有者核准的團隊成員。 這是大型組織中專案團隊和虛擬團隊的標準設定。
-   _公開_團隊對組織中的任何人開放，任何人都能直接加入。 這項設定對於在不同專案中工作的不同部門人員、針對一般興趣的主題進行共同作業時非常有用。 這是非常適合小型組織的預設設定。

**團隊使用者類型和系統管理員角色** 

團隊使用者類型決定團隊成員擁有的控制權：

-   _團隊建立者_擁有可以在目錄中建立群組或團隊的權限。 系統管理員可以將此使用者類型限制為系統管理員或使用者的子集。 如需詳細資訊，請參閱[管理能建立 Office 365 群組的使用者](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) (英文)。 
-   _團隊擁有者_管理團隊的成員資格和設定。 每個團隊最多可以有 100 位團隊擁有者。
-   _團隊成員_是參與團隊的組織成員。
-   _來賓_是組織外部的使用者。 如果您的組織已啟用[來賓存取](guest-access.md)，則擁有電子郵件地址的任何人都可以受邀成為來賓。

> [!Note]
> 若要深入了解團隊擁有者和團隊成員的能力，請參閱[在 Microsoft Teams 中指派角色和權限](assign-roles-permissions.md) (英文)。

Teams 系統管理員角色決定每個系統管理員角色持有者所擁有的能力。 下表將說明這些角色。

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">角色&nbsp;&nbsp;</th>
    <th width="25%">說明</th>
    <th width="60%">可以使用標註的工具執行下列工作</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Teams 服務管理員</td>
    <td valign="top">管理 Teams 服務，建立和管理 Office 365 群組</td>
    <td valign="top">管理會議，包括會議原則、組態和會議橋接器<sup>1</sup><br><br>管理語音，包括通話原則、電話號碼的庫存和指派、通話佇列以及自動語音應答<sup>1</sup><br><br>管理訊息，包括訊息原則<sup>1</sup><br><br>管理所有的全組織設定，包括同盟、Teams 升級和 Teams 用戶端設定<sup>1</sup><br><br>管理組織中的團隊及其相關設定，包括成員資格<sup>2</sup><br><br>透過使用進階的疑難排解工具組<sup>3</sup>，檢視使用者設定檔頁面，並針對使用者通話品質問題進行疑難排解</td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通訊系統管理員</td>
<td valign="top">管理 Microsoft Teams 服務內的通話和會議功能</td>
<td valign="top">管理會議，包括會議原則、組態和會議橋接器<sup>1</sup><br><br>管理語音，包括通話原則、電話號碼的庫存和指派、通話佇列以及自動語音應答<sup>1</sup><br><br>透過使用進階的疑難排解工具組<sup>1</sup>，檢視使用者設定檔頁面，並針對使用者通話品質問題進行疑難排解</td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通訊專家</td>
<td valign="top">使用基本工具在 Teams 內針對通訊問題進行疑難排解</td>
<td valign="top">存取使用者設定檔頁面，以便在通話分析中針對通話進行疑難排解。 針對搜尋所得的特定使用者，僅能檢視使用者資訊。<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通訊支援工程師</td>
<td valign="top">使用進階工具針對 Teams 內的通訊問題進行疑難排解</td>
<td valign="top">存取使用者設定檔頁面，以便在通話分析中針對通話進行疑難排解。 可以檢視完整的通話記錄資訊。<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell - 商務用 Skype 模組</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell - Microsoft Teams 模組</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">僅 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>開始使用前必須做出的 IT 決策

在向組織推出 Teams 前，請先實作組織已決定為必要的任何控管原則。 這些原則包括如命名慣例、到期原則、保留原則等項目。 一般來說，在組織內放大部署之前實作這些需求會較為容易。

如需詳細資訊，請參閱 [Teams 中的控管方案](plan-teams-governance.md)。

## <a name="teams-lifecycle-stages"></a>Teams 生命週期階段

一般來說，團隊的目的與專案一致或與完成目標有關。 即使團隊是根據共同的興趣而形成，團隊的成員資格可能會隨著時間而有所變更，討論內容顯得陳舊過時，只是在不同的團隊中以稍微不同的方式再次呈現。

每個團隊都有開始，就是團隊建立和頻道設定的時候；中期時，團隊會被使用且共同作業會發生以符合工作流程的節奏；接著 (有時) 是結束，團隊會完成其目的並到達使用期限的終點。 

如需詳細資訊，請參閱[在 Microsoft Teams 系統管理中心管理團隊](manage-teams-in-modern-portal.md) (英文)。

### <a name="stage-1-beginning"></a>階段 1：開始

#### <a name="create-the-team"></a>建立團隊

第一個步驟是定義團隊的目標 (範圍可從商務流程到組織結構再到專案，或者只是建立開放、未結構化的共同作業中心)。 定義團隊的目標與找出正確的人員有密不可分的關係。 在可行的情況下，透過以廣泛成員資格為目標來促進開放式共同作業不失為一個好方法。 

團隊擁有者可以邀請團隊成員、設定團隊圖片和說明，以及設定個別成員的權限。 

> [!Tip]
>  為顧及缺席或重新指派的情形，最佳做法是找出至少兩位團隊擁有者。

#### <a name="team-origins"></a>團隊來源

團隊來源可以有各種不同的方法，包括：

-   從頭開始建立團隊。 使用個人的電子郵件別名或使用者名稱新增成員，或是展開通訊群組清單。
-   從現有團隊建立團隊，然後使用該團隊的頻道設定和任何應用程式設定做為範本。 您也可以選擇使用該團隊的成員資格清單。
-   將團隊新增至現有的 Office 365 群組，這樣也可讓團隊存取信箱和 SharePoint 網站。
-   使用 Microsoft Graph Teams API 或 PowerShell Cmdlet 建立團隊。 API 可以根據全域通訊錄的屬性 (例如地區或部門) 或商務流程 (例如客戶參與或教室名冊)，透過程式設計的方式建立團隊。

請利用下列連結取得更多有關組織團隊的詳細資訊：

-   [在 Teams 中組織團隊的最佳做法](best-practices-organizing.md) (英文)
-   [部署交談、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md) (英文)
-   [部署會議和研討會](deploy-meetings-microsoft-teams-landing-page.md) (英文)
-   [部署雲端語音](cloud-voice-landing-page.md) (英文)


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>團隊的目的為何？</li><li>哪些人屬於團隊？</li><li>小組是私人還是公開的？</li><li>新成員可以自行加入，還是須由小組擁有者將其加入？</li><li>哪些人擁有可以建立頻道或新增索引標籤、Bot 和連接器的權限？</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>建立團隊。</li><li>規劃頻道。</li></ul>|


#### <a name="set-up-channels"></a>設定頻道

任何擁有適當權限的團隊擁有者或成員都能在團隊中建立頻道。 請務必將每個頻道的目標納入考量，您的選項包括有與專案相關的共同作業、主題的討論或共同興趣的領域等。 依預設，每個團隊都包含有 [一般] 頻道；大部分團隊的需求不只這一個，因此成員會建立額外的頻道。 頻道組很可能會隨著新主題或專案的提出而蓬勃發展，討論的成長比成員剛加入頻道時更為快速。

為引起興趣，頻道擁有者可以張貼歡迎訊息，將相關文件上傳至 [檔案]**** 索引標籤，或是在頻道中新增索引標籤或連接器。 擁有者也可以設定頻道的說明，可以將重要頻道「自動加入我的最愛」，使這些頻道能夠依預設對所有團隊成員列出。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>團隊中會新增哪些初始頻道？</li><li>如果有的話，系統可以針對新增新頻道提供哪些指引？ (這些頻道的設定依據是專案、主題或是...？)</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>建立初始頻道。</li><li>張貼歡迎訊息。</li><li>開始共同作業。</li></ul>|

### <a name="stage-2-middle"></a>階段 2：中期

隨著團隊合作的開始，團隊的成員資格可能會隨著頻道階層開始演進。 除非團隊需要進行嚴格的控制和鎖定，否則鼓勵深入探索不失為一個好主意，即使探索沒有結果。 隨著使用者逐漸熟悉，他們可以試驗使用 \@團隊提及、將頻道標示為我的最愛，以及使用 [一般] 頻道來熟悉張貼功能。 每個團隊都是獨一無二的；讓使用情況指引設計的演進。 透過團隊報告功能監視團隊的使用情況和健康情況。

信賴、包容和共同作業的精神會蓬勃發展，因為關鍵的群組溝通可以在 Teams 中起始並延續下去。 比起一對一交談，團隊成員更加看重群組交談的實用性。 個別團隊傾向借助有趣的功能 (如 Giphys 和貼紙) 開發出自己的風格。 同時，有一點很重要，就是任何時候都不鼓勵惡意或無禮的行為。

團隊並非一成不變，因此需要偶爾的監督和照料。 以下是一些最佳做法：

-   如果使用率開始往下掉，利用風雲人物維持使用率，同時間可以探索和傳播有創意的新行為。 
-   謹慎地管理來賓，確保來賓的存取權在業務需求結束時終止。
-   讓頻道隨著業務需求而演進，必要時新增新頻道並使舊頻道逐漸退場 (或者，如果頻道包含有敏感性或暫時性資料，您可以根據保留需求，考慮封存或刪除頻道)。
-   隨著大型群組或興趣型領域的出現，打造全新的團隊。
-   嘗試不同頻道的共同作業，例如與文件相關的頻道會議或索引標籤交談。

如果團隊開始停滯不前，請考慮：

-   在團隊中推動溝通，而不是使用電子郵件。
-   使用行動應用程式提升互動。
-   縮減頻道數量。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>誰負責監視使用情況以找出問題？</li><li>將使用哪些指標來判斷團隊的健康情況？</li><li>找出任何已到達使用期限的團隊。</li><li>找出狀況不良但仍在使用、而需要重整的團隊。</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>實作一個流程來監視個別團隊的健康情況。</li></ul>|

### <a name="stage-3-end"></a>階段 3：結束

當團隊的工作持續到自然結束，正式知悉團隊已結束非常重要。 這樣可以讓團隊成員感覺到團隊已關閉，也可以避免任何人存取過期過時的資訊。 您可以利用團隊本身來舉辦如事後剖析和執行摘要等的關閉儀式。

您可以刪除您了解已不再需要的團隊 (例如專為測試而建立的團隊，或是含有敏感性資料的團隊)。 實際上，團隊會以「虛刪除」的方式刪除，IT 人員最多可以在 21 天內回復 (Office 365 群組為 30天)。 刪除團隊不會影響依照合規性原則而保留的任何交談或內容。 頻道也有「虛刪除」，而且可以在刪除後最多 21 天內回復。

除了封存功能之外，您也可以使用到期和保留原則，針對不再使用的團隊或是擁有者已離開組織的團隊，減少這些團隊的曝光率。

如需設定到期和保留原則的相關資訊，請參閱 [Microsoft Teams 中的安全性與合規性概觀](security-compliance-overview.md) (英文)。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>定義團隊生命週期結束的形式。</li><li>決定是否要保留團隊的內容，以及要保留多久。</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄最佳做法和經驗傳承。</li><li>封存資料 (如有需要)。</li></ul>|

## <a name="related-topics"></a>相關主題

[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)
