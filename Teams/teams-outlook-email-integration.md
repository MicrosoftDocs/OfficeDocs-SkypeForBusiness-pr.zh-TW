---
title: 團隊和 Outlook 電子郵件整合
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 瞭解團隊和 Outlook 電子郵件整合功能，包括可讓使用者在 Outlook 中的電子郵件之間共用資訊，或在團隊中進行頻道交談的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429439"
---
# <a name="teams-and-outlook-email-integration"></a>團隊和 Outlook 電子郵件整合

Microsoft 團隊包含的功能可讓貴組織中的使用者輕鬆地在 Outlook 和小組中的電子郵件之間共用資訊，以及隨時掌握未接的交談。 本文將為您概述這些功能，以及適用的管理控制項。

## <a name="share-to-outlook"></a>共用至 Outlook

[**共用至 outlook** ] 可讓使用者在 Outlook 中與電子郵件共用小組交談複本，而不需離開小組。 如果使用者需要與直屬小組以外的使用者共用交談或狀態更新，這項功能很實用。 移至 [團隊] 中的交談頂端，選取 [ **̇̇̇其他選項**]，然後選取 [ **共用至 Outlook**]。  若要深入瞭解，請參閱 [從團隊共用至 Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![螢幕擷取畫面顯示團隊中的 [共用至 Outlook] 功能](media/share-to-outlook.png)

若要使用此功能，您必須為使用者開啟 Outlook 網頁版。 如果 Outlook 網頁版已關閉，就不會在使用者的小組中顯示 [ **共用至 outlook** ] 選項。 如需如何開啟和關閉 Outlook 網頁版的相關步驟，請參閱 [啟用或停用 outlook 網頁](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)版的信箱。

## <a name="actionable-activity-emails"></a>可操作的活動電子郵件

使用者會自動取得可操作的未接活動電子郵件，協助他們在團隊中找出未接的交談。 未接的活動電子郵件會顯示交談中的最新回復，包括錯過的郵件之後所傳送的郵件，以及使用者可以按一下 [ **回復** ]，直接在 Outlook 中回復。 若要深入瞭解，請參閱 [從 Outlook 回復未接的活動電子郵件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Mac 版 Outlook 或某些舊版 Outlook for Windows 不支援此功能。 如需詳細資訊，請參閱 [Outlook 和 Office 365 群組中](https://docs.microsoft.com/outlook/actionable-messages/)的可採取動作的郵件。

![顯示未接的活動電子郵件的螢幕擷取畫面](media/missed-activity-email.png)

![顯示如何回復未接的活動電子郵件的螢幕擷取畫面](media/missed-activity-email-reply.png)

您可以將 [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 與 **SmtpActionableMessagesEnabled** 參數搭配使用，以關閉可操作的電子郵件。 根據預設， **SmtpActionableMessagesEnabled** 參數會設定為 **true**。 將參數設定為 **false** ，即可在 Office 365 中關閉可操作的電子郵件訊息。 針對團隊使用者而言，這表示未接的活動電子郵件中不提供直接在 Outlook 中回應的 **回復** 選項。 相反地，未接的活動電子郵件包括 [ **在** 團隊中回復使用者] 選項。
