---
title: Teams電子郵件Outlook整合
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解Teams和Outlook整合功能，包括讓使用者在電子郵件之間共用資訊的功能Outlook以及聊天或頻道交談Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f41d26a2d87d1c95b99534a866f64cd9f30eb8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837455"
---
# <a name="teams-and-outlook-email-integration"></a>Teams電子郵件Outlook整合

Microsoft Teams包含的功能，可讓使用者輕鬆在 Outlook 中的電子郵件與 Teams 中的聊天或頻道交談之間共用資訊，並隨時瞭解未接的交談。 本文提供這些功能和適用之系統管理控制項概觀。

## <a name="share-to-outlook"></a>共用至Outlook

**共用至Outlook** 讓使用者在 Teams 中將交談的一份Outlook共用至電子郵件，而不需要離開Teams。 如果使用者需要與直系小組或甚至貴組織以外的使用者共用交談或狀態更新，這項功能非常實用。 前往交談的頂端，選取 Teams **Teams 更多選項**，然後選取共用 **Outlook。**  若要深入瞭解，請參閱從 Outlook[共用Teams。](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![螢幕擷取畫面顯示 Outlook 共用至Teams。](media/share-to-outlook.png)

若要使用這項功能，Outlook 網頁版使用者必須開啟此功能。 如果Outlook 網頁版關閉，使用者 **Outlook共用至** Teams選項。 若要瞭解如何開啟和關閉信箱Outlook 網頁版，請參閱啟用或Outlook 網頁版[信箱。](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>可採取行動的活動電子郵件

使用者會自動收到可採取動作的未接活動電子郵件，協助他們瞭解未接Teams。 未接的活動電子郵件會顯示來自交談的最新回復，包括未接郵件後所寄的郵件，使用者可以按一下 [回復以直接從 Outlook 中回復。 若要深入瞭解，請參閱回復來自 Outlook 的[未接Outlook。](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> 此功能在 Mac 版 Outlook 或部分舊版的 Outlook 中Windows。 詳細資訊請參閱群組和群組中的[可Outlook Office 365訊息](/outlook/actionable-messages/)。

![顯示未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email.png)

![顯示如何回復未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email-reply.png)

您可以將 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 與 **SmtpActionableMessagesEnabled 參數** 一起使用，以關閉可採取動作的電子郵件。 根據預設 **，SmtpActionableMessagesEnabled 參數** 會設為 **true。** 將參數設定為 **false** 會關閉所有郵件Office 365。 對於Teams，這表示未接活動電子郵件中Outlook回復選項。 相反地，未接的活動電子郵件會包含 Teams **回復選項**，讓使用者在 Teams。

另請參閱[群組和群組中的可Outlook Office 365訊息](/outlook/actionable-messages/)。
