---
title: Microsoft Teams 監控與警示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: 瞭解 Teams 系統管理中心提供的 Teams 通知和通知功能Microsoft。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 18279954a9bd71932422bd60519977288ae30ca6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438251"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Microsoft Teams 監控與警示

Teams 系統管理中心提供適用于 Microsoft Teams 的新監控和警示功能。 使用 Teams 系統管理中心 [ **通知&通知** ] 區段下所提供的不同規則來監控 Teams 功能並接收通知。 例如，您可以主動監視 Teams 裝置的健康情況，例如 IP Phone、Android 上的 Teams 會議室，以及其他裝置意外離線。  

您的組織可以使用 Teams 監控和警示來執行下列專案：

- 自動管理 Teams 功能
- 如果出現非預期的訊息，請提醒您。
- 採取修正性動作，讓專案步入正軌。

> [!NOTE]
> 在 GCC/GCC-High 環境中無法使用 Teams 系統管理中心內的警示功能。

## <a name="how-to-manage-monitoring-and-alerting"></a>如何管理監視和警示

 您必須是 Microsoft 365 中的全域系統管理員或 Teams 服務系統管理員，才能設定警示規則。 請參閱 [使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md) ，以深入瞭解 Teams 系統管理員角色，以及每個系統管理員角色可以存取哪些報告。

1. 登入 Teams 系統管理中心。
2. 在左側導覽畫面中，選 **取 [通知&通知]**。
3. 選擇您要從 [規則] 設定的 **規則**。

## <a name="teams-monitoring-rules-reference"></a>Teams 監控規則參考

我們透過新增各種監控功能和設定功能，持續新增並改善 Teams 監控體驗。 以下是 Teams 系統管理中心目前提供的 Teams 監控規則清單。


|規則  |監控功能|監視哪些內容？ |
|---------|---------|---------|
|應用程式提交  |Teams 應用程式 | 如果 Teams 應用程式已提交核准，請主動監控它們。|
|[裝置狀態規則](device-health-status.md)  |Teams 裝置 | 如果 Teams 裝置離線，請主動監視裝置。|
