---
title: " (CQD) 建立通話品質儀表板的建築物地圖"
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何在 [通話品質儀表板] (CQD) 中建立您可以用來上傳租使用者和建置資料的建築物地圖。
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789818"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a> (CQD) 建立通話品質儀表板的建築物地圖

在 Microsoft Teams 或 商務用 Skype Online 部署中，所有用戶端都是外部用戶端。 因此，根據預設，所有用戶端都會在通話品質儀表板 (CQD) 中回報為外部，無論用戶端是否已連線到內部公司網路。

當您使用 CQD 時，您必須知道端點的位置，以及端點是連線到您可以管理的網路還是無法管理的網路，假設您只能改善您可以管理的網路。 透過將子網和建築物資訊上傳到 CQD，您可啟用 CQD 來判斷端點是連線到內部 (受管理) 網路，還是外部 (未受管理) 網路。 因此，請務必為組織建立建築物地圖，並將 [它上傳到 CQD](CQD-upload-tenant-building-data.md)。

## <a name="building-mapping-tools"></a>建置地圖工具

有許多方式可以對應貴組織的子網。 如果您需要協助，可以使用這 [篇部落格文章](https://aka.ms/cqdtools)中所述的 CQDTools PowerShell 模組。 這些工具是以 PowerShell 為基礎，並使用 Active Directory (AD) 網站與服務以及 Microsoft DHCP 服務，協助預先填入您的建築物檔案。 這些工具可協助您執行下列工作：

1. 查詢 AD 網站與服務，並根據內含的資訊建立建築物檔案。
1. 查詢 Microsoft DHCP 伺服器或伺服器以擷取子網路資訊，並自動建立建築物檔案。
1. 驗證現有的建築物檔案，檢查是否有重複與重迭。
1. 在 CQD 中尋找未對應的子網。

## <a name="related-topics"></a>相關主題

[在 CQD 中上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)