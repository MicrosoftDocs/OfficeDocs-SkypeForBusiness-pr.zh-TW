---
title: 為 Microsoft 團隊準備貴組織的網路
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: 瞭解如何準備及管理您的 Microsoft 團隊網路。 資訊包括網路需求、頻寬需求, 以及其他考慮。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184236"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>為 Microsoft 團隊準備貴組織的網路


團隊結合三種形式的流量:

-   Office 365 線上環境與團隊用戶端之間的資料流量 ([通知]、[目前狀態]、[聊天]、檔案上傳和下載、OneNote 同步處理)。

-   對等即時通訊流量 (音訊、影片、桌面共用)。

-   會議即時通訊流量 (音訊、影片、桌面共用)。

這會影響兩個層次上的網路: 流量會直接在 Microsoft 團隊用戶端與對等案例之間流動, 且流量將在 Office 365 環境與 Microsoft 團隊用戶端之間流動, 以進行會議案例。 為確保最佳流量流程, 必須允許流量在內部網路區段 (例如, 在 WAN 之間的網站之間) 以及網路網站與 Office 365 之間流動。 無法開啟正確的埠或主動封鎖特定的埠, 可能會造成降級的體驗。

> [!NOTE]
> IOS 和 Android 行動裝置支援會議。 

若要在 Microsoft 團隊中取得即時媒體的最佳體驗, 您的網路必須符合 Office 365 的網路需求。 如需詳細資訊, 請參閱[商務用 Skype Online 的媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

針對這兩個定義網段 (用戶端到 microsoft edge, 以及客戶邊緣至 Microsoft Edge), 請考慮下列建議。


|值  |用戶端到 Microsoft Edge  |客戶邊緣到 Microsoft Edge  |
|:--- |:--- |:--- |
|**延遲 (一種方式)**\*  |< 50ms          |< 30ms         |
|**延遲 (RTT 或往返時間)**\* |< 100ms   |< 60ms |
|**突發資料包遺失**    |在任何200ms 間隔期間, <10%         |在任何200ms 間隔期間, <1%         |
|**資料包遺失**     |在任何15s 間隔期間, <1%          |在任何15s 間隔期間, <0.1%         |
|**資料包內部到達抖動**    |在任何15s 間隔期間 <30ms         |在任何15s 間隔期間 <15ms         |
|**資料包重新排序**    |<0.05% 的順序外資料包         |<0.01% 的順序外資料包         |

\*延遲量度目標假設您的公司網站或網站, 而且 Microsoft 邊緣位於同一個洲上。

您的 Microsoft 網路 edge 的公司網站連線包含第一個躍點網路存取, 這可以是 WiFi 或其他無線技術。

網路效能目標會採用適當的頻寬與/或[QoS 規劃](QoS-in-Teams.md)。 換句話說, 當網路連線達到峰值負載時, 這些需求會直接套用至團隊即時媒體流量。

若要測試兩個網路區段, 您可以使用 [[網路評](https://go.microsoft.com/fwlink/?linkid=855799)量] 工具。 此工具可以直接在用戶端電腦上和連線至客戶網路邊緣的電腦上部署。 此工具組含有限的檔, 但在此可找到有關該工具用法的深入說明文件:[網路就緒評估](https://go.microsoft.com/fwlink/?linkid=855800)。 您可以透過執行此網路準備情況評估來驗證您的網路是否已準備好執行即時媒體應用程式, 例如 Microsoft 團隊。

> [!NOTE]
> 這是相同的網路準備情況評估, 建議針對想要成功部署商務用 Skype 的客戶執行。


## <a name="bandwidth-requirements"></a>頻寬需求
無論您的網路狀況為何, Microsoft 團隊都能提供最佳的音訊、影片和內容共用體驗。 有了可變的編解碼器, 就可以在有限的頻寬環境中協商媒體, 且影響極小。 但在頻寬不是一個重要問題時, 體驗可以針對品質進行優化, 包括最高解析度 (含1080p 解析度), 最多30fps 影片和15fps 內容, 以及高保真音訊。

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>其他網路考慮
---------------

#### <a name="external-name-resolution"></a>外部名稱解析

請確定執行團隊用戶端的所有用戶端電腦都可以解析外部 DNS 查詢, 以探索 Office 365 提供的服務, 而且您的防火牆無法防止存取。 如需設定防火牆埠的相關資訊, 請移至[Office 365 url 與 IP 範圍](office-365-urls-ip-address-ranges.md)。

#### <a name="nat-pool-size"></a>NAT 池子大小

當多個使用者/裝置使用網路位址轉譯 (NAT) 或埠位址轉換 (PAT) 存取 Office 365 時, 您必須確保隱藏在每個公開路由的 IP 位址後面的裝置不會超過支援的號碼。

若要緩解此風險, 請確保已將充足的公用 IP 位址指派給 NAT 池, 以避免埠耗盡。 埠耗盡會導致內部使用者和裝置在連線至 Office 365 服務時面臨問題。 如需詳細資訊, 請參閱[Office 365 的 NAT 支援](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**入侵偵測與防範指導方針**

如果您的環境針對外部連線安全層級部署了入侵偵測及/或防護系統 (IDS/IPS), 請確定任何具有目的地至 Office 365 Url 的流量都是白名單。

<a name="network-health-determination"></a>網路狀況判斷
-----------------

規劃您網路中的 Microsoft 團隊實施時, 您必須確保您具備所需的頻寬, 您可以存取所有必要的 IP 位址、已開啟正確的埠, 以及滿足即時媒體的效能需求.

如果您知道您不符合這些準則, 您的使用者將無法在通話和會議期間因品質差而從小組獲得最佳體驗。

如果您不符合這些準則, 這是考慮暫停專案以確保您在繼續之前符合準則的時間。


|  |  |  |
|---------|---------|---------|
|![代表決策點的圖示](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |決策點         |您是否已評估您的網路功能以支援即時媒體？<br></br>如果您的網路未正確評定, 或是您知道它不支援即時媒體, 您會停用影片和螢幕共用功能來減少網路影響與不佳的團隊體驗嗎？         |
|![代表後續步驟的圖示](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |後續步驟         |網路品質未知: 執行網路就緒評估, 以判斷您的網路是否已準備好使用即時媒體。<br></br>網路品質差: 執行網路修正步驟, 為高品質即時媒體提供適當的環境。<br></br>網路滿意: 確保所有 IP 位址和埠都能正確存取。           |

## <a name="related-topics"></a>相關主題

[影片: 網路規劃](https://aka.ms/teams-networking)
