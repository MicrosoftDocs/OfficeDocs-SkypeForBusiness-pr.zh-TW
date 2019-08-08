---
title: 部署 Microsoft 團隊雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下載網站啟用行動手冊以規劃您的團隊推出, 並加速及優化使用者採納、品質與滿意度。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17b73629aa874232a449605b45f97ea10e445204
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233027"
---
# <a name="deploy-my-service"></a>部署我的服務

本文將提供正確部署雲端語音服務的需求概覽。 透過遵循部署雲端語音服務的規範性指導方針, 您可以確定您已成功地考慮所有需求, 並提供可重複的結果。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft 團隊語音工作負載的 [網站啟用] 行動手冊

使用這項行動手冊, 協助您的組織以網站為基礎, 順利規劃並執行 Microsoft 團隊語音功能。

包括所有必要的活動、建議的時程表, 以及每個活動的相關指南的連結, 此行動手冊會涵蓋端對端指導方針, 以協助確保針對特定網站成功的小組語音部署, 並將重點放在重要因素上給使用者。

透過完成本行動手冊中的活動, 您的組織可以:

-   有效規劃並排程您的團隊推出。

-   加速並優化使用者採用。

-   減少支援需求並提高使用者滿意度。

> [!NOTE]
> 本文和相關的行動手冊並不是用來描述服務啟用所需的每個技術設定步驟, 或提供撥號音給特定網站。 相反地, 他們會將重點放在快速的使用者的活動和工作上, 並讓他們透過快速且流暢的過渡來開始使用團隊語音作業, 同時將支援需求降至最低。 如需如何針對團隊語音設定您的環境的最佳技術指導方針, 請參閱設定[小組語音工作負載](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)的 [[直接佈線](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)]、[團隊[核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)]、[[網路]針對團隊](onboarding-checklist-configure-networking.md), 並[啟用 Office 365](onboarding-checklist-enable-office-365.md)。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>行動手冊焦點區域

行動手冊的重點是解決影響使用者對小組語音部署所感覺的因素。 活動和工作會分為下列焦點區域:

-   驗證服務準備
    - 音訊會議
    - 通話方案
    - 直接路由

-   使用者啟用

-   端點

-   使用量與品質

-   促進

[[網站啟用行動手冊] 語音 (行動手冊)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 活頁簿。 這五個焦點區域中的每一個都是活頁簿中的個別工作表, 而每個部署工作和活動都會群組到其中一個工作表上。

![[網站啟用行動手冊] 的螢幕擷取畫面](media/deploy-my-service-image1.png "行動手冊的螢幕擷取畫面")

> [!NOTE]
> 您將針對團隊推出的範圍內的每個網站, 建立一個單獨的行動手冊實例。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>如何使用行動手冊

無論位置為何大小和複雜度, 都能讓每個網站都能儘早規劃您的工作和活動, 並在實際的服務推出期間和之後以最佳循序執行這些作業。 我們建議您在規劃並執行自己的 Microsoft 團隊語音時, 按照這些步驟進行。

1. 下載 [[網站啟用] 行動手冊 (適用于 Microsoft 團隊語音的語音 (行動手冊)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 。

2. 針對每個網站分別建立 [行動手冊] 複本。

3. 在名為 [**行動手冊] {SiteName-code}** 的工作表索引標籤上, 將 **{sitename 程式碼}** 取代為相關的網站名稱和/或網站程式碼。

4. 輸入**網站名稱、網站程式碼**及**規劃的啟動日期**, 如下所示。 這是一個重要的步驟, 因為它會針對行動手冊中的每個活動調整建議的截止時間。

   ![包含網站名稱、網站程式碼及規劃啟動日期的範例](media/deploy-my-service-image2.png "含紐約網站名稱、網站程式碼 NY01 及規劃啟動日期為20年3月18日的範例")

5. 查看每個活動、執行必要的動作, 並在您逐步完成時程表時更新狀態。 狀態以圖形表示, 如下所述:
  
   - ![綠色核取記號](media/deploy-my-service-image3.png)為 **[是] 或 [不適用 (綠色)]** 的圖例: 活動已完成, 或不適用於此網站, 因此不需要進一步的動作。</li>
   - ![黃色驚嘆號](media/deploy-my-service-image4.png)的圖例<strong>該活動尚未完成 (黃色):</strong>此活動尚未完成, 且必須在排程上更新為 [是] 或 [否]。</li>
   - ![紅色 X 的圖例, 代表 [](media/deploy-my-service-image5.png)否] <strong>(紅色):</strong>由於問題而無法完成活動, 且必須傳送給專案狀態會議。</li></ul>

6. 狀態是在每個區段中累計, 而節標題則是以其中一個狀態指標來設定格式。 [**每週] 狀態**也會自動更新。

[![行動手冊] 中每週狀態匯總的螢幕擷取畫面][(media/deploy-my-service-image6.png "行動手冊] 中每週狀態匯總的螢幕擷取畫面")

> [!TIP]
> 針對您所有的位置, 重複上述步驟。

> [!IMPORTANT]
> 某些步驟可能不適用於所有位置與網站。 如果特定活動與網站無關, 您必須選取 [**不適**用於此活動]。 **請勿刪除**[行動手冊] 中的任何資料列;如果您這樣做, 狀態匯總公式將無法運作。<br/><br/>
請注意, 可能會花費比您計畫更多時間的活動 (例如, 數位移植與採購活動)。 這些活動可能會對網站部署時程表造成負面影響。 請務必查看並更新活動清單及相關聯的時程表, 並在[指導委員會會議](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)中展示, 以確保專案關係人知道每個網站的狀態, 以及部署排程的任何可能的偏差。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定您的部署是否需要網站啟用行動手冊。</li><li>針對您要部署的每個網站, 決定誰將負責為 Microsoft 團隊自訂 [網站啟用] 行動手冊。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下載網站啟用行動手冊</a>。</li><li>針對您的第一個網站自訂 [網站啟用] 行動手冊。</li><li>視需要重複其他網站的步驟。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->