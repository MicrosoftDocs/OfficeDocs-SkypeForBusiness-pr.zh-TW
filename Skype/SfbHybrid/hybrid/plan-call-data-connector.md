---
title: 規劃通話資料連線器 |通話品質儀表板監控混合式分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 使用商務用 Skype 線上遙測工具來監視混合式案例中的內部部署實施，以瞭解如何使用線上遙測工具。
ms.openlocfilehash: a0288f07c942f003cfece5aceaddf4139af84569
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407172"
---
# <a name="plan-call-data-connector"></a>規劃通話資料連接器

## <a name="overview"></a>概觀

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題說明執行商務用 Skype Server 呼叫資料連線器的優點、規劃考慮和需求。 如需設定呼叫資料連線器的詳細資訊，請參閱 [設定呼叫資料連線器](configure-call-data-connector.md)。


呼叫資料連線器大幅簡化混合式環境中的呼叫監控，因為您不再需要使用不同的內部部署和線上工具來監視所有使用者的通話品質。 不論您的使用者是位於內部部署或線上，您可以選擇線上查看整個組織的通話品質。

使用「呼叫資料連線器」，您可以使用單一工具集來執行下列工作：

- 監控使用者對 Microsoft Teams、商務用 Skype 線上及商務用 Skype Server 的體驗。

- 查看並疑難排解整個網路的問題。

- 指派呼叫分析的「服務台」和「系統管理員」角色，讓輔助技術人員能夠查看及疑難排解其職責範圍。

使用呼叫資料連線器時，商務用 Skype Server 會將資料推送至雲端服務，以便您可以利用商務用 Skype 線上呼叫分析 (CA) 及通話品質儀表板 (CQD) 工具，如下圖所示：

![SfB 雲端語音信箱圖表。](../../sfbserver2019/media/call-data-connector-plan-1.png)

伺服器會將經驗品質 (QoE) 和詳細通話記錄 (CDR) 資料到線上服務。

通話分析和 CQD 工具可讓您監視通話的品質，並使用 Microsoft Teams 和商務用 Skype 服務來疑難排解連線問題，如下所示：

- 呼叫分析著重于特定通話的品質問題。 它會顯示商務用 Skype 帳戶中每位使用者之通話和會議的詳細資訊。  使用呼叫分析，您可以將許可權指派給服務台操作員，這樣就能在未存取商務用 Skype 系統管理中心的其餘部分的情況下監視通話。

- 通話品質儀表板側重于整個組織的網路效能和問題。 商務用 Skype 系統管理員和網路工程師使用此工具來疑難排解及優化網路效能。

如需詳細資訊，請參閱[通話分析和通話品質儀表板圖表（含監控伺服器詳細資料）。](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

當然，您可能想要在內部部署中保留一些通話品質資料。 例如，如果您要使用協力廠商的解決方案與自訂的報表和工作流程，便會發生這種情況。  呼叫資料連線器可讓您設定將資料傳送到線上服務，同時在內部部署伺服器上保留資料的複本，如下圖所示：

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server。  如需部署商務用 Skype Server 和支援的拓撲的詳細資訊，請參閱[拓撲基礎](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。 若要設定呼叫資料連線器，您必須：

- 啟用混合連接。 如果您已部署商務用 Skype Server 而且想要啟用呼叫資料連線器，則必須確定您的內部部署與線上環境之間已設定混合式連線能力。 這有時稱為分割網域設定。

   如需詳細資訊，請參閱[Plan 商務用 Skype Server 和 Microsoft 365 之間的混合](plan-hybrid-connectivity.md)式連線，或 Office 365 和[設定商務用 Skype Server 及 Microsoft 365 或 Office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 驗證您的 Microsoft 365 或 Office 365 組織，並確認您已啟用下列角色：

  - 商務用 Skype Server管理員
  - Microsoft 365 或 Office 365 全域管理員

- 如果您還沒有這麼做，請依[開啟和使用通話品質儀表板中的 Microsoft Teams 和商務用 Skype 線上](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述，開啟通話品質儀表板。

- 使用本機 LCSCdr 和 QoEMetrics 資料庫，啟用監視的前端集區。 若未這麼做，則通話資料連線器沒有可使用的計量資料。

> [!IMPORTANT]
> 如果前端集區上未啟用監視，則通話資料連線器將無法運作。

- 正確設定 [伺服器對伺服器驗證](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>內部部署和線上通話品質儀表板的比較 (CQD) 報告

| 功能報告 | 商務用 Skype Online | 商務用 Skype Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 應用程式共用度量 |是 | 有限 |
| 客戶組建資訊| 是 | 是 |
| 深入分析 | 是 | 否 |
| 媒體可靠性度量 | 是 | 有限 |
| 現成的報表 | 是 | 是 |
| 總覽報表 | 是 | 否 |
| 每個使用者報告 | 是 | 是 |
| 報表集合自訂 <br>  (新增、刪除、修改報告)  | 是 | 是 |
| 以影片為基礎的螢幕共用計量 | 是 | 否 |
| 以程式設計方式存取的資料 APIs <br> 若要 CQD | 否 | 是 |
||||