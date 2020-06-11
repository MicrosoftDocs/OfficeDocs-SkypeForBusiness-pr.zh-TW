---
title: 在 Microsoft Teams 中設定即時活動
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 在 Teams 中設定即時活動，包括設定您的網路、指派授權、啟用即時活動功能和排程，以及視訊發佈解決方案。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2e865fe2285abb9cd515d1efe769f18cb5735ff2
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689669"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中設定即時活動

設定即時活動時，您必須採取幾個步驟。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>步驟 1：在 Teams 中針對即時活動設定您的網路

在 Teams 中產生的即時活動，需要您[針對 Teams 準備組織的網路](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>步驟 2：取得和指派授權

確保您擁有[可建立及排程即時活動的人員](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events)和[可監視即時活動的人員](plan-for-teams-live-events.md#who-can-watch-live-events)的正確授權指派。

## <a name="step-3-set-up-live-events-policies"></a>步驟 3：設定即時活動原則

即時活動原則是用來控制組織中的哪些人員可以舉辦即時活動，以及在他們所建立活動中可用的功能。 您可以使用預設原則或建立一或多個自訂即時活動原則。 建立自訂原則之後，請將它指派給組織中一個或一組使用者。

> [!NOTE]
> 除非您建立並指派自訂原則，否則組織中的使用者將會取得全域原則。 依預設在全域原則中，會為 Teams 使用者啟用即時活動排程，關閉即時的輔助字幕和翻譯字幕 (謄寫)，組織中的每個人都可以加入即時活動，且錄製設定設為永遠錄製。

### <a name="create-or-edit-a-live-events-policy"></a>建立或編輯即時活動原則

<a name="bkcreatepolicy"> </a>

**![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png)使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 **[會議]**  >  **[即時活動原則]**。
2. 執行下列其中一項動作：

- 如果要編輯現有的預設原則，請選擇 **[全域 (全組織預設值)]**。
- 如果要建立新的自訂原則，請選擇 **[新增原則]**。
- 如果要編輯自訂原則，請選取該原則，然後選擇 **[編輯]**。

    以下是您可以根據組織需求變更的設定。

    ![即時活動原則設定的螢幕擷取畫面](../media/teams-live-events-policies.png "Microsoft Teams 系統管理中心即時活動原則設定的螢幕擷取畫面")

|設定  |描述  |
|---------|---------|
|**標題**     |這是顯示在即時活動原則頁面上的原則標題。 不能超過 64 個字元或含有任何特殊字元。          |
|**描述**    |使用此項目來新增原則的易記描述。         |
|**允許排程**     |開啟此功能可讓組織中的使用者在 Teams 中建立及排程即時活動。 請注意，如果您希望使用者排程由外部應用程式或裝置產生的即時活動，您必須執行其他步驟。 若要深入了解，請參閱[讓使用者能夠排程使用外部應用程式或裝置所產生的活動](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。     |
|**允許出席者的謄寫** |此設定只能套用至在 Teams 中產生的活動。 開啟此功能可讓即時活動出席者在活動期間查看即時輔助字幕和翻譯字幕。         |
|**誰可加入已排程的即時活動**    |選擇下列其中一項。<br><br>**每個人**：使用者可以建立每個人 (包括組織外部人員) 都可以出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用**公用**權限類型。<br> **組織中的每個人**：使用者可以建立組織中的人員 (包括新增至您組織的[來賓使用者](../add-guests.md)) 可以出席的即時活動。 使用者無法建立由匿名使用者出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用**全組織**權限類型。<br> **特定使用者或群組**：使用者可以建立只有組織中特定使用者或群組可以出席的即時活動。 使用者無法建立由組織中的每個人或匿名使用者出席的即時活動。 當使用者排程即時活動時，此設定會在 Teams 中啟用**人員及群組**權限類型。       |
|**錄製設定**  <br>     | 此設定只能套用至在 Teams 中產生的活動。 選擇下列其中一項。 <br><br> **永遠錄製**：永遠會錄製使用者建立的即時活動。 活動結束之後，活動團隊成員可以下載錄製，而出席者可以觀看活動。 <br> **永不錄製**：永不錄製使用者建立的即時活動。 <br>**召集人可否錄製**：使用者可以決定是否要錄製即時活動。 如果有錄製，活動結束之後，活動團隊成員可以下載錄製，而出席者可以觀看活動。      

您也可以使用 Windows PowerShell 執行此動作。 如需詳細資訊，請參閱[使用 PowerShell 在 Teams 中設定即時活動原則](set-teams-live-events-policies-using-powershell.md)。 

### <a name="assign-a-live-events-policy-to-users"></a>將即時活動原則指派給使用者 

如果您建立了自訂即時活動原則，請將它指派給使用者，讓原則成為使用中。 

![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側瀏覽中，移至 **[使用者]**，然後選取該使用者。
2. 在 **[指派的原則]** 旁，選擇 **[編輯]**。 
3. 選取您要指派的即時活動原則，然後選擇 **[儲存]**。 

您也可以將即時活動原則指派給一或多個使用者，如下所示：

![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 移至 **[會議]**  >  **[即時活動原則]**。
2. 按一下原則名稱的左側來選取原則。
3. 選取 **[管理使用者]**。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者時，選取 **[儲存]**。
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>讓使用者能夠排程使用外部應用程式或裝置所產生的活動

若要讓使用者能夠排程使用外部應用程式或裝置所產生的活動，您也必須執行下列動作：

1. 為組織中的使用者啟用 Microsoft Stream。 資料流程是以合格的 Microsoft 365 或 Office 365 訂閱或獨立服務的形式提供。 Stream 未包含在商務基本版或商務進階版方案中。 如需詳細資訊，請參閱 [Stream 授權概觀](https://docs.microsoft.com/stream/license-overview)。

      進一步瞭解您可以如何[指派授權給使用者](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，讓使用者可以存取資料流程。 確保未針對使用者封鎖 Stream，如[本文章](https://docs.microsoft.com/stream/disable-user-organization)所定義。

2. 確保使用者擁有在 Stream 中建立即時活動的權限。 根據預設，系統管理員可以使用外部應用程式或裝置來建立活動。 Stream 系統管理員可以在 Stream 中[為額外的使用者啟用即時活動建立](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

3. 確保即時活動召集人已同意 Stream 系統管理員設定的公司原則。如果 Stream 系統管理員已[設定公司指導方針原則](https://docs.microsoft.com/stream/company-policy-and-consent)，並要求員工在儲存內容之前先接受此原則，則使用者必須先接受，才能在 Teams 中建立即時活動 (使用外部應用程式或裝置)。 在組織中推出即時事件功能之前，請確認將建立這些即時活動的使用者已同意該原則。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>步驟 4：在 Teams 中針對即時活動設定視訊發佈解決方案
播放即時活動視訊會使用的自適性串流 (ABR)，但它是單點廣播串流，表示每個檢視器都會從網際網路取得自己的視訊。 針對向外傳送給組織中大多數的即時活動或視訊，檢視器可能會明顯耗用大量網際網路頻寬。 針對想要減少即時活動的這項網際網路流量的組織，即時活動解決方案已與 Microsoft 信任的視訊傳遞合作夥伴整合，其提供軟體定義的網路 (SDN) 或企業內容傳遞網路 (eCDN)。 這些 SDN/eCDN 平台能讓組織將網路頻寬最佳化，而不需犧牲使用者的瀏覽體驗。 我們的合作夥伴可協助您在整個商業網路中更具伸縮性且有效率的視訊發佈。

**在 Teams 以外購買和設定您的解決方案** 運用 Microsoft 信任的視訊傳遞合作夥伴，獲得擴大視訊傳遞的專家協助。 在您能夠讓視訊傳遞提供者與 Teams 搭配使用之前，您必須向外部購買並設定 SDN/eCDN 解決方案，並與 Teams 區隔。

下列 SDN/eCDN 解決方案已預先整合，且可設定以搭配 Stream 使用。

- **Hive Streaming** 為即時且隨選的企業視訊發佈提供簡單且功能強大的解決方案。 Hive 是一項軟體型解決方案，不需要額外的硬體或頻寬，並可提供一個安全的方式讓您啟用數千個同時使用的視訊檢視器，而不會影響您的網路。 針對想要在購買 SDN/eCDN 解決方案之前了解視訊對其網路的影響的客戶，Hive Streaming 也為 Microsoft 客戶提供瀏覽器型分析解決方案。 [深入了解](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective** 是一項雲端式智慧型對等分送平台，其會運用您現有的網路基礎結構，以更多種方式 (即時串流視訊、隨選視訊、軟體更新、安全性修補程式等)、更快速可靠地傳遞內容，並使用更少的頻寬。 我們的安全平台受到世界上最大的金融機構信任，且不需要額外的硬體，且設定和維護極為簡單。 [深入了解](https://kollective.com/microsoft-pilot/)。
 
- **Ramp OmniCache** 提供下一代的網路發佈方式，並確保在全球 WAN 上順暢地傳送視訊內容，協助活動製作人將網路頻寬最佳化，並支援成功的即時活動廣播和隨選串流處理。 針對在 Teams 中所產生即時活動的 Ramp OmniCache 支援近期推出。 [深入了解](http://www.ramp.com)。 
 
> [!NOTE] 
> 您選擇的 SDN 或 eCDN 解決方案受限於選取的**協力廠商提供者的服務條款和隱私權原則**，其將控管您對提供者解決方案的使用方式。 您對提供者解決方案的使用方式將不受限於 Microsoft 大量授權條款或線上服務條款。 如果您不同意**協力廠商提供者的條款**，則不要在 Teams 中啟用該解決方案。 

設定了 SDN 或 eCDN 解決方案之後，您就可以開始為 Teams 中的即時活動設定提供者。 

## <a name="next-steps"></a>後續步驟
前往[在 Teams 中設定即時活動設定](configure-teams-live-events.md)。

### <a name="related-topics"></a>相關主題
- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的方案](plan-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
