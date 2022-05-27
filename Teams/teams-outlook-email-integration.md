---
title: Teams與Outlook電子郵件整合
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解Teams和Outlook電子郵件整合功能，包括可讓使用者在Outlook的電子郵件與聊天或Teams頻道交談之間共用資訊的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd1226cddb41ee40139029b64c65d6c151c3993b
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681754"
---
# <a name="teams-and-outlook-email-integration"></a>Teams與Outlook電子郵件整合

Microsoft Teams包含可讓貴組織中的使用者輕鬆在Outlook的電子郵件與Teams中的聊天或頻道交談之間共用資訊，以及掌握未接交談的功能。 本文提供您適用的這些功能和系統管理控制項概觀。

## <a name="share-to-outlook"></a>分享給Outlook

**共用至Outlook** 可讓使用者在Outlook中將Teams交談的複本共用至電子郵件，而不需要離開Teams。 如果使用者需要與其直接小組或甚至貴組織外部的使用者共用交談或狀態更新，這項功能就很實用。 移至Teams交談的頂端，選取 **...[更多選項]**，然後選取 [**共用] 以Outlook**]。  若要深入瞭解，請參閱[從Teams分享Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![螢幕擷取畫面顯示 Teams 中的 [分享至Outlook] 功能。](media/share-to-outlook.png)

若要使用此功能，使用者必須開啟Outlook 網頁版。 如果關閉Outlook 網頁版，使用者 **的 [共用至Outlook**] 選項就不會顯示在Teams中。 如需如何開啟和關閉Outlook 網頁版的步驟，請參閱[啟用或停用信箱Outlook 網頁版](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)。

## <a name="actionable-activity-emails"></a>可採取動作的活動電子郵件

使用者會自動收到可採取動作的未接活動電子郵件，協助他們在Teams中掌握未接的交談。 錯過的活動電子郵件會顯示交談中的最新回復，包括未接郵件後傳送的訊息，使用者可以按一下 [**回復**] 直接從Outlook內回復。 若要深入瞭解，請參閱[回復來自Outlook的未接活動電子郵件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Windows Mac 版 Outlook 或某些舊版 Outlook 不支援此功能。 如需詳細資訊，請參閱[Outlook和Office 365群組中的可採取動作的郵件](/outlook/actionable-messages/)。

![顯示未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email.png)

![顯示如何回復未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email-reply.png)

您可以搭配 **SmtpActionableMessagesEnabled** 參數使用 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 來關閉可採取動作的電子郵件。 根據預設， **SmtpActionableMessagesEnabled** 參數設為 **True**。 將參數設為 **False** 可關閉Office 365的電子郵件訊息。 對於Teams使用者，這表示未接活動電子郵件中無法使用直接在Outlook中回應的 [**回復**] 選項。 錯過的活動電子郵件反而包含 [**在Teams中回復**] 選項，讓使用者在 Teams 中回復。

另請參閱[Outlook和Office 365群組中的可採取動作的郵件](/outlook/actionable-messages/)。
