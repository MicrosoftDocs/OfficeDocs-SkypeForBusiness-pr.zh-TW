---
title: Microsoft Teams 中串流的編碼器設定
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
description: 本文將討論 Microsoft Teams 串流事件的編碼器型 RTMP 設定。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767929"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>在 Microsoft Teams 中使用編碼器進行即時串流

Teams 編碼器可讓使用者使用 Microsoft Teams 直接從外部硬體或軟體型編碼器產生即時活動。

## <a name="overview"></a>概觀

編碼器會從您在即時活動中使用的各種來源擷取音訊和視訊內容，例如相機、麥克風、桌面螢幕擷取等等。 它會將該媒體壓縮並轉換成適當的數位格式，然後將它傳送給 Teams，以便即時串流給您的觀眾。 請參閱我們的 [自訂生產活頁簿](https://aka.ms/CustomProductionVEP) ，以深入瞭解如何使用 Teams 生產技術 (例如 NDI) 與外部編碼器。

## <a name="production-workflow-when-using-an-encoder"></a>使用編碼器時的生產工作流程

製作 Teams Live 事件的工作流程如下所示：

即時活動已在 Teams 或 Yammer 中排程，且已選取 **[Teams 編碼器** ] 選項。 此規定 RTMP 端點隨附 RTMP (S) URL 和對應機碼。 編碼器會使用 URL 和按鍵連線至已排程即時活動的 RTMP 端點。

### <a name="common-encoders-user-with-live-events"></a>使用即時事件的常用編碼器使用者

Microsoft 已對下列兩份清單中的編碼器進行 Teams 即時串流測試。 第一個清單是這些編碼器的子集合，這些編碼器已經與產品一起測試，以方便使用和快速設定。

#### <a name="stream-ready-encoders"></a>Stream 就緒編碼器

|編碼                                |網站  |詳細資料  |
|---------------------------------------|---------|---------|
|Vision                              |[Vision Makito X](https://www.haivision.com/microsoft/stream) |使用[錄製中心] 提供高品質 HD 視訊，這是 RTMP 的強大替代方案。 |
|Vision                              |[Vision KB](https://www.haivision.com/microsoft/stream) |H.264 和 HEV 視訊編碼器提供高品質的 ABR 視訊串聯，解析度高達 4K。 |
|開啟[廣播軟體] (OBS Studio)  |[開啟[廣播軟體]](https://obsproject.com/) |高效能即時視訊/音訊擷取和混搭 —支援所有串流平臺等等。 |
|vMix                                   |[vMix](https://www.vmix.com/) |可控制相機、視訊、音訊及其他專案錄製、混合及即時串流的軟體視覺混音器。 |
|有線廣播                               |[有線廣播](https://www.telestream.net/wirecast) |涵蓋所有基本概念的網路廣播軟體 + 多重攝影機生產。 |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |將多個 Apple 裝置與一或多個相機同步處理，以便即時擷取和編輯影片。 |
|AWS 元素即時                     |[AWS 元素即時](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |即時串流至連線網際網路的裝置的即時視訊和音訊錄製 |
|XSplit 廣播                     |[XSplit 廣播](https://www.xsplit.com/) |產生、混合並提供豐富的影片內容，包括即時串流的遊戲。 |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |用於處理視訊、音訊及其他多媒體檔案和即時串流的軟體開放原始檔套件。 |
|生產卡車          |[生產卡車](https://www.blueframetech.com/productiontruck) |從行動車或卡車現場觀看影片和串流活動。 |
|Live Arena AI 製作人                 |AI 製作人 |Production studio 整合于 Microsoft Teams 做為會議應用程式。|
|StreamYard                             |StreamYard |在瀏覽器中即時串流工作室。|
|社交                              |社交 |雲端視訊生產平臺，提供製作和散發工作室品質影片內容的一體式體驗。|
|Brandlive                              |BrandLive |雲端型生產平臺。|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Vision Makito X Encoder 和 Makito KB Encoder

如果您有現有的設定 X 或 Makito KB 編碼器，您可以從下拉式清單中選擇適當的選項，並依照指示清單進行。

1. 選取 **[開始設定]** 以建立即時串流頻道。 等待設定完成。 您會在螢幕上看到[ **準備好聯** 機] 訊息。
1. 完成之後，下載包含所有編碼參數的預設值，包括內嵌 URL 和事件名稱。 將預設值匯入編碼器並啟動編碼器。
1. 返回至 Teams。 當您能夠從編碼器查看預覽之後，請選取 **[開始] 活動** 以進行即時活動，讓觀眾可以看到即時活動。

> [!NOTE]
> RtMPS 的Vision KB Encoder 支援尚未過測試。 Vision Makito X Encoder 不支援 RTMPS。 這兩個編碼器下載的預設值都包含 RTMP 內嵌 URL。

### <a name="switcher-studio"></a>Switcher Studio

您可以使用 Switcher Studio 開始使用 iPhone 或 iPad 串流至 Teams。

1. 選取 **[開始設定]** 以建立即時串流頻道。 等待設定完成。 您會在螢幕上看到[ **準備好聯** 機] 訊息。
2. Switcher Studio 會開啟 Switcher Studio 儀表板，將即時活動新增至您的帳戶。

> [!NOTE]
> 如果您還沒有 Switcher Studio 帳戶，您必須建立一個) 。

3. 完成後，您可以移至 iPhone 或 iPad 上的 Switcher Studio 應用程式、在 [輸出] 索引標籤中選取 [Teams]，然後開始串流至 Teams。
4. 返回至 Teams。 從編碼器查看預覽之後，請選取 **[開始] 活動** 以進行即時活動，讓觀眾可以看到即時活動。

> [!NOTE]
> Switcher Studio 使用 RTMP 內充 URL。

### <a name="wirecast"></a>有線廣播

如果您是 Wirecast 的現有使用者，您可以從下拉式清單中選擇此選項，將即時串流傳送至 Teams。 請注意，您需要有線廣播版本 10 或更新版本。

1. 選取 **[開始設定]** 以建立即時串流頻道。 等待設定完成。 您會在螢幕上看到[ **準備好聯** 機] 訊息。
1. 編碼器會在電腦上啟動預先設定正確編碼參數的 Wirecast 應用程式，並擷取該即時事件的 URL。 準備好時，按一下 [有線廣播] 應用程式中的 [Teams] 圖示，即可開始串流至 Teams。
1. 返回至 Teams。 從編碼器查看預覽之後，請選取 **[開始] 活動** 以進行即時活動，讓觀眾可以看到即時活動。

> [!NOTE]
> 隨即啟動 Wirecast 應用程式，並預先設定 RTMPS 內含 URL。
