---
title: '建立通話品質儀表板的建 (CQD) '
ms.author: serdars
author: SerdarSoysal
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
description: 瞭解如何建立建築物地圖，以在 CQD (中上傳租使用者和) 。
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634097"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>建立通話品質儀表板的建 (CQD) 

在 Microsoft Teams 或 商務用 Skype部署中，所有用戶端都是外部的。 因此，根據預設，所有用戶端都會在通話品質儀表板 (CQD) 中報告為外部，無論用戶端是否已在內部公司網路上連接。

當您使用 CQD 時，您必須知道端點的位置，以及端點是否連接到您可以管理的網路或無法管理的網路，前提是只能改善您可以管理的網路。 將子網和建築物資訊上傳至 CQD，您可以啟用 CQD 來判斷端點是連接到內部 (受管理的) 網路，還是外部 (未管理的) 網路。 這就是為什麼為貴組織建立建築物地圖並將其上傳到 [CQD](CQD-upload-tenant-building-data.md)非常重要的原因。

## <a name="building-mapping-tools"></a>建立地圖工具

有許多方法可以映射貴組織的子網。 如果您需要協助，您可以使用這篇部落格文章中所述的 CQDTools PowerShell [模組](https://aka.ms/cqdtools)。 這些工具是以 PowerShell 為基礎，並使用 Active Directory (AD) 網站與服務和 Microsoft DHCP 服務，協助預先填入您的建房檔案。 這些工具可協助進行下列工作：

1. 查詢 AD 網站和服務，然後根據所包含的資訊建立建房檔案。
1. 查詢 Microsoft DHCP 伺服器或伺服器以提取子網資訊，並自動建立建築物檔案。
1. 驗證現有的建築物檔案，檢查重複和重迭。
1. 在 CQD 中尋找未映射的子網。

## <a name="related-topics"></a>相關主題

[Upload在 CQD 中建立租使用者和建築物資料](CQD-upload-tenant-building-data.md)