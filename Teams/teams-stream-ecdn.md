---
title: 在 Microsoft Teams 中縮放視訊傳遞
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文將討論 Microsoft Teams 串流事件 (eCDN) 規模視訊傳遞和企業內容傳遞網路。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767925"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>在 Microsoft Teams 中使用 eCDN 來縮放視訊傳遞和監視網路流量

播放來自 Microsoft Teams 的影片和「外部應用程式或裝置」即時活動， (之前稱為「外部編碼器」生產) 使用調適性位元速率串流 (ABR) 以 Unicast 串流的形式傳遞。 這表示每個檢視器都會從網際網路取得自己的視訊串流。 針對傳送給組織中很大一部分的即時活動或影片，檢視者可能會使用大量的網路和網際網路頻寬。

組織可能會想要瞭解並減少即時活動和熱門影片的網路流量。 若是如此，Teams 可與提供企業內容傳遞網路 (eCDN) 解決方案的受信任 Microsoft 合作夥伴整合，這些解決方案包括自我管理的傳遞技術、即時監控和深度網路分析。 這些 eCDN 平臺可讓組織在商業網路上監視、縮放視訊串流，並優化其散佈 (，有時還可) 其他內容類型。

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>在 Teams 外部取得並設定您的 eCDN 解決方案

透過與受信任的 Microsoft eCDN 合作夥伴合作，取得專家協助監控和縮放視訊傳遞。

您必須先在 Teams 外部購買並設定 eCDN 解決方案，才能啟用與 Teams 搭配使用的 eCDN 解決方案。 為了確保解決方案符合您的需求，部分合作夥伴會免費試用其內容傳遞和網路分析技術。

數個 eCDN 解決方案都已預先整合，且可以啟用以搭配 Teams 使用。 請參閱下方提供者的資訊。

### <a name="hive-streaming"></a>Hive 串流

**Hive 串流視訊體驗平臺** 由三個核心產品組成：

- **Hive Video Optimization** 是以專利軟體專用零設定演算法為基礎。 優化會自動最大化整個組織的即時和隨選影片 (VOD) 。
- **Hive Video Analytics** 可協助客戶瞭解即時活動的趨勢和隨選視訊效能，以改善檢視器在一段時間內的參與度。 隨著參與度的改善，全公司的視訊採用也一樣。
- **Hive Video Operations** 提供強大的功能，旨在在即時視訊活動之前和期間主動保護串流視訊成功。 操作工具可讓您的視訊串流和 UC 小組在問題發生之前找到並修正問題。

從規劃到執行和分析，所有這些功能都可建立完整範圍的視訊體驗。 最大化串流視訊通訊的體驗對於員工參與公司任務和對齊至關重要。 若要深入瞭解，請查看 [此連結](https://www.hivestreaming.com/partners/microsoft)。

### <a name="kollective"></a>Kollective

**Kollective 技術** 是雲端式內容發佈平臺，可利用智慧型對等功能，以僅頻寬的 1% 提供 100% 的視訊品質和 100% 的參與度。 Kollective 與 Teams Live Events 的整合可讓全球分散的員工輕鬆使用視訊、改善員工溝通、促進整體參與，以及增加訓練和保留機會。

**Kollective IQ** 是一個精密、方便使用者的分析平臺，可Microsoft Stream。 透過可自訂的報告、視覺效果和儀表板，您可以在複雜的全球商業網路上輕鬆量化並摘要使用者體驗和參與度。 通訊管理員和網路系統管理員可以監看即時事件和網路活動，以便快速解決瓶頸問題，確保網路效能達到頂峰。

若要深入瞭解這些選項，請查看 [此連結](https://kollective.com/microsoft-live-events/)。

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** 解決全手會議等大型公司虛擬活動期間發生的網路壅塞問題。 Microsoft eCDN 透過 LAN 建立網格網路，可將負載減少 95%，並消除網路問題。 Microsoft eCDN 是第一個使用 WebRTC 做為基礎的 eCDN，這表示不需要軟體或硬體安裝。 幸運 500 客戶可減輕網路問題，並信任 Peer5 舉辦他們最大的公司活動。

- Microsoft eCDN 的零設定網路設定可確保遠端工作者和/或大量視訊流量不會使您的網路疲勞，也不會有義務投資在成本高額的基礎結構上。 它包括自動網站偵測、自動 VPN 偵測，以及自動 NAT/防火牆穿越。 若要深入瞭解 [，請參閱此連結](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant)。
- 使用 Microsoft eCDN 進行無訊息測試可讓 IT 系統管理員在其公司網路上模擬大型即時活動，允許在發生實際事件之前進行徹底且無干擾的測試和疑難排解。 若要深入瞭解 [，請參閱此連結](/ecdn/how-to/perform-silent-test)。
- Microsoft eCDN 領先業界的分析提供細部分析，並讓系統管理員快速找到任何串流問題的根本原因。 您的工具組包括傳遞和 UX 指派、進階向下切入、每個使用者分析，以及後端 API。 若要深入瞭解 [，請參閱此連結](/ecdn/technical-documentation/analytics)。

### <a name="ramp"></a>Ramp

當依需求串流即時活動和視訊時，**Ramp eCDN** 可將網路頻寬耗用量減少 90% 以上 (VOD) 。 使用 Ramp 混合並比對任何 eCDN 技術組合，包括多重廣播、快取和對等網路。 透過集中式管理、監控和深入分析，您可以對網路效能取得可見度和控制，以建立最高品質的檢視器體驗。

- **Ramp Multicast+** 是串流即時視訊最有效率的方式。 使用多場廣播通訊協定時，無論您有 100、10，000 或 100，000 位檢視者，您都只會使用一個檢視器所需的頻寬。 若要深入瞭解 [，請參閱此連結](https://www.rampecdn.com/altitudecdn/multicast/)。
- **Ramp OmniCache™** 是視訊專屬的快取軟體，使用本機快取為鄰近觀眾提供即時和 VOD 視訊，大幅減少跨越網際網路連線和 WAN 連結的視訊串流數量。 若要深入瞭解 [，請參閱此連結](https://www.rampecdn.com/altitudecdn/video-cache/)。
- **對等 (P2P)** 可讓您在基礎結構受限的位置優化頻寬。 P2P 會建立一個可觀賞相同內容之用戶端裝置的對等網路，將視訊串流從一個檢視裝置轉散發到另一個裝置。 若要深入瞭解 [，請參閱此連結](https://www.rampecdn.com/altitudecdn/p2p/)。

### <a name="riverbed"></a>Riverbed

**Riverbed** 是網路優化的業界標準，已將其加速解決方案延伸至 Teams。 Microsoft 365 客戶可以放心地加快 Microsoft 365 流量，包括 Teams，以及豐富的其他前導企業 SaaS 服務，以隨時隨地提高員工生產力。 Teams 加速可以透過隨附于 Riverbed 世界級支援與持續投資的所有保證輕鬆設定來啟用。 若要深入瞭解 [，請參閱此連結](https://www.riverbed.com/office365)。

> [!NOTE]
> 您選擇的 eCDN 解決方案受選合作夥伴 eCDN 提供者的服務條款和隱私權原則所規範，這將會規範您使用 eCDN 提供者的解決方案。 您使用 eCDN 提供者的解決方案將不受 Microsoft 大量授權條款或線上服務條款的規範。 如果您不同意協力廠商提供者的條款，請不要在 Microsoft Teams 中啟用 eCDN 解決方案。

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>為您的 eCDN 解決方案設定 Stream 編碼器類型事件

購買並設定您的 eCDN 解決方案之後，您可以將它啟用以搭配Microsoft Stream使用，包括透過 Microsoft Teams 或 Yammer 建立的 Stream 編碼器即時活動。

1. 以 Microsoft 365 全域系統管理員或 Teams 系統管理員的身分開啟 Teams 系統管理中心，並流覽至 [即時活動設定](https://admin.teams.microsoft.com/broadcasts/settings) 頁面。
1. 將 **視訊發佈提供者** 切換為 [ **開啟]**。
1. 從影片 **發佈提供者** 下拉式清單中選擇 **eCDN/SDN 提供者**。
1. 填寫解決方案提供者指引的其他欄位 (並非所有解決方案提供者) 都會使用所有欄位。
1. 選取 [儲存 **]**。
1. 若要檢查您的設定是否正確，請選取 **[驗證設定]**。
    - 搜尋貴組織中的任何影片以進行驗證。
    - 如果您的 eCDN 提供者設定正確，您會在驗證設定工具上看到 **成功** 訊息。
    - 如果您未正確設定，您會看到 **失敗** 訊息。 複製事件訊息，與您的提供者共用以進行疑難排解。

在您為 eCDN 解決方案設定 Teams 之後，任何在 Teams 中播放的視訊或即時活動都會自動利用該解決方案。

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>透過 Teams 和 Yammer 為您的 eCDN 解決方案設定 Teams 生產類型事件

如果您打算透過 Teams 或 Yammer 建立 Teams 即時活動，您也必須將 [eCDN 提供者設定為與 Microsoft Teams 整合](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) 。

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>取得 eCDN 解決方案的視訊分析報告

如上所述，某些 eCDN 解決方案也提供分析報告，提供有關播放會話、檢視者及服務品質的更深入資訊。 如果您的提供者提供分析報告 URL 範本，以便在您于 Teams 系統管理中心設定提供者時進行設定，則視訊或事件的擁有者可以輕鬆取得特定視訊或事件的分析報告。

影片擁有者會在影片正下方看到 [分析] 索引標籤。 在此索引標籤上，會有一個連結供擁有者在 eCDN 提供者的系統中存取此特定影片的分析報告。

如果您是 Teams 系統管理員，您也可以提高查看 [分析] 索引標籤以及存取 eCDN 分析報告連結的許可權，即使您不是即時活動或影片的擁有者。

1. 身為 Teams 系統管理員，請移至視訊播放程式頁面。
1. 選 **取 [設定]**。
1. 選 **取 [以系統管理模式檢視]**。
1. 選取 [ **分析] 索引卷** 標。

## <a name="troubleshooting-issues"></a>疑難排解問題

請確定您的 eCDN 解決方案已在您的網路中正確設定，而且您已正確設定 Teams，讓提供者依照其指示和特定組態字串來啟用。 如果您仍有問題，下列部分資訊可能會有説明。

### <a name="verify-setup-tool"></a>驗證設定工具

如果您的 eCDN 解決方案有問題，您可以隨時返回並執行 **[驗證設定]** 工具。 針對您的測試視訊顯示的 eCDN 提供者事件訊息，可以提供您和您的 eCDN 提供者更多無法運作的資訊。

- 移至 **[設定**  >  **管理員設定**  >  **eCDN 提供者**  >  **驗證設定**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>透過 URL 查詢字串停用特定會話的 eCDN

若要判斷您看到的是 eCDN 解決方案或 Teams 的問題，您可以透過查詢字串輕鬆停用特定播放會話的 eCDN 解決方案。

- 如果您的播放 URL 已經有問 **號？，** 請在其中新增 **&停用SDN=true**。
- 如果您的播放 URL 沒有問 **號？，** 請在其中新增 **？disableSDN=true**。

### <a name="view-ecdn-info-in-browser-console"></a>在瀏覽器主機上檢視 eCDN 資訊

如果您的 eCDN 解決方案提供者支援，他們可能會在初始化期間透過解決方案列印偵錯資訊。 這項額外資訊在判斷發生錯誤時可能會很有説明。 您可以透過查詢字串啟用額外的主機偵錯訊息。

- 如果您的播放 URL 已經有問 **號？，** 請在其中新增 **&為SDNDebug=true**。
- 如果您的播放 URL 沒有問 **號？，** 請在其中新增 **？isSDNDebug=true**。

當瀏覽器處於使用中狀態時，請選取鍵盤上的 **F12** ，然後切換到 [ **主機** ] 索引標籤，查看載入頁面時列印的所有資訊，並在播放 URL 上設定 isSDNDebug=true 查詢字串。
