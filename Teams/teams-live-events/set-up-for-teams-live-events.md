---
title: 在 Microsoft Teams 中設定即時活動
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: 在 Teams 中設定即時活動，包括設定您的網路、指派授權、啟用即時活動功能和排程，以及視訊發佈解決方案。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cf3d364ce01ea80892dc929102c96a7fab5a74bc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767584"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中設定即時活動

設定即時活動時，您必須採取幾個步驟。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>步驟 1：在 Teams 中針對即時活動設定您的網路

在 Teams 中產生的即時活動，需要您[針對 Teams 準備組織的網路](../prepare-network.md)。  

## <a name="step-2-get-and-assign-licenses"></a>步驟 2：取得和指派授權

確保您擁有[可建立及排程即時活動的人員](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events)和[可監視即時活動的人員](plan-for-teams-live-events.md#who-can-watch-live-events)的正確授權指派。

## <a name="step-3-set-up-live-events-policies"></a>步驟 3：設定即時活動原則

即時活動原則是用來控制組織中的哪些人員可以舉辦即時活動，以及在他們所建立活動中可用的功能。 您可以使用預設原則或建立一或多個自訂即時活動原則。 建立自訂原則之後，請將它指派給組織中一個或一組使用者。

> [!NOTE]
> 除非您建立並指派自訂原則，否則貴組織中的使用者會獲得全域 (組織的預設) 原則。 依預設在全域原則中，會為 Teams 使用者啟用即時活動排程，關閉即時的輔助字幕和翻譯字幕 (謄寫)，組織中的每個人都可以加入即時活動，且錄製設定設為永遠錄製。

### <a name="create-or-edit-a-live-events-policy"></a>建立或編輯即時活動原則

<a name="bkcreatepolicy"> </a>

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **[會議**  >  **即時活動原則**  >  **管理原則]** 索引標籤。
2. 執行下列其中一個選項：

    - 如果要編輯現有的預設原則，請選擇 **[全域 (全組織預設值)]**。
    - 如果您想要建立新的自訂原則，請選擇 **[+新增]**。
    - 如果要編輯自訂原則，請選取該原則，然後選擇 **[編輯]**。

    以下是您可以根據組織需求變更的設定。

    ![即時活動原則設定的螢幕擷取畫面。](../media/teams-live-events-policies-new.png "Microsoft Teams 系統管理中心即時活動原則設定的螢幕擷取畫面")

|設定  |描述  |
|---------|---------|
|**標題**     |這是顯示在即時活動原則頁面上的原則標題。 不能超過 64 個字元或含有任何特殊字元。          |
|**描述**    |使用此項目來新增原則的易記描述。         |
|**即時活動排程**     |開啟此功能可讓組織中的使用者在 Teams 中建立及排程即時活動。     |
|**出席者的轉譯** |此設定只能套用至在 Teams 中產生的活動。 開啟此功能可讓即時活動出席者在活動期間查看即時輔助字幕和翻譯字幕。         |
|**誰可加入已排程的即時活動**    |選擇下列其中一項。<br><br>**每個人**：使用者可以建立每個人 (包括組織外部人員) 都可以出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用 **公用** 權限類型。<br> **組織中的每個人**：使用者可以建立組織中的人員 (包括新增至您組織的 [來賓使用者](../add-guests.md)) 可以出席的即時活動。 使用者無法建立由匿名使用者出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用 **全組織** 權限類型。<br> **特定使用者或群組**：使用者可以建立只有組織中特定使用者或群組可以出席的即時活動。 使用者無法建立由組織中的每個人或匿名使用者出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用 **人員及群組** 權限類型。       |
|**錄製設定**  <br>     | 此設定只能套用至在 Teams 中產生的活動。 選擇下列其中一項。 <br><br> **永遠錄製**：永遠會錄製使用者建立的即時活動。 活動結束之後，活動團隊成員可以下載錄製，而出席者可以觀看活動。 <br> **永不錄製**：永不錄製使用者建立的即時活動。 <br>**召集人可否錄製**：使用者可以決定是否要錄製即時活動。 如果有錄製，活動結束之後，活動團隊成員可以下載錄製，而出席者可以觀看活動。

您也可以使用 Windows PowerShell 執行此動作，而且目前 GCC High 和 DoD 客戶必須使用此方法。 如需詳細資訊，請參閱[使用 PowerShell 在 Teams 中設定即時活動原則](set-teams-live-events-policies-using-powershell.md)。

### <a name="assign-a-live-events-policy-to-users"></a>將即時活動原則指派給使用者

如果您建立了自訂即時活動原則，請將它指派給使用者，讓原則成為使用中。 <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>步驟 4：在 Teams 中針對即時活動設定視訊發佈解決方案

播放即時活動視訊會使用的自適性串流 (ABR)，但它是單點廣播串流，表示每個檢視器都會從網際網路取得自己的視訊。 針對向外傳送給組織中大多數的即時活動或視訊，檢視器可能會明顯耗用大量網際網路頻寬。 針對想要減少即時活動的網際網路流量的組織，Microsoft 提供第一方解決方案 [Microsoft eCDN](/ecdn) (企業內容傳遞網路) 。 即時活動解決方案也與 Microsoft 信任的影片傳遞合作夥伴整合，提供軟體定義的網路 (SDN) 或 eCDN。 這些 SDN/eCDN 平臺可讓組織優化網路頻寬，而不需要犧牲使用者檢視體驗。 這些解決方案可協助您在整個商業網路上進行更可縮放且更有效率的視訊發佈。

- **Microsoft eCDN** Microsoft eCDN 已整合至 Teams，並且與 Stream 和 Yammer 相容。 它在公司網路中採用對等技術，以從 WAN 連線卸載頻寬。

- **在 Teams 以外購買和設定您的解決方案** 運用 Microsoft 信任的視訊傳遞合作夥伴，獲得擴大視訊傳遞的專家協助。 

下列 SDN/eCDN 解決方案是預先整合的，可設定為搭配 Teams 串流使用：

- **Hive Streaming** 為即時且隨選的企業視訊發佈提供簡單且功能強大的解決方案。 Hive 是一項軟體型解決方案，不需要額外的硬體或頻寬，並可提供一個安全的方式讓您啟用數千個同時使用的視訊檢視器，而不會影響您的網路。 針對想要在購買 SDN/eCDN 解決方案之前了解視訊對其網路的影響的客戶，Hive Streaming 也為 Microsoft 客戶提供瀏覽器型分析解決方案。 [深入了解](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。

- **Kollective** 是雲端型智慧對等通訊平臺，可運用您現有的網路基礎結構，以多種形式提供內容， (即時串流視訊、隨選視訊、軟體更新、安全性修補程式，以及更快速、更可靠且頻寬較少的) 。 我們的安全平台受到世界上最大的金融機構信任，且不需要額外的硬體，且設定和維護極為簡單。 [深入了解](https://kollective.com/microsoft-pilot/)。

- **Ramp OmniCache** 提供下一代的網路發佈方式，並確保在全球 WAN 上順暢地傳送視訊內容，協助活動製作人將網路頻寬最佳化，並支援成功的即時活動廣播和隨選串流處理。 針對在 Teams 中所產生即時活動的 Ramp OmniCache 支援近期推出。 [深入了解](https://rampecdn.com)。

- **Riverbed** 是網路優化的業界標準，它正將加速解決方案延伸至 Microsoft Teams。 現在，Microsoft 365 客戶可以安心加速 365 流量，包括 Teams 及其他豐富的企業 SaaS 服務，以隨時隨地提高員工生產力。 Teams 加速可以透過隨附于 Riverbed 世界級支援與持續投資的所有保證輕鬆設定來啟用。

> [!NOTE]
> 如果您選擇協力廠商 SDN 或 eCDN 解決方案，則會受到所選 **協力廠商提供者的服務條款和隱私權原則** 所規範，這將會規範您對提供者解決方案的使用。 您對提供者解決方案的使用方式將不受限於 Microsoft 大量授權條款或線上服務條款。 如果您不同意 **協力廠商提供者的條款**，則不要在 Teams 中啟用該解決方案。

設定了 SDN 或 eCDN 解決方案之後，您就可以開始為 Teams 中的即時活動設定提供者。

## <a name="next-steps"></a>後續步驟

前往[在 Teams 中設定即時活動設定](configure-teams-live-events.md)。

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的規劃](plan-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
