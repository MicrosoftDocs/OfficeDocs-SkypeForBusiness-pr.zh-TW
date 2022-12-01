---
title: 管理可採取動作的活動電子郵件
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何啟用和停用 teams 交談中可採取動作的活動電子郵件Microsoft
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198505"
---
# <a name="manage-actionable-activity-emails"></a>管理可採取動作的活動電子郵件

可採取動作的活動電子郵件預設為啟用，並通知貴組織中的使用者Microsoft Teams 上的未接交談。

錯過的活動電子郵件會顯示交談的最新回復，包括在未接的訊息之後傳送的訊息。 這項功能可讓使用者直接從 Outlook 回復，方法是選取 [ **回復]**。

## <a name="disable-actionability-in-missed-activity-emails"></a>停用錯過活動電子郵件中的可執行性

雖然此功能預設為啟用，但您可以執行下列命令，關閉貴組織內活動電子郵件的可執行性：

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

停用此功能後，Teams 中的 **[回復** ] 選項會取代 [ **回復** ]，讓錯過的活動電子郵件不再視為可採取動作。 使用者將無法直接從 Outlook 回應，並會被導向在 Teams 上繼續交談。

> [!NOTE]
> Mac 版 Outlook或某些舊版 Windows 版 Outlook 不支援此功能。 如需詳細資訊，請參閱[Outlook 和Office 365群組中的可採取動作的郵件](/outlook/actionable-messages/)。

## <a name="related-topics"></a>相關主題

[回復 Outlook 中未接的活動電子郵件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。

[Outlook 和 Office 365 群組中可採取動作的郵件](/outlook/actionable-messages/)。
