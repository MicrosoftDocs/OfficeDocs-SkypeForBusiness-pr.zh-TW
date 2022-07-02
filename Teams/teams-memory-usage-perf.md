---
title: Microsoft Teams 如何使用記憶體
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 瞭解 Microsoft Teams 系統記憶體使用量，以及為什麼傳統型應用程式與 Web 應用程式之間的記憶體使用量相同。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 0d55caf2a1642b28ccc63e3be1cf3eccc69bb260
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605672"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams 如何使用記憶體

有些 Microsoft Teams 使用者對於 Teams 如何使用記憶體有疑問。 本文說明 Teams 如何使用記憶體，以及為什麼 Teams 桌面應用程式 (應用程式) 和 Teams Web App 無法防止同一部電腦上的其他應用程式和工作負載具有足夠的記憶體以優化執行。 Teams 是專為使用新式 Web 技術所設計。 為了達到此目的，Teams 桌面用戶端是在Electron上開發，其使用Chromium進行轉譯。 這是現今許多熱門瀏覽器背後的相同轉譯引擎，包括 Edge 和 Chrome。

## <a name="how-teams-works"></a>Teams 的運作方式

在Electron 上設計的 Teams 可加快開發速度，而且在 Windows、Mac 和 Linux) 等不同作業系統 (，Teams 版本之間也維持同位。 這有可能是因為Electron 和 Chromium在所有版本中都維持類似的程式碼基礎。 此架構的另一個優點是 Teams Web App 與桌上出版本之間有類似的記憶體使用狀況設定檔。 Web 應用程式和桌上出版本使用記憶體的方式與瀏覽器使用記憶體的方式類似。 有關Electron的詳細資訊可 [在他們的網站上](https://electronjs.org/)取得。

如需詳細資訊，請參閱Chromium [Chrome 記憶體中的](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)[記憶體使用量](https://www.chromium.org/developers/memory-usage-backgrounder)和重要概念。

下圖顯示 Windows 版 Teams 傳統型應用程式的並排記憶體使用量，以及在此範例中執行 Google Chrome) 的 Teams Web App (。

![傳統型應用程式和 Web 應用程式的 Teams 記憶體使用量。](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Teams 中的記憶體使用量

請務必瞭解 Teams 在系統記憶體方面 *的預期* 行為，並瞭解真正有問題的系統記憶體問題症狀。

### <a name="expected-memory-usage-by-teams"></a>Teams 的預期記憶體使用量

無論您執行的是 Teams 傳統型應用程式或 Teams Web App，Chromium偵測到有多少系統記憶體可用，並充分運用該記憶體來優化轉譯體驗。 當其他應用程式或服務需要系統記憶體時，Chromium為這些程式提供記憶體。 Chromium持續調整 Teams 記憶體使用量，以優化 Teams 效能，而不會影響目前執行中的其他任何專案。

如此一來，類似Chromium工作負載會根據可用的系統記憶體量，使用不同的記憶體量。

下圖說明 Teams 在四個不同系統上的記憶體使用量，每個系統都有不同數量的可用記憶體。 每個系統都會處理類似的工作負載， (開啟並執行) 的相同應用程式。

![跨不同系統的 Teams 記憶體使用量。](media/teams-memory-usage.png)

當電腦有更多記憶體時，Teams 會使用該記憶體。 在記憶體不足的系統中，Teams 會使用較少。

### <a name="symptoms-of-system-memory-issues"></a>系統記憶體問題的問題

如果您在電腦上看到下列一或多個症狀，表示您可能有嚴重的系統記憶體問題：

- 當多個大型應用程式同時執行時，使用高記憶體。
- 系統效能緩慢或應用程式當機。
- 在所有應用程式中持續使用 90% 或更高的系統記憶體。 有了這麼大的記憶體使用量，Teams 應該會將記憶體還給其他應用程式和工作負載。 持續使用 90% 的記憶體可能表示 Teams 沒有將記憶體回系統，這表示有問題。

下列影像顯示當系統記憶體使用量異常高時，工作管理員中的檢視範例。

![[工作管理員] 中的 [Teams 記憶體使用狀況] 檢視。](media/teams-memory-high-mem-process-list.png)

![工作管理員中的 Teams 記憶體使用量圖表。](media/teams-memory-high-mem-process-list2.png)
