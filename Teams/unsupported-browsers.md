---
title: 不支援瀏覽器上的 Microsoft Teams 會議
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解 Teams 如何在不支援的瀏覽器中支援音訊和視音訊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121311"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>不支援瀏覽器上的 Microsoft Teams 會議

某些瀏覽器 ，例如 Internet Explorer 11、Safari 和 Firefox，支援 Microsoft Teams Web App，但不支援一些 Teams 通話和會議功能。 若要解決這項限制，Teams Web App 可讓使用者透過 PSTN 連接接收音訊，並讓他們以降低的顯示 (螢幕) 畫面分享內容。

> [!Note]
> 自 2021 年 8 月 17 日起，Microsoft 365 應用程式和服務不支援 Internet Explorer 11 (Microsoft Teams 將不支援 Internet Explorer 11，從 2020 年 11 月 30 日) 。 [深入了解](https://aka.ms/AA97tsw)。 請注意，Internet Explorer 11 仍然是受支援的瀏覽器。 Internet Explorer 11 是 Windows 作業系統的[](/lifecycle/faq/internet-explorer-microsoft-edge)一個元件，並遵循安裝該作業系統之產品的生命週期政策。

當 Teams 偵測到不支援的瀏覽器時，它會自動顯示一則訊息，說明問題與會話限制。 此訊息提供存取會議音訊的進一步指示，例如建議使用者留下回電號碼，讓 Teams 可以打電話給使用者，或指示使用者撥打會議邀請中包含的會議號碼。 訊息也會鼓勵使用者下載並使用 Teams 桌面 [用戶端](https://teams.microsoft.com/downloads) ，以體驗完整的 Teams 體驗。

如果 PSTN 無法使用，使用者將看不到存取會議的指示，且無法加入會議。

## <a name="browser-limitations"></a>瀏覽器限制

在不支援的瀏覽器上使用 Teams Web App 的人將會遇到下列限制：

- 音訊僅能透過 PSTN 連接使用。 使用者無法使用麥克風。
- 使用者無法共用相機或查看其他參與者的影片，但可以透過圖像型螢幕分享來查看呈現的內容。
- 使用者無法共用其螢幕，雖然他們可以看到另一個會議參與者分享的畫面。
- 使用者無法控制螢幕共用會話期間。
- 使用者不會收到來電通知。
- 如果通話中斷，會議不會自動重新連接。
- 使用者無法開始會議。

有關 Teams 中的瀏覽器支援詳細資訊，請參閱 Teams [的限制和規格](./limits-specifications-teams.md#browsers)。

## <a name="related-topics"></a>相關主題

- [在不支援的瀏覽器上加入 Teams 會議](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)