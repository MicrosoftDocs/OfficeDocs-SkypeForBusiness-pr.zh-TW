---
title: Teams 與 Outlook 電子郵件整合
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解 Teams 和 Outlook 電子郵件整合功能，包括可讓使用者在 Outlook 中的電子郵件與 Teams 中的聊天或頻道交談之間共用資訊的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606232"
---
# <a name="teams-and-outlook-email-integration"></a>Teams 與 Outlook 電子郵件整合

Microsoft Teams 包含可讓貴組織中的使用者輕鬆在 Outlook 中的電子郵件與 Teams 中的聊天或頻道交談之間共用資訊，並隨時掌握未接交談的功能。 本文提供您適用的這些功能和系統管理控制項概觀。

## <a name="share-to-outlook"></a>共用至 Outlook

**[共用至 Outlook** ] 可讓使用者在 Outlook 中將 Teams 交談的複本共用至電子郵件，而不需要離開 Teams。 如果使用者需要與其直接小組或甚至貴組織外部的使用者共用交談或狀態更新，這項功能就很實用。 移至 Teams 中的交談頂端，選取 **...[更多選項]**，然後選取 **[共用至 Outlook]**。  若要深入瞭解，請參閱 [從 Teams 共用至 Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![顯示 Teams 中 [共用至 Outlook] 功能的螢幕擷取畫面。](media/share-to-outlook.png)

若要使用此功能，使用者必須開啟Outlook 網頁版。 如果關閉Outlook 網頁版，使用者的 Teams 中就不會顯示 [**共用至 Outlook**] 選項。 如需如何開啟和關閉Outlook 網頁版的步驟，請參閱[啟用或停用信箱Outlook 網頁版](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)。

## <a name="actionable-activity-emails"></a>可採取動作的活動電子郵件

使用者會自動收到可採取動作的未接活動電子郵件，協助他們在 Teams 中掌握未接的交談。 錯過的活動電子郵件會顯示交談中的最新回復，包括未接郵件後傳送的訊息，使用者可以按一下 [ **回復** ] 直接從 Outlook 內回復。 若要深入瞭解，請參閱 [回復 Outlook 中未接的活動電子郵件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Mac 版 Outlook或某些舊版 Windows 版 Outlook 不支援此功能。 如需詳細資訊，請參閱[Outlook 和Office 365群組中的可採取動作的郵件](/outlook/actionable-messages/)。

![顯示未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email.png)

![顯示如何回復未接活動電子郵件的螢幕擷取畫面。](media/missed-activity-email-reply.png)

您可以搭配 **SmtpActionableMessagesEnabled** 參數使用 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 來關閉可採取動作的電子郵件。 根據預設， **SmtpActionableMessagesEnabled** 參數設為 **True**。 將參數設為 **False** 可關閉Office 365的電子郵件訊息。 對於 Teams 使用者，這表示在未接的活動電子郵件中無法使用直接在 Outlook 中回復 **的回復選項** 。 錯過的活動電子郵件反而包含 [ **在 Teams 中回復** ] 選項，讓使用者在 Teams 中回復。

另請參閱[Outlook 和 Office 365 群組中的可採取動作的郵件](/outlook/actionable-messages/)。
