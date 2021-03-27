---
title: Teams 和 Outlook 電子郵件整合
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 瞭解 Teams 和 Outlook 電子郵件整合功能，包括讓使用者在 Outlook 電子郵件之間共用資訊的功能，以及 Teams 中的聊天或頻道交談。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc1ce6eec084dfe2f4bb736f018352e0eb0e2c88
ms.sourcegitcommit: e55d1623e686db2b183e02052bfe10a0269abb5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51397556"
---
# <a name="teams-and-outlook-email-integration"></a>Teams 和 Outlook 電子郵件整合

Microsoft Teams 包含的功能，可讓使用者輕鬆在 Outlook 中的電子郵件之間共用資訊，以及 Teams 中的聊天或頻道交談，並隨時瞭解未接的交談。 本文提供這些功能和適用之系統管理控制項概觀。

## <a name="share-to-outlook"></a>共用至 Outlook

**共用至 Outlook** 可讓使用者在 Outlook 中將 Teams 交談的一份副本共用至電子郵件，而不需要離開 Teams。 如果使用者需要與直系小組或甚至貴組織以外的使用者共用交談或狀態更新，這項功能非常實用。 在 Teams 中，前往交談的頂端，選取 **2010 年 12 月 12** 日更多選項，然後選取共用 **至 Outlook**。  若要深入瞭解，請參閱 [從 Teams 共用至 Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![在 Teams 中顯示共用至 Outlook 功能之螢幕擷取畫面](media/share-to-outlook.png)

若要使用這項功能，使用者必須開啟 Outlook 網頁。 如果 Outlook 網頁化已關閉，使用者的 Teams 中不會顯示共用至 **Outlook** 選項。 若要瞭解如何開啟和關閉 Outlook 網頁流覽的步驟，請參閱啟用或停用[信箱的 Outlook 網頁。](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>可採取行動的活動電子郵件

使用者會自動收到可採取動作的未接活動電子郵件，協助他們趕上 Teams 中未接的交談。 錯過的活動電子郵件會顯示來自交談的最新回復，包括未接郵件後所寄的郵件，使用者可以按一下 **[回復** 以直接從 Outlook 內回復。 若要深入瞭解，請參閱回復 Outlook 中錯過 [的活動電子郵件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Mac 版 Outlook 或某些舊版 Windows 版 Outlook 不支援此功能。 詳細資訊，請參閱 [Outlook 和 Office 365](/outlook/actionable-messages/)群組中的可採取動作的郵件。

![顯示未接活動電子郵件的螢幕擷取畫面](media/missed-activity-email.png)

![顯示如何回復未接活動電子郵件的螢幕擷取畫面](media/missed-activity-email-reply.png)

您可以將 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 與 **SmtpActionableMessagesEnabled 參數** 一起使用，以關閉可採取動作的電子郵件。 根據預設 **，SmtpActionableMessagesEnabled 參數** 會設為 **true。** 將參數設定為 **False** 會關閉 Office 365 上可採取動作的電子郵件訊息。 對於 Teams 使用者，這表示未接活動電子郵件中無法直接在 Outlook 中回復的回復選項。 相反地，錯過的活動電子郵件會 **包含一個** Teams 中的回復選項，讓使用者在 Teams 中回復。

另請參閱 [Outlook 和 Office 365 群組中的可動作郵件](https://docs.microsoft.com/outlook/actionable-messages/)。
