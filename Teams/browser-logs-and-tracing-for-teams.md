---
title: Teams 的瀏覽器記錄和追蹤
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解 Microsoft Teams 所產生的瀏覽器和 WebRTC 記錄檔、可找到這些記錄的位置、如何使用Microsoft 支援服務收集記錄檔，以及如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005459"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Teams 的瀏覽器記錄和追蹤

對於某些類型的錯誤，Microsoft 支援服務可能需要您收集瀏覽器追蹤。 這項資訊可以提供有關錯誤發生時 Teams 用戶端狀態的重要詳細資料。 本文說明如何收集 Teams 的瀏覽器和 WebRTC 記錄檔。

## <a name="browser-logs"></a>瀏覽器記錄

開始瀏覽器追蹤之前，請確定您已登入 Teams。 請務必先執行此動作，再啟動追蹤，讓追蹤不含敏感的登入資訊。

登入之後，請根據您的瀏覽器，選取下列其中一個連結，然後依照提供的步驟進行。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [邊緣](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [火狐](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步驟中，將所有Azure 入口網站參照取代為 Teams 用戶端。
  
## <a name="webrtc-logs-in-browsers"></a>瀏覽器中的 WebRTC 記錄

WebRTC 記錄檔可以提供音訊和視訊通話的連線詳細資料，協助Microsoft 支援服務。 依照步驟在 Edge (Chromium) 或 Chrome 中存取 WebRTC 記錄檔：
  
1. 開啟新索引標籤，然後移至下列其中一個 URL：
    - Edge (Chromium) ：`edge://webrtc-internals/`
    - 鉻： `chrome://webrtc-internals/`
  
2. 開啟 Teams Web 應用程式並重現問題。
  
3. 返回到步驟 1 中存取的索引標籤，您會看到至少兩個索引標籤：
    - GetUserMedia 要求
    - `https://teams.microsoft.com/url`

4. 選擇含有 Teams 應用程式名稱的索引標籤，然後儲存頁面內容。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)

[在 Teams 中設定記錄檔以進行監視和疑難排解](/MicrosoftTeams/log-files)
