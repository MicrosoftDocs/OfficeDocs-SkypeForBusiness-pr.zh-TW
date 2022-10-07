---
title: Teams 系統管理中心的Microsoft Teams 會議室授權概觀
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 瞭解及比較 Teams 系統管理中心的Teams 會議室授權和功能可用性。
ms.openlocfilehash: 0e4a3d4fc15f5e978731254e3344ee6e413ff682
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999628"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Teams 系統管理中心的Microsoft Teams 會議室授權概觀

Teams 系統管理中心可讓您從中央位置檢視和管理Teams 會議室裝置及其周邊裝置。 本文將根據Teams 會議室裝置是否獲指派 Microsoft Teams 會議室 Basic 或 Microsoft Teams 會議室 專業版授權，來說明您擁有[哪些管理功能](#comparison-of-teams-rooms-feature-availability-by-license)。

如需Microsoft Teams 會議室授權的詳細資訊，請[參閱Microsoft Teams 會議室授權](rooms-licensing.md)。

> [!NOTE]
> 如果您有現有的 Teams 會議室 Standard 或 Teams 會議室 Premium 舊版授權，您必須在舊版授權到期時切換到 Teams 會議室 專業版。 如果您有Enterprise 合約，您必須在下一個續約期間切換到Teams 會議室專業版授權。 如需詳細資訊，請參閱[從 Teams 會議室 Standard 和 Teams 會議室 Premium 切換](rooms-licensing.md#switching-from-teams-rooms-standard-and-teams-rooms-premium)。

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>查看已指派哪些授權給Teams 會議室裝置

您可以在 Teams 系統管理中心移至 Teams 裝置，然後選取 Windows 上的裝置類別 (Teams 會議室、Android 上的Teams 會議室，以及您想要查看的 Surface Hub) ，以查看您的裝置擁有哪些授權。 例如，如果您在 **Windows 上** 選取 **Teams 裝置**  >  Teams 會議室，您會看到類似下列影像的內容。 [**授權]** 欄會顯示指派給每個裝置Teams 會議室授權。

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Teams 會議室庫存清單，並著重于標準版、專業版和專業版 (試用版) 授權。":::

擁有 **專業版** 授權的裝置可以存取 Teams 系統管理中心的所有功能。 具有其他授權的裝置可以存取這些功能的子集合。 您可以在[[依授權比較Teams 會議室功能可用性](#comparison-of-teams-rooms-feature-availability-by-license)] 中查看每個授權可用的功能。

> [!IMPORTANT]
> 如果您選取了多個同時包含 Microsoft Teams 會議室 Basic 和 Microsoft Teams 會議室 專業版授權的裝置，則需要Microsoft Teams 會議室專業版授權的動作只會在已指派該授權的裝置上執行。 此動作不會在指派基本Microsoft Teams 會議室授權的裝置上執行。

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>查看哪些功能需要Microsoft Teams 會議室專業版授權

需要Microsoft Teams 會議室專業版授權的功能可以在裝置的詳細資料頁面上尋找 :::image type="icon" source="../media/mtr-pro-icon.png" border="false"::: 圖示來識別。 如果目前選取的裝置未獲指派Microsoft Teams 會議室專業版授權，您將無法執行該動作，並會看到升級提示。

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="顯示 Pro 圖示Teams 會議室裝置重新開機對話方塊。":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>依授權比較Teams 會議室功能可用性

下表顯示 Teams 系統管理中心中每個Microsoft Teams 會議室授權可用的管理功能。

|                                               | Microsoft Teams 會議室基本版 | Microsoft Teams 會議室專業版 |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **自動裝置更新**                  | &#x2714;                    | &#x2714;                  |
| **基本裝置分析**                    | &#x2714;                    | &#x2714;                  |
| **基本裝置健康情況**                       | &#x2714;                    | &#x2714;                  |
| **通話品質儀表板**                    | &#x2714;                    | &#x2714;                  |
| **建立和檢視工作區**                | &#x2714;                    | &#x2714;                  |
| **即時遙測**                       | &#x2714;                    | &#x2714;                  |
| **一般功能更新**                   | &#x2714;                    | &#x2714;                  |
| **遠端登入和登出**               | &#x2714;                    | &#x2714;                  |
| **Android 裝置設定**             |                             | &#x2714;                  |
| **裝置警示**                             |                             | &#x2714;                  |
| **裝置分析 - 健康情況與使用率** |                             | &#x2714;                  |
| **裝置詳細資料檢視**                        |                             | &#x2714;                  |
| **裝置健康情況詳細資料**                     |                             | &#x2714;                  |
| **裝置標籤**                               |                             | &#x2714;                  |
| **圖形 API**                                |                             | &#x2714;                  |
| **遠端重新開機**                            |                             | &#x2714;                  |
| **Windows 裝置周邊管理**     |                             | &#x2714;                  |
| **Windows 裝置設定**                   |                             | &#x2714;                  |
