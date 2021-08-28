---
title: 應用程式中的應用程式更新Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何更新應用程式Microsoft Teams。
ms.openlocfilehash: 156bafa45fe51884d6697bb4121143fad98fc7cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593167"
---
# <a name="update-apps-in-microsoft-teams"></a>更新應用程式Microsoft Teams

在大多數情況下，應用程式開發人員發佈 App 更新後，新版本會自動顯示給使用者。 不過，系統對 Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">清單</a>有一些更新需要使用者接受才能完成：

* 已新增或移除 Bot
* 現有 Bot 的 「botId」 屬性已變更
* 已變更現有 Bot 的 "isNotificationOnly" 屬性
* 已新增 Bot 的支援Calling、支援Video 和 SupportsFiles 功能
* 已新增訊息擴充功能
* 已新增連接器
* 「webApplicationInfo」中的屬性已變更

![提供新版本](media/manage-your-custom-apps-update1.png)

![應用程式的升級選項](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 更新程式適用于 Microsoft App、自訂應用程式和協力廠商應用程式的所有 App 更新。 

## <a name="related-topics"></a>相關主題

[管理應用程式](manage-apps.md)
