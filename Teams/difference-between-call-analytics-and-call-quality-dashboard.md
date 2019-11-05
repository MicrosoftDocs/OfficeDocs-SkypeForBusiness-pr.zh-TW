---
title: 通話分析和通話品質儀表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 瞭解 [通話分析] 和 [通話品質儀表板]，以及何時使用它們監視及排除通話品質問題。
ms.openlocfilehash: 70efd7f17189d9aac2236383a07cfc5fc0a37096
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972464"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>通話分析和通話品質儀表板

Microsoft 團隊和商務用 Skype 提供兩種監視及疑難排解通話品質問題的方法： [通話分析] 和 [通話品質儀表板] （CQD）。 本文將說明這兩者，並告訴您何時使用每一個專案。

呼叫分析與 CQD 會並存執行，而且可以獨立地或一起使用。 例如，假設通訊支援專家認為他們需要進一步協助疑難排解通話問題。 通訊支援專家將呼叫傳遞給通訊支援工程師，使用者可以存取呼叫分析中的其他資訊，而不是通訊支援專家。 接著，通訊支援工程師可以提醒網路工程師發生問題。 網路工程師可以檢查 CQD，以查看總體網站相關問題是否可能是引起呼叫問題的問題。

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>什麼是呼叫分析，何時應該使用它？

**[通話分析] 現已提供給[Microsoft [團隊管理中心](https://admin.teams.microsoft.com)]。** 若要查看使用者的所有呼叫資訊和資料，請使用使用者設定檔頁面上的 [**通話記錄**] 索引標籤。 若要查看索引標籤，請從 [儀表板] 搜尋使用者，或從左側導覽列的 [**使用者**] 索引標籤尋找使用者。

[通話分析] 會顯示與 Microsoft 團隊或商務用 Skype 租使用者帳戶中每位使用者的通話與會議相關的裝置、網路及連線能力的詳細資訊。 為什麼此使用者的通話不佳？ 使用呼叫分析，Office 365 系統管理員或訓練有素的支援者代理程式可以調查裝置、網路、連線，以及在 Microsoft 團隊與商務用 Skype 中呼叫品質和連線問題的通話相關的其他因素。

若要在 Microsoft 團隊系統管理中心查看使用者的這項資訊，請按一下 [使用者詳細資料] 頁面中該使用者的 [**通話記錄**] 索引標籤，即可查看該使用者在過去30天內的所有通話與會議。

![所有分析使用者資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要取得特定會話的其他相關資訊，包括詳細的媒體和網路統計資料，請按一下某個會話查看詳細資料。

![呼叫分析使用者會話資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

如果您希望非系統管理員（例如外部廠商提供的支援人員）使用呼叫分析，您可以指派許可權，讓他們可以使用呼叫分析，但他們無法存取 Microsoft 團隊系統管理中心的其他部分：
  
- **提供通訊支援專家許可權的支援人員**：代理程式會在通話分析中看到一組有限的資料和個人辨識資訊（PII）。 他們可以對通話進行疑難排解，但他們會將會議問題提升至通訊支援工程師。
- **含通訊支援工程師許可權的支援人員代理**：代理程式會查看通話分析中所有可用的資料，並同時為通話與會議進行疑難排解。 他們擁有通話記錄及客戶資訊的完整存取權。

> [!NOTE]
> 通訊支援專家角色相當於預覽入口網站中的第1層支援角色，且通訊支援工程師角色相當於預覽入口網站中的第2層支援角色。

如需溝通支援專家和通訊支援工程師角色的詳細資訊，請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。

> [!IMPORTANT]
> Microsoft 團隊系統管理中心提供服務台代理許可權和網路拓撲上傳。 溝通支援專家和溝通支援工程師可以使用此入口網站存取通話分析和通話品質儀表板。

如需通話分析的詳細資料，請參閱[設定商務用 Skype 通話分析](set-up-call-analytics.md)。 如需説明台代理程式如何使用呼叫分析的詳細資訊，請參閱[使用通話分析來診斷不佳通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>什麼是通話品質儀表板，我該如何使用？
  
[通話分析] 的設計目的是協助系統管理員和技術支援人員*針對特定通話*的通話品質問題進行疑難排解。 通話品質儀表板（CQD）的設計目的是協助團隊管理員、商務用 Skype 系統管理員和網路工程師*優化網路*。 CQD 會將焦點從特定的使用者轉移，而不是查看整個團隊或商務用 Skype 組織的匯總資訊。 如需詳細資訊，請參閱[適用于團隊和商務用 Skype Online 的通話品質儀表板功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。
  
假設使用者的通話品質不佳，是因為網路問題也會影響許多其他使用者。 在 CQD 中看不到個別通話體驗，但會捕獲使用 Microsoft 團隊或商務用 Skype 所做的整體品質。 使用 CQD 時，整個模式可能會變得很明顯，因此網路工程師可以進行通話品質的及時評估。 CQD 提供通話品質度量的報告，可讓您深入瞭解整個通話品質、伺服器用戶端資料流程、用戶端用戶端資料流程，以及語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD 的位置-改良的報表會在使用者的組建中匯總通話品質與可靠性。 您可以評估資料來判斷問題是獨立于單一使用者，還是會影響較大的使用者區段。

![[通話品質儀表板] 的位置改良報告的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> 若要在 CQD 中啟用組建或端點專用的視圖，系統管理員必須在 CQD 的租使用者資料上傳頁面上[傳建築物或端點資訊](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。

如果您希望非系統管理員的使用者（例如支援人員）使用 [通話品質儀表板]，您可以為這些使用者指派下列其中一項角色，這些角色也具有存取通話品質儀表板所需的許可權：

- 全域系統管理員
- 全域閱讀程式
- 商務用 Skype 系統管理員
- Teams 服務管理員
- Teams 通訊系統管理員
- Teams 通訊支援工程師
- 團隊溝通支援專家
- 報表閱讀程式

> [!NOTE]
> 團隊通訊支援工程師、團隊溝通支援專家及報告閱讀者角色無法在 CQD 的租使用者上修改檔案，也無法在租使用者啟用 CQD。

如需有關這些角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。

如需有關 CQD 的詳細資訊，請參閱[開啟與使用 Microsoft 團隊和商務用 Skype online 的通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)，以及[Microsoft 團隊和商務用 Skype Online 的通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。
  
## <a name="related-topics"></a>相關主題

[影片：通話品質概覽](https://aka.ms/teams-quality)

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)
