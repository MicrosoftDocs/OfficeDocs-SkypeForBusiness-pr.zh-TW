---
title: 疑難排解 Microsoft Teams 中的即時串流
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
description: 本文將討論 Microsoft Teams 串流事件的疑難排解選項。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767933"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>疑難排解 Microsoft Teams 中的即時活動

> [!IMPORTANT]
> **中國**：位於中國的使用者將無法設定或參加 Teams 或 Yammer 即時活動，或是視需要檢視視訊，因為目前這些應用程式所仰賴的 Azure CDN 可能無法在中國存取。
>
> 身為系統管理員，您可能需要設定 VPN 來連接公司網路，這些應用程式才能順暢地運作。 完成之後，貴組織人員就可以排程並參加即時活動。

## <a name="before-a-live-event"></a>即時活動之前

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>確認您的網路可連線到所有事件

#### <a name="general-teams-endpoints"></a>一般 Teams 端點

Teams 需要連線到網際網路。 所有列在[Teams 端點Office 365端點上的端點](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)，都必須由貴組織網路中的 Teams 使用者連線。

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Teams 編碼器即時活動 - RMTP 內裝端點

若要從您的編碼器取得 Teams Encoder 即時活動的影片摘要，您需要在網路防火牆中開啟功能變數名稱和埠：

- 網域：*.rtmpingest.mcr.teams.microsoft.com
- 埠：RTMP/RTMPS) 1935/1936 (

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>確定您有足夠的上傳頻寬

透過 RTMP 製作或串流即時活動時，網際網路在推播即時串流的網站上傳頻寬可能不夠。 上傳頻寬過低可能會導致畫面掉落或即時視訊本身發生問題，因而導致檢視者播放問題。

確定您在推播即時串流的電腦和網路上傳速度高於您為即時串流設定的位元速率。 如果您從編碼器輸出 5 Mbps 串流，但上傳位元速率接近或低於該值，您可能會遇到無法以足夠快的速度上傳串流的問題。

如果您有上傳頻寬的問題，以下是一些您可以嘗試的動作：

1. 針對您推入串流的任何電腦使用有線乙太網路連線，以避免 WiFi 掉落。
1. 將即時摘要的編碼位元速率降低到最低於上傳速度的值。

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>為許多同時檢視者準備您的網路

在即時活動期間，許多人會加入觀看您的即時活動。 這可能會對您的網路和網際網路下載頻寬造成壓力。 您需要評估目前的網路基礎結構，並確保公司網路中的人員將擁有觀看即時活動所需的頻寬。 為了協助減少即時活動所需的網際網路流量，有兩個選項：

1. 在您的網路中設定現有的快取 Proxy，以從 Teams 快取視訊。
1. 使用協力廠商 eCDN 視訊傳遞解決方案來優化視訊流量。

### <a name="i-cant-create-a-live-event"></a>我無法建立即時活動

根據您用於即時活動的服務而定，使用者需要具備跨 Microsoft Teams 和 Yammer 的許可權，才能建立即時活動。

1. 檢查 Teams 系統管理員是否已啟用您建立即時活動。
1. 請洽詢您的系統管理員，確認您擁有允許建立即時活動的有效 Teams 授權。

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>確定檢視者有權觀看活動

Microsoft Teams 即時活動在活動本身 (召集人、製作人、簡報者、出席者) 具有一些不同的許可權角色。

如需詳細資訊，請參閱 [Microsoft Teams 事件群組角色](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) 。

## <a name="producing-a-live-event"></a>製作即時活動

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>我不知道如何設定編碼器

開始使用最簡單的方式是遵循 [Microsoft Teams 中使用編碼器進行即時串流](teams-encoder-setup.md) 一文中所述的指示。

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>我的編碼器未連線至伺服器摱取 URL

- 檢查 RTMP URL 是否在編碼器輸出時正確輸入。
- 檢查 RTMP 鍵是否在編碼器輸出時正確輸入。
- 檢查網際網路連線的狀態，以確保您的編碼器已正確連線和上線。
- 您可能有網路安全性或防火牆相關設定，可能會封鎖連線輸出。
- Teams 可能不支援您的編碼器。 請參閱在 [Microsoft Teams 中使用編碼器進行即時串流中的](teams-encoder-setup.md)測試編碼器清單。

### <a name="i-cant-get-rtmps-to-work"></a>我無法讓 RTMP 運作

- 有些編碼器可能支援 Teams 不支援的不同實作。 請參閱在 [Microsoft Teams 中使用編碼器進行即時串流](teams-encoder-setup.md)中使用 Teams 的測試編碼器清單。
- 並非所有的編碼器或版本都支援 RTMP。 請洽詢製造商或軟體建立者，以瞭解他們支援哪些專案。

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>我嘗試開始設定，但花費很長的時間

一般說來，您可能需要幾分鐘的時間才能開始進行設定，然後您才能開始推送編碼器。 如果服務忙碌中，可能需要較長的時間才能開始，因此建議您在排定的即時活動之前，先給自己足夠的時間來開始設定。

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>我嘗試開始設定，但發生太多事件

如果您在開始活動時收到一則訊息，指出已達到最多活動數目，請連絡 Teams 系統管理員，該管理員可以停止其他事件，為較高的優先順序活動騰出空間。

### <a name="i-cant-see-producer-view"></a>我看不到製作人檢視

1. 從您的編碼器開始串流之後，製作人預覽可能需要幾秒鐘才會出現。
1. 確定編碼器已連線至 Teams。
1. 有時候，重新整理 Teams 中的頁面會有所説明。 系統可能會詢問您是否要離開頁面;這不會影響您的即時活動。
1. 某些網路可能會封鎖內容的存取權。 確定您的網路安全性和防火牆設定允許 RTMP 通訊協定， [且必要網域](/microsoft-365/enterprise/urls-and-ip-address-ranges) 在允許清單中。 它可以協助您嘗試查看它是否適用于不同的網路環境，與公司網路、VPN 或鎖定的網路無關。

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>我的摘要看起來很差、品質不佳或不順暢

1. 檢查您從推播即時串流的電腦上傳頻寬。 頻寬過低可能會導致框架掉落、品質不佳或視訊串流不順暢。 您需要高於您在串流處理之位元速率的上傳頻寬。
1. 請確定您使用的是 Teams 建議的編碼器設定。 如需詳細資訊，請參閱 [在 Microsoft Teams 中手動設定即時活動串流的編碼器](teams-encoder-configuration.md) 。
1. 檢查進入編碼器的音訊/視訊沒有任何問題。 傳送到編碼器的來源音訊或視訊摘要本身可能有問題，因此傳送給檢視者時會遇到錯誤的體驗。
1. 檢查編碼器上的 CPU 負載。 您可能會使用來源內容和/或您嘗試推播的位元速率來將 CPU 最大化。 如果 CPU 負載太高，請嘗試降低即時摘要重迭/內容的複雜度，或降低您在串流處理的位元速率。
1. 確定您的編碼器是最新狀態。 如果是硬體編碼器，請確定您有最新的韌體更新。 如果是軟體編碼器，請確定您執行的是最新版本。
1. 嘗試重設或重新開機您的編碼器。 請注意，如果您在即時串流期間執行此動作，則當您的編碼器重新開機時，檢視者會在播放期間看到錯誤訊息。 從編碼器重新開機即時串流之後，檢視者必須重載頁面，才能再次取得即時串流。

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>我已從編碼器結束即時活動，但檢視者看到錯誤

在中斷連接您的編碼器之前，選取 **[停止事件** ]。 如果您已經中斷連接您的編碼器，您仍然可以選取 **[停止活動]**，但檢視者可能會看到錯誤。

### <a name="my-viewers-are-seeing-issues"></a>我的檢視者看到問題

- 如果單一檢視器回報問題，請確定檢視器有足夠的頻寬，且有良好的網際網路連線來觀看活動。
- 如果相同網路中的多人發生問題，您可能會遇到網路𶔳塞相關問題。 檢閱 [在 Microsoft Teams 中使用 eCDN 來縮放視訊傳遞和監視網路流量](teams-stream-ecdn.md) ，以瞭解您是否可以找出問題的解決方案。
- 很多時候，當多位檢視者看到問題時，實際上會與編碼器摘要相關。
  - 檢查編碼器是否正確設定為編碼器設定中所述的規格，且設定正確。
  - 確定您有足夠的上傳頻寬可以串流。 您可以嘗試減少編碼器輸出的頻寬。
  - 有時重設編碼器會很有説明，但請注意，重新連線時，您必須維持相同的設定。 觀眾可能會在即時活動中看到錯誤或問題。

### <a name="i-or-my-viewers-cant-hear-the-video"></a>我或我的檢視者無法聽到視訊

1. 檢查編碼器是否正在傳送音訊。
1. 檢查音訊裝置是否已接上電源。
1. 如果在 Windows 上，請確定已選取正確的音訊裝置並取消靜音。
1. 如果連接器中斷，某些瀏覽器或裝置可能無法正確復原和播放音訊。

> [!NOTE]
> 如果您已將 Microsoft eCDN 部署為即時活動的視訊發佈提供者，請參閱 [疑難排解 eCDN 效能問題](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) ，以取得有關疑難排解您可能遇到的 eCDN 效能問題的詳細資料。
