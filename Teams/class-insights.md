---
title: Microsoft Teams 中 Education Insights 的 IT 系統管理員指南
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版中 Insights 的 IT 系統管理員指南。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9468047673f1832fdf9878bda123be181d21067c
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2022
ms.locfileid: "62190864"
---
# <a name="it-admin-guide-to-education-insights-in-microsoft-teams"></a>Microsoft Teams 中 Education Insights 的 IT 系統管理員指南

本文件提供讓 Education Insights 在 Microsoft Teams 中順利運作所需的步驟，並協助授課者和教育領導者採用平台並成功地使用該應用程式。

## <a name="overview"></a>概觀
**每個學生都有獨特的體驗、技能和心聲。**<br/>
**Insights 可協助您了解學生並回應其需求。**

Insights 可提供其班級內學生進度和活動的即時分析。 利用容易理解的視覺效果，學校社群可以主動且輕鬆地追蹤學生的體驗。 系統會為授課者和教育領導者提供有意義且可靠的資料，得以對其班級團隊做出明智的決策。 根據此資料，授課者可獲得要確保學生的情感、社交和學術需求能被滿足所需的資訊。  

當授課者知道哪些策略適合其學生時，學校社群就可以將精力集中，並達成更顯著的影響。 透過 Insights 提供的及時資料，授課者和教育領導者能夠將時間和精力聚焦於採行可提升學習環境、推動學生成功，以及並協助學習者成長的動作上。 

## <a name="who-uses-insights"></a>誰會使用 Insights？

### <a name="educators"></a>授課者
授課者是擁有班級團隊的任何人。 授課者可以包括教師、講師和教授。 

授課者可在班級層級存取 Insights。 他們會看到指派給其班級的學生活動，但無法存取來自其他班級的資料。 Insights 可協助授課者了解並支援其學生。

使用 Insights 沒有特別的必要條件，授課者只需要在 Teams 中將 Insights 新增至左側的應用程式列或以索引標籤形式新增至他們的每個班級即可。

授課者由教職員授權所識別。授課者必須擁有教職員授權，並成為班級團隊的擁有者，才能在 Insights 中查看資料。

### <a name="education-leaders"></a>教育領導者
教育領導者是機構中的所有角色，其需要組織面的檢視來了解其學生的參與、進度、狀況良好等等。如果授課者擁有班級團隊且需要較班級檢視更多的資訊 (例如專業科系主任)，則授課者也可以是教育領導者。 

教育領導者可能包括學務長、科系主任、校區領導者、學校校長、首席教師、顧問、專業科系主任、計畫主任、社交工作者和心理學家。

教育領導者會獲得組織的檢視，將視 IT 系統管理員指派的權限而定。例如，學校校區系統管理員可以查看他們存取的所有學校。 相反地，學校校長或學校主管只會看到學校的成績層級和班級。 

假設監督人也能授課，則會將其同時視為授課者和教育領導者，且可以存取 Insights 的這兩個檢視 (授課者和教育領導者)。 在這裡，Insights 可協助教育領導者支援授課者和學生。 在組織層級，IT 系統管理員必須連接學生資訊系統，並指派權限給每個角色，以存取與他們相關的學校或科系。

教育領導者會依教職員授權來識別，而且他們也需要來自 IT 全域系統管理員的 *明確權限*，才能檢視其組織的 Insights 報告。


> [!NOTE]
> **關於學生：**
>
> Insights 會收集關於 Teams 中學生活動的資料。
>
> 學生是 Teams 內班級團隊的成員。 依其授權加以識別，且他們 **無權存取** Insights 應用程式或索引標籤 (即使他們是團隊擁有者)。
>
> 來賓 *無法* 被視為學生。 



## <a name="where-do-users-find-insights"></a>使用者可在哪裡找到 Insights？
授課者和教育領導者可以採用不同的方式存取 Insights。 

### <a name="educators"></a>授課者
授課者可使用下列這兩個方法：

*   [個人應用程式](https://support.microsoft.com/office/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - 可從 Teams 左側應用程式列取得、其所有活動中班級的概觀，並能夠向下切入班級資料。
*   [索引標籤](https://support.microsoft.com/office/1386d1b4-3641-4a23-9b9c-0c6c774c2b6c) - 針對他們所擁有特定班級的 Insights，可從班級團隊上方瀏覽功能表的索引標籤取得。 此索引標籤可讓授課者處於 Teams 中的該班級時直接存取相關資料，以查看班級內容中的該資料。 

Insights 會呈現來自班級團隊內所有頻道的活動資料，但只能新增為公用頻道的索引標籤。 該索引標籤會反映來自非擁有者 (包括非班級團隊擁有者的授課者) 的班級團隊中每個人的活動。

在這兩個檢視中，授課者都可以存取班級資料。使用此個人應用程式，授課者必須向下切入班級層級，而使用索引標籤則可讓其直接存取班級資料。

在班級層級，如果某位授課者擁有班級團隊，就可以使用 Insights，而不需要 IT 系統管理員進行任何其他動作。

### <a name="education-leaders"></a>教育領導者
教育領導者可以使用 Insights 做為可從 Teams 左側應用程式列取得的 [個人應用程式](https://support.microsoft.com/office/8738d1b1-4e1c-49bd-9e8d-b5292474c347)。

在組織層級，IT 系統管理員必須連接學生資訊系統，並指派權限給每個角色，以存取與他們相關的學校或科系。

例如，校長只會看到其學校的班級，或是科系主任只會看到該科系的班級。 學生資料會於班級、科系、學校和校區層級彙總，而我們會在每個層級 (根據每位使用者的權限) 提供深入解析。授課者和教育領導者能夠放大審視並查看個別學生的資料。

**若要在 Teams 中新增 Insights 應用程式：**
* 按一下 "**…**" 於應用程式列上。
* 搜尋 **Insights** 並選取它。
* 描述畫面將隨即開啟。 按一下 [新增 **]**。

:::image type="content" source="media/insights-add-personal-app.png" alt-text="將 Insights 新增至 Teams。":::

* 在 Insights 圖示上按一下滑鼠右鍵，然後選取 **[釘選]**。

:::image type="content" source="media/insights-pin-app.png" alt-text="釘選 Insights 應用程式。":::

> [!TIP]
> 您也可以透過以下連結找到 Insights 應用程式：[https://aka.ms/addInsights](https://aka.ms/addInsights)

## <a name="when-is-insights-used"></a>Insights 的使用時機？ 
Insights 在整個 **學習週期** 支援學習社群。 透過多個維度的即時度量，Insights 可支援學校社群成員之間的識別、反映、討論和採取行動的持續循環。
*   **識別** 學生與授課者、課程教材及其同儕互動的方式和時間，以及他們執行作業的情況。 
*   **反映** 該意見如何支援學生以獲得成功，判斷成長領域，以及需要協助之處。
*   與學生和學校社群 **討論** 發現的項目，以強化關聯、目標設定、自我檢討、激發共同作業，並改善成果。
*   **採取行動** 來發展介入，提供有關成長領域的意見反應、修改教學策略，並識別需要的額外支援。

:::image type="content" source="media/insights-learning-cycle.png" alt-text="Insights 在整個學習週期支援學習社群。":::

## <a name="how-insights-works"></a>Insights 的運作方式為何？
Insights 可產生功能強大的分析，以協助授課者提供更完善的學習成果。其做法是透過分析 Teams 內的學生活動，並選擇性地運用您提供的學生資訊系統 (SIS) 資料來協助將活動情境化和分組。 

開始為您的機構部署 Insights 之前，請先快速查看 Insights 的運作方式、我們對資料道德的承諾，以及所需的授權。

### <a name="data-collection"></a>資料收集
將為 Insights 從 Teams 中的學生和授課者活動收集資料。不會收集來賓資料。

Insights *不會* 顯示關於授課者的資料。 資料的分析可提供可行的深入解析，以協助您參與教學和學習。

目前，資料會從班級團隊的以下幾個領域收集：

| Teams 元件   | 收集的資料 |
|-------------------|-----------------------------|
| **作業** | 開啟、繳交和對作業評分。|
| **頻道參與** |  造訪頻道、建立貼文、回覆貼文並按讚 (不包括聊天內容)。|
| **檔案** |   上傳、下載、存取、修改、註解及共用檔案 (不包括檔案內容)。|
| **OneNote 課程筆記本** |  編輯筆記本中的頁面或章節 (不包括頁面內容)。|
| **會議** |    出席 (不包括會議內容)。|
| **[朗讀進展](https://support.microsoft.com/topic/e71705a2-a79a-4d7e-bcef-a1e0aa336017)** |    準確度速率、最具挑戰的字詞，以及每分鐘的字數。  |
| **[反映](reflect.md)** |   簽入 (包括值)。|

> [!NOTE]
> 收集的資料多數會在幾分鐘內出現在 Insights 中。班級會議 (與其中一個班級頻道相關聯的會議) 中的出席資訊，會在會議結束後顯示幾小時 (通常最多為 24 小時)。

> [!NOTE]
> 在教育版分析中收集的資料會保留，直到 IT 系統管理員關閉 [[教育版分析切換]](#turn-sds-for-insights-on-or-off)，或租用戶 Office 訂閱結束為止。 關閉 Teams 中的特定功能不會刪除歷史資料。

### <a name="privacy-and-security"></a>隱私權和安全性
透過 Insights 收集和顯示的資訊，符合[超過 90 個法規和產業標準](/compliance/regulatory/offering-home)，其中包括 [GDPR](/compliance/regulatory/gdpr) 和針對學生與兒童安全性的[家庭教育權和隱私權法案 (FERPA)](/compliance/regulatory/offering-ferpa)，以及其他類似的以隱私權為導向法規。

資料屬於機構，而 Microsoft 只會收集資料並儲存資料。 Microsoft 人員無法存取資料或查看資料，除非合規性以經稽核的方式允許，以便維護服務 (例如資料復原)。

> [!NOTE]
> 若要深入了解 Microsoft 如何保護您的資料，請造訪 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。

### <a name="performance-and-reliability"></a>效能和可靠性
Insights 的設計可處理從 Teams 活動收集的大量資料，並具有最佳效能和可靠性。 我們無法保證 100% 的可用性，但我們會努力盡可能接近該目標。

資料收集程序會在不同伺服器上，針對 Teams 中的 Insights 索引標籤安裝進行。 Insights 索引標籤或個人應用程式不會影響使用其餘 Teams 功能的授課者和學生的應用程式效能或網路頻寬。

> [!TIP]
> 如需詳細資訊，請參閱[協助 Teams 教育版的低頻寬情況](edu-remote-low-bandwidth.md)。

### <a name="data-storage"></a>資料儲存
Insights 目前於歐洲和美國部署。 以歐洲為基礎的使用者資料會儲存在歐洲的伺服器上。 以澳洲和美國使用者為基礎的使用者資料會儲存在美國的伺服器上。 歐洲、澳洲或美國以外使用者的資料，會儲存在我們其中一個地理區域中。 

### <a name="using-data-ethically"></a>有道德地使用資料
我們致力於負責地且有道德地使用資料。 Insights 遵循 Microsoft 針對負責任的資料和 AI 的原則。 這表示我們對資料的使用方式是透明的，而我們會以授課者和學生的利益優先。  我們採用最高的安全性和隱私權標準，監視持續的可靠性和準確性，並確保您的機構的持續合規性。

Microsoft 從頭開始建立 Insights，以確保資料保護。 我們知道資料使用方式的潛在敏感度，並且重視您的資料和個人的隱私權。 

#### <a name="data-to-support-learning"></a>支援學習的資料
Insights 聚焦於學生學習和數位參與。 資料可支援學習，並展現數位學習平台上的學生參與層級。 雖然您可以向下切入班級活動的個別層級，但 Microsoft **並未指派任何正數或負數值** 指派給這些動作。 收集資料的目的是為了支援學生與授課者，以便達成最佳成果。

授課者最知道並了解其學生。 Insights 中提供的資訊可協助他們在數位學習案例中 **為學生提供支援**。 它會複製一般可在面對面體驗中獲得的深入解析。 例如，假設某個學生在特定期間未處於非活動中狀態，或未在上週準時完成其所有作業。 該資料會向授課者呈現，以便對學生適當催促或查勤。 與學生或與學生的家長或監護人進行互動仍為授課者的責任，以找出所偵測任何活動中或非活動中的基礎原因。

Insights 的設計可同時支援學生和授課者的數位學習環境架構。 Insights **不會直接擷取關於授課者的資料**。 除了個別的學生資料之外，它還為特定授課者提供學生活動和成果的彙總，以讓教育授課者可支援學生和授課者。

### <a name="licensing"></a>授權
若要存取 Insights，使用者必須具備適用於 Microsoft 365 的 A1、A3 或 A5 教職員授權。

*教育版 Insights Premium* 是付費的升級，為教育領導者提供教育版 Insights 資料的組織層級檢視，以及教育者對歷史資料檢視的擴充存取權。 合格的教育機構可以購買 *教育版 Insights Premium* 附加元件授權，方法是透過註冊教育版解決方案 (EES)、雲端服務提供者 (CSP) 和 Microsoft 365 系統管理中心 (Web 直接)。

組織可根據為租用戶中的所有數位活躍學生購買權限，使用 Education Insights Premium 附加元件。

## <a name="student-information-system-sis-integration"></a>學生資訊系統 (SIS) 整合
送入 Insights 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。

若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。 

以班級授課者身分檢視班級層級的 Insights 並 *不需要* 此動作，因為我們會使用 Teams 的班級結構和權限。

若要深入了解，請參閱 [**將學生資訊系統 (SIS) 資料與 Education Insights 同步處理**](education-insights-sis-data-sync.md)。

## <a name="manage-permissions"></a>管理權限
身為 IT 系統管理員，您必須為教育領導者、校區領導者、學校校長、首席教師、顧問、學習領域主任、計畫主任、社交工作者和心理學家提供權限。 當授課者擁有班級團隊時，系統就會 *自動* 提供其權限。

若要深入了解，請參閱 [**管理 Education Insights 的使用者存取權**](education-insights-manage-access.md)。

## <a name="manage-the-setup-policy"></a>管理設定原則
身為 IT 系統管理員，您可以使用應用程式設定原則，在授課者和領導者啟動 Teams 時，預設為其安裝 Insights。 使用設定原則，您可以自訂 Teams 以突顯 Insights，並將它釘選在應用程式列中。

如果授課者想要直接存取每個班級，他們可以在上方瀏覽功能表手動安裝 Insights 索引標籤。 此索引標籤可讓授課者處於 Teams 中的該班級時直接存取相關資料，以查看班級內容中的該資料。 

在這兩個檢視中，授課者都可以存取班級資料。使用此個人應用程式，授課者必須向下切入班級層級，而使用索引標籤則可讓其直接存取班級資料。

> [!TIP]
> 如需詳細資訊，請參閱[適用於教育界的 Teams 原則和原則套件](./policy-packages-edu.md)。

## <a name="encourage-the-adoption-of-insights"></a>鼓勵採用 Insights
讓您的教育機構對於使用 Insights 感到振奮。

您可以隨意將下列資料發佈給 **授課者**：
*   如需詳細說明，請查看 [ Insights 支援頁面](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)。
* 快速啟動並執行 - [取得 Insights 一頁式 PDF](https://aka.ms/insights/start)。
*   閱讀[完整的 PDF](https://aka.ms/insights/guide)。
*   觀看[逐步教學課程](https://aka.ms/insights/resources)以了解如何使用 Insights。
*   使用 Microsoft 教育工作者中心[免費的 Insights 課程](https://aka.ms/insights/course)訓練您自己
*   最後，查看 Insights 專屬的[此部落格](https://techcommunity.microsoft.com/t5/education-blog/6-ways-to-be-insight-ful-and-support-student-engagement/ba-p/1903091)。

適用於 **教育領導者** 的資料：
*   [適用於教育組織支援頁面的 Insights](https://support.microsoft.com/office/8738d1b1-4e1c-49bd-9e8d-b5292474c347)。

### <a name="turn-insights-on-or-off"></a>開啟或關閉 Insights

根據預設，會開啟 Insights，這可讓我們收集 Teams 中學生活動的分析，以用於 Insights。 您可以決定退出 Insights，在這種情況下，我們會 *刪除 Insights 已收集的所有資料*，並停止收集任何未來的資料。 若您重新開啟 Insights，我們就會從重新啟用的時間開始收集資料。

* 若要關閉/開啟 Insights，開啟 [[SDS 系統管理中心]](https://sds.microsoft.com/)，並移至 **[設定]** > **[管理教育版 Insights]**。 關閉/開啟 **收集 Insights 活動資料**，以啟用或停用 Insights。

:::image type="content" source="media/insights-settings.png" alt-text="SDS 系統管理中心頁面的螢幕擷取畫面，您可以在此設定選項開啟或關閉 Insights。":::

> [!NOTE]
> 如果您已關閉 Insights，系統將會刪除已收集的資料。 即使重新啟用 Insights，選擇退出時已刪除的資料以後無法恢復。

### <a name="turn-sds-for-insights-on-or-off"></a>開啟或關閉 Insights 的 SDS

學校資料同步處理 (SDS) 可協助您將與 Teams 進行學生資訊系統 (SIS) 資料的匯入與同步處理自動化。

使用 Insights *不要求* 使用 SDS。 不過，您可以隨時選擇退出 Insights。 

* 若要關閉 Insights 使用學校資料同步處理，請遵循 [停用適用於 Insights 的 SDS](/schooldatasync/how-to-deploy-sds-for-insights#disabling-sds-for-insights) 中的指示。

* 若要重新開啟，請遵循 [如何部署適用於 Insights 的 SDS](/schooldatasync/how-to-deploy-sds-for-insights) 中的指示。

### <a name="how-to-delete-your-data"></a>如何刪除您的資料
Insights 會儲存在班級團隊內容中執行的學生和授課者動作。 此資料被視為混合資料集，因此，一旦從組織中刪除了學生或授課者的使用者帳戶，就不會自動從服務中刪除。
附註：刪除資料會損及 Insights 分析一段時間班級團隊參與度的能力。
* [開啟支援票證](https://aka.ms/edusupport)。 支援票證必須明確聲明對 [GDPR Delete DSR] 操作的請求，並包含要刪除的使用者物件識別碼。 無法限制刪除的資料集或時間窗口。
*   一旦提出，支援票證就會在佇列中等候一週，以符合合規性的最低保留原則。 您可以在此期間取消該作業。
*   一週之後，Education Insights 團隊會確保與該使用者識別碼相關的所有資料都已從服務中刪除。 Microsoft 支援服務會監視該票證，並會在刪除程序完成後 28 天內通知您。

## <a name="troubleshooting"></a>疑難排解
### <a name="why-doesnt-my-institution-see-any-data-in-insights"></a>為什麼我的機構在 Insights 中看不到任何資料？
如果這是 *新的* 租用戶，且您 *未曾* 在 Insights 中看到資料，請檢查您的租用戶 **已以教育租用戶的身分通過驗證**，才能存取 Insights。 與您的 Microsoft 帳戶管理員連絡，請求他們檢查該租用戶是否正確設定。

如果您沒有帳戶管理員，請開啟票證。 移至 [Office 365 系統管理中心 []](https://admin.microsoft.com/AdminPortal/)  >  [支援 **]**  >  [新增服務要求 **]**。  在票證標題中，撰寫：「需要協助進行教育驗證」。
 
此外，請確認已為 Insights 啟用資料收集。雖然其預設會開啟，但 IT 系統管理員可能已將它關閉，並因而已刪除 Insights 所擁有的所有資料。

若要加以確認，請開啟 [SDS 系統管理中心](https://sds.microsoft.com)，並移至 **[設定]** > **[管理 Education Insights]**。 檢查‘收集 Insights 活動資料’的狀態。

如果已關閉，請將其重新開啟。Insights 會開始收集資料，但可能需要最多 24 小時的時間，才能在報告中看到資料。 


### <a name="why-do-i-see-data-for-some-students-or-classes-not-all"></a>為什麼我會看到部分學生或班級的資料，而非全部？
我們只會收集經 *授權* 學生的資料，因此最可能的原因是您的學生以來賓身分參與班級，因此不會收集其資料。 您可能會看到他們的名稱，但沒有任何資料。

檢查學生的狀態，以確保他們都擁有學生授權。 

### <a name="why-dont-educators-see-meeting-data"></a>為什麼授課者看不到會議資料？
要在 Insights 報告中看到會議資料，最多需要 24 小時的時間。 因此，請檢查是否已超過足夠的時間。

此外，請檢查學生 *並未*[在沒有 Teams 帳戶的情況下加入班級會議](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)。 在這種情況下，系統不會收集該學生的活動。

> [!TIP]
> 針對想要追蹤學生出勤的授課者，您可以建議其在會議期間傳送訊息以要求學生回覆。這麼做可在幾分鐘內註冊其出席。

> [!NOTE]
> 如果您的問題仍未獲得回覆，請[開啟支援票證](https://aka.ms/edusupport)。 請包含代表問題的相關螢幕擷取畫面和問題發生的日期。 新增您認為可能有助於我們解決問題的任何其他資料。

### <a name="what-licenses-do-i-need-to-activate-education-insights-premium"></a>我需要哪些授權才能啟用教育版 Insights Premium？
為了為您的組織啟用教育版 Insights Premium，租用戶必須根據組織租用戶中數位活躍學生的數量購買權限。 也就是說，對於所有使用 Teams 課程作為其學校作業的一部分進行會議、交流、聊天、作業、編輯文件、課堂筆記本或反思等活動的學生。

