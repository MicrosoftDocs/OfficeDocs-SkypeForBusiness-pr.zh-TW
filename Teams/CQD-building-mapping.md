---
title: 為通話品質儀表板（CQD）建立地圖
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何建立您可以用來在通話品質儀表板（CQD）中上傳租使用者和組建資料的組建地圖。
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086043"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>為通話品質儀表板（CQD）建立地圖

在 Microsoft 團隊或商務用 Skype Online 部署中，所有用戶端都是外部的。 因此，根據預設，所有用戶端都會在通話品質儀表板（CQD）中報告為外部，不論用戶端是否已連線至內部公司網路。

當您使用 CQD 時，您必須知道端點的位置，以及它是否已連線到您可以管理的網路，或是您無法管理的網路，假設您只能改善您可以管理的網路。 透過將子網和組建資訊上傳到 CQD，您可以讓 CQD 判斷端點是連線到內部（受管理的）網路或外部（未受管理的）網路。 這就是為什麼為貴組織建立組建地圖並[將其上傳到 CQD](CQD-upload-tenant-building-data.md)很重要的原因。

## <a name="building-mapping-tools"></a>建立地圖工具

您可以透過多種方式來對應貴組織的子網。 如果您需要協助，您可以使用此[博客文章](https://aka.ms/cqdtools)中所述的 CQDTools PowerShell 模組。 這些工具是以 PowerShell 為基礎，並使用 Active Directory （AD）網站和服務與 Microsoft DHCP 服務協助預先填入您的組建檔案。 這些工具將協助您執行下列任務：

1. 查詢廣告網站和服務，並根據所含的資訊建立組建檔案。
1. 查詢 Microsoft DHCP 伺服器或伺服器以抽取子網資訊並自動建立組建檔案。
1. 驗證現有的建築物檔案、檢查重複專案和重疊。
1. 在 CQD 中尋找未對應的子網。

## <a name="related-topics"></a>相關主題

[在 CQD 中上傳租使用者和組建資料](CQD-upload-tenant-building-data.md)