---
title: 規劃通話資料連線器 |通話品質儀表板監視混合式分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在混合式案例中使用商務用 Skype Online 遙測工具來監控內部部署實現的概覽。
ms.openlocfilehash: 3300ad17b109ac069c4f7382f610dd0214b30197
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328425"
---
# <a name="plan-call-data-connector"></a>規劃通話資料連線器

## <a name="overview"></a>概觀

本主題說明實現商務用 Skype Server 通話資料連線器的優點、規劃考慮及需求。 如需設定呼叫資料連線器的詳細資訊，請參閱[設定呼叫資料連線器](configure-call-data-connector.md)。


呼叫資料連線器極大地簡化了混合式環境中的呼叫監視，因為您不再需要使用不同的內部部署和線上工具來監控所有使用者的通話品質。 無論您的使用者是駐留在內部部署還是線上，您都可以選擇在線上查看整個組織的通話品質。

使用 [呼叫資料連線器]，您可以使用單一工具集來執行下列工作：

- 在 Microsoft 團隊、商務用 Skype Online 和商務用 Skype Server 上監控您的使用者體驗。

- 在您的網路上查看問題並進行疑難排解。

- 指派呼叫分析的 [支援人員] 和 [系統管理員] 角色，讓技術支援人員能查看並疑難排解其職責範圍。

使用呼叫資料連線器時，商務用 Skype 伺服器會將資料推入雲端服務，以便您利用商務用 Skype Online 通話分析（CA）和通話品質儀表板（CQD）工具，如下圖所示：

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-1.png)

伺服器會將體驗品質（QoE）推入，並呼叫詳細資料錄製（CDR）資料至線上服務。

[通話分析] 和 [CQD 工具] 可讓您監控通話品質，以及使用 Microsoft 團隊與商務用 Skype 服務的連線問題進行疑難排解，如下所示：

- 呼叫分析重點針對特定通話的品質問題。 它會顯示商務用 Skype 帳戶中每位使用者的通話與會議的詳細資訊。  有了呼叫分析，您就可以將許可權指派給支援人員的操作員，而不需存取其餘的商務用 Skype 系統管理中心，就可以監視通話。

- [通話品質儀表板] 重點說明整個組織的網路效能與問題。 商務用 Skype 系統管理員和網路工程人員使用這個工具來疑難排解及優化網路效能。

如需詳細資訊，請參閱[通話分析和通話品質儀表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。

當然，您可能會想要在內部部署中保留一些通話品質資料。 例如，如果您使用的是協力廠商解決方案，且已自訂報表與工作流程，則可能是這種情況。  [通話資料連線器] 可讓您設定將資料傳送至線上服務，同時也會在您的內部部署伺服器上保留一份資料複本，如下圖所示：

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype 伺服器。  如需有關部署商務用 Skype Server 和支援的拓撲的詳細資訊，請參閱[拓撲結構基礎](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。 若要設定呼叫資料連線器，您必須：

- 啟用混合式連接。 如果您已部署商務用 Skype Server 且想要啟用呼叫資料連線器，您必須確保您在內部部署與線上環境之間已設定混合式連接。 這有時稱為分割網域配置。

   如需詳細資訊，請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md)，以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 驗證您的 Office 365 租使用者，並確認您已啟用下列角色：

  - 商務用 Skype Server 系統管理員
  - Office 365 全域系統管理員

- 如果您尚未這麼做，請開啟 [通話品質儀表板]，如[開啟並使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述。

- 使用 local LCSCdr 和 QoEMetrics 資料庫啟用監視的前端池。 若未這麼做，通話資料連線器將無法使用公制資料。

> [!IMPORTANT]
> 如果未在前端池中啟用監視，則呼叫資料連線器將無法運作。

- 已正確設定[伺服器對伺服器驗證](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)。 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>內部部署與線上通話品質儀表板（CQD）報告的比較

| 功能報告 | 商務用 Skype Online | 商務用 Skype 伺服器   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 應用程式共用躍點數 |是的 | 受 |
| 客戶建築物資訊| 是的 | 是的 |
| 向下切入分析 | 是的 | 不 |
| 媒體可靠性度量單位 | 是的 | 受 |
| 外框報告 | 是的 | 是的 |
| [總覽] 報表 | 是的 | 不 |
| 每位使用者報告 | 是的 | 是的 |
| 報表集自訂 <br> （[新增]、[刪除]、[修改報告]） | 是的 | 是的 |
| 以影片為基礎的畫面共用規格 | 是的 | 不 |
| 以程式設計方式存取的資料 Api <br> 若要 CQD | 不 | 是的 |
||||
