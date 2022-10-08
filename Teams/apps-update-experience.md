---
title: Microsoft Teams 中的應用程式更新體驗
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/04/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 在此文章中，了解如何更新已及系統管理員如何加速更新 Microsoft Teams 中的 Microsoft 應用程式、自訂應用程式和協力廠商應用程式。
ms.openlocfilehash: 14c327c2a24536f5441b318767e301ffe9a3196d
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376811"
---
# <a name="teams-app-updates-and-admin-role"></a>Teams 應用程式更新與系統管理員角色

Teams 系統管理員可以協助使用者取得最新版本的應用程式。 若要這麼做，他們會完成下列一或兩項工作：

* 更新當應用程式開發人員或廠商提供新版本時，可在 Teams 市集中取得[的協力廠商應用程式](#updates-to-third-party-apps)。
* 更新只有當您的開發人員提交新版本時才可在貴組織中使用的[自訂應用程式](#updates-to-custom-apps)。

## <a name="updates-to-third-party-apps"></a>更新至協力廠商應用程式

使用者若要安裝及使用應用程式，必須授與許可權給應用程式，才能存取所需的服務和資訊。 在大多數情況下，當 Teams 市集中有新版已安裝的應用程式可用時，系統會自動為所有使用者更新該應用程式。 不過，新版應用程式中的一些特定變更需要再次獲得使用者許可權。 這個重複的使用者接受會確保使用者對於功能或個人資訊存取等變更的意識。 Teams 系統管理員可以 [代表使用者提供應用程式的許可權](app-permissions-admin-center.md)。

如果應用程式開發人員對其應用程式進行下列一或多項變更，使用者必須核准應用程式的更新。

* 新增或移除 Bot。 使用屬性變更 Bot 的 `botId` 識別碼。
* `isNotificationOnly`變更現有 Bot 的屬性，以變更 Bot 的通知。
* 變更 `SupportsCalling` 現有 Bot 的 、 `SupportsVideo` 和 `SupportsFiles` 屬性，以新增通話、播放影片，以及上傳或下載檔案的功能。
* 新增或移除授權許可權。
* 新增或移除訊息延伸模組、新增群組索引標籤、新增連接器或新增頻道。
* 變更資訊清單檔案中的 [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) 參數。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>更新自訂應用程式

在組織內建立和部署的自訂應用程式可供租使用者或組織中的使用者使用。 Teams 系統管理員將自訂應用程式更新為組織內開發人員所提供的新版本。 如需詳細資訊，請參閱 [系統管理員如何管理自訂應用程式](custom-app-overview.md)。

## <a name="related-article"></a>相關文章

* [瞭解應用程式中更新完成的資訊清單架構](/microsoftteams/platform/resources/schema/manifest-schema)。
* [瞭解自訂應用程式管理](custom-app-overview.md)。
