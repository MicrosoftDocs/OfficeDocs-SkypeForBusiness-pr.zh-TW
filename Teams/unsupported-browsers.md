---
title: 不支援的瀏覽器上的 Microsoft Teams 會議
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解 Teams 如何在不受支援的瀏覽器中支援音訊和視訊。
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 71fb02fae88f2f61d2d6435e126e20093a5a3baf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267819"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>不支援的瀏覽器上的 Microsoft Teams 會議

Internet Explorer 11、Safari 和 Firefox 等部分瀏覽器支援 Microsoft Teams Web App，但不支援部分 Teams 通話和會議功能。 為了解決此限制，Teams Web App 可讓使用者透過 PSTN 連線接收音訊，並讓他們以降低顯示速率檢視呈現的內容 (螢幕共用) 。

> [!Note]
> 自 2021 年 8 月 17 日起，Microsoft 365 應用程式與服務將不支援 Internet Explorer 11， (從 2020 年 11 月 30 日開始，Microsoft Teams 不支援 Internet Explorer 11，) 。 [深入了解](https://aka.ms/AA97tsw)。 請注意，Internet Explorer 11 仍然是受支援的瀏覽器。 Internet Explorer 11 是 Windows 作業系統的元件，並遵循其安裝所在產品 [的生命週期原則](/lifecycle/faq/internet-explorer-microsoft-edge) 。

當 Teams 偵測到不受支援的瀏覽器時，它會自動顯示一則訊息，說明問題與會話限制。 訊息會提供存取會議音訊的進一步指示，例如建議使用者留下回撥號碼，讓 Teams 可以撥打電話給使用者，或指示使用者撥打會議邀請中包含的會議號碼。 訊息也鼓勵使用者下載並使用 [Teams 桌面用戶端](https://teams.microsoft.com/downloads) ，以獲得完整的 Teams 體驗。

如果 PSTN 無法使用，使用者將不會看到存取會議的指示，也無法加入會議。

## <a name="browser-limitations"></a>瀏覽器限制

在不受支援的瀏覽器上使用 Teams Web App 的使用者將會遇到下列限制：

- 音訊僅可透過 PSTN 連線使用。 使用者無法使用麥克風。
- 使用者無法共用相機或查看其他參與者的視訊，但可以透過影像型螢幕畫面分享來檢視呈現的內容。
- 使用者無法共用螢幕畫面，但可以看到其他會議參與者共用的畫面。
- 使用者無法在螢幕共用會話期間取得控制權。
- 使用者不會收到來電通知。
- 如果通話中斷，會議不會自動重新連線。
- 使用者無法開始會議。

如需有關 Teams 中瀏覽器支援的詳細資訊，請參閱 [Teams 的限制和規格](./limits-specifications-teams.md#browsers)。

## <a name="related-topics"></a>相關主題

- [在不受支援的瀏覽器上加入 Teams 會議](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)