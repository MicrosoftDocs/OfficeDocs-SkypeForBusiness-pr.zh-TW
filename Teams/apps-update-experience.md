---
title: Microsoft Teams 中的應用程式更新體驗
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 在此文章中，了解如何更新已及系統管理員如何加速更新 Microsoft Teams 中的 Microsoft 應用程式、自訂應用程式和協力廠商應用程式。
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299042"
---
# <a name="update-apps-in-microsoft-teams"></a>更新 Microsoft Teams 中的應用程式

在大多數情況下，在 Teams Store 中推出新版應用程式之後，系統會自動為使用者更新該應用程式。 不過，新應用程式版本中的一些特定變更需要使用者接受應用程式才能更新。 使用者接受可確保使用者對於功能或存取等變更的意識。 如果應用程式開發人員對 Microsoft Teams 應用程式進行下列特定變更，您的使用者必須核准應用程式更新：

* 已新增 Bot。
* 現有 Bot 的 `botId` 屬性或 `isNotificationOnly` 屬性隨即變更。
* 已新增 Bot 的 `SupportsCalling`、`SupportsVideo` 和 `SupportsFiles` 功能。
* 已新增傳訊擴充功能。
* 「授權」內的權限已新增或變更。
* `Id` 或 `ApplicationPermissionsHash` 或兩者會在 `webApplicationInfo` 中變更。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>相關文章

* [瞭解應用程式中更新完成的資訊清單架構](/microsoftteams/platform/resources/schema/manifest-schema)。
