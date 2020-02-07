---
title: Microsoft 團隊中的保留原則已知問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Microsoft 團隊保留原則目前已知問題清單。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838203"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Microsoft 團隊中的保留原則已知問題

> [!NOTE]
> 我們還不支援保留私人通道訊息的設定。 支援在私人通道中共用的檔案保留。

下列是追蹤及調查之小組中保留原則的已知問題。

- 在 [小組頻道訊息位置] 列中的 [選擇團隊] 底下，您可能會看到不是 [小組] 的 Office 365 群組。 未來將會解決這個問題。

- 在 [在團隊聊天位置] 列中選擇 [使用者] 底下，您可能會看到 [來賓] 和 [非信箱] 使用者。 保留原則並非要針對來賓進行設定，我們正在努力從清單中移除這些原則。

- Exchange 生命週期助理（ELC）每天都會執行一次，但其 SLA 是7天。 因此，如果您有小組保留原則刪除超過60天的專案，這些專案可能會持續到67天。 這不是一種新的情況-它是在 Exchange 模型之後。 當然，在大多數情況下沒有延遲。


| | | |
|---------|---------|---------|
|![代表決策點的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |決策點         |貴組織需要哪些安全性與合規性功能？ 貴組織是否有符合安全性與合規性商業需求的必要授權？         |
|![代表後續步驟的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |後續步驟         |記錄您所需的安全性與合規性功能。         |
