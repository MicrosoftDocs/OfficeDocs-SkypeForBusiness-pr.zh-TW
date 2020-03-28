---
title: Microsoft Teams 如何使用記憶體
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft 團隊如何使用系統記憶體，以及為什麼桌面應用程式與 web 應用程式之間的記憶體使用量相同。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033397"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams 如何使用記憶體

有些 Microsoft 團隊使用者有關于團隊如何使用記憶體的問題。 本文說明團隊如何使用記憶體，以及為什麼團隊桌面應用程式（應用程式）和團隊 web app 不會防止同一部電腦上的其他應用程式和工作負載能以最佳的方式執行。 團隊是設計用來使用新式 web 技術的。 若要這樣做，小組桌面用戶端是在 Electron 上開發的，使用 Chromium 來轉譯。 此轉譯引擎是在如今許多最流行的瀏覽器（包括邊緣與 Chrome）之後，都是相同的轉譯引擎。

## <a name="how-teams-works"></a>團隊的運作方式

在 Electron 上設計的團隊可讓您更快速地進行開發，而且也會在不同的作業系統（Windows、Mac 和 Linux）之間維持團隊版本之間的同位。 此同位是可能的，因為 Electron 和 Chromium 會在所有版本中維持相似的程式碼基底。 這個體系結構的另一個優點是，小組 web app 與桌上出版本之間有類似的記憶體使用量設定檔。 Web app 和桌上出版都使用記憶體，與瀏覽器使用的方式類似。 有關 Electron 的詳細資訊可在[他們的網站](https://electronjs.org/)上使用。

如需詳細資訊，請參閱[Chrome 記憶體中](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)的[Chromium 記憶體使用量](https://www.chromium.org/developers/memory-usage-backgrounder)與重要概念。

下列影像顯示適用于 Windows 和小組 Web app （在此範例中，在 Google Chrome 中執行）的小組桌面應用程式的並排記憶體使用量。

![團隊桌面應用程式和 Web app 記憶體使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>團隊中的記憶體使用量

瞭解團隊在系統記憶體中的*預期*行為，並瞭解真正問題的系統記憶體問題的症狀，這一點很重要。

### <a name="expected-memory-usage-by-teams"></a>小組預期的記憶體使用量

不論您執行的是團隊桌面應用程式還是團隊 web app，Chromium 會偵測到有多少可用的系統記憶體，並充分利用該記憶體來優化轉譯體驗。 當其他 app 或服務需要系統記憶體時，Chromium 會為那些進程帶來記憶體。 Chromium [調整小組的記憶體使用量]，以優化團隊效能，而不會影響目前執行的任何其他專案。

如此一來，類似的 Chromium 工作負載可能會使用不同的記憶體量，視可用的系統記憶體數量而定。

下圖說明四個不同系統上的小組記憶體使用量，每個都有不同的可用記憶體量。 每個系統都會處理相似的工作負荷（相同的 app 開啟並執行）。

![團隊在不同系統上的記憶體使用量](media/teams-memory-usage.png)

當電腦有更多記憶體時，小組會使用該記憶體。 在記憶體不足的系統中，小組將會使用較少的時間。

### <a name="symptoms-of-system-memory-issues"></a>系統記憶體問題的症狀

如果您在電腦上看到下列一或多個症狀，可能會有嚴重的系統記憶體問題：

- 當多個大型應用程式同時執行時，會使用高記憶體。
- 系統效能變慢或應用程式掛起。
- 所有 app 在90% 或更高的整體系統記憶體使用量。 使用這個記憶體使用量時，小組應該將記憶體傳回其他 app 和工作負載。 持續記憶體使用量90% 可能意味著團隊沒有將記憶體傳回給系統，這表示發生問題。

下列影像顯示在系統記憶體使用量異常高時，工作管理員中的視圖範例。

![[工作管理員] 中的小組記憶體使用量視圖](media/teams-memory-high-mem-process-list.png)

![[團隊記憶體使用量] 圖形在 [工作管理員] 中](media/teams-memory-high-mem-process-list2.png)
