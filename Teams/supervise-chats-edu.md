---
title: 使用受監督的聊天
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解 Microsoft Teams 會議中受監督的聊天。
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5cee0678e48a0fcdeb340b90e95981c3b1759f83
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271468"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Microsoft Teams 中受監督的聊天

教育機構為學生提供安全且健康的網際空間。 網際空間包括電子郵件、線上會議和通話，以及 Teams 中的訊息中心。 為防止不當傳訊行為，許多學校停用 Teams 中的私人聊天。 很抱歉，停用聊天也會阻礙教師私下與學生接觸以進行個人化學習的機會。 在聊天停用的情況下，學生不想在班級團隊中公開張貼訊息時，無法連絡教師。

受監督的聊天可讓指定的授課者開始與學生聊天，並禁止學生開始新的聊天，除非有適當的授課者出席。 啟用聊天監督時，監督者將無法離開聊天，而且不允許其他參與者移除，以確保有適當監督與學生有關的聊天。

這些限制只會套用至在完全啟用受監督的聊天之後所建立的新私人聊天。 這些專案不適用於現有的私人聊天、會議聊天或頻道。 若要深入瞭解會議聊天、頻道安全及保護學生安全的最佳做法，請檢視 [使用 Teams 時保護學生的安全](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)。

> [!Note]
> 受監督的聊天會保護在強制執行此功能後建立的新聊天。  它無法保護現有的聊天。

## <a name="review-use-cases-for-supervised-chats"></a>檢閱受監督聊天的使用案例

下列範例說明何時需要受監督的聊天。

- 當學生不習慣共用或公開提問時，與授課者進行 1.1 後續追蹤。

- 授課者向學生詢問作業、最近的班級互動 (或缺少) 或其他主題。

- 授課者監視的學生群組討論。

- 允許非授課教職員在受監督的環境中與學生聊天。

## <a name="enable-supervised-chat"></a>啟用受監督的聊天

> [!Note]
> 在啟用機構的聊天前，請先確定您已設定聊天許可權角色和角色型聊天許可權原則，以避免不想要的學生存取不受監督的聊天。

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>定義環境中每個使用者的聊天許可權角色

若要讓受監督的聊天如預期般運作，您環境中的每個使用者都必須獲派正確的聊天許可權角色。 使用者可以指派三種角色：

- *完全許可權* – 這個角色很適合應具有學生和其他教職員成員完整存取權的授課者。 他們可以與您環境中的任何使用者開始聊天。 擁有完整許可權的使用者應監督他們參與的聊天。 他們無法離開或從他們所開始的聊天中移除，也無法從同盟租使用者中監督的聊天中移除。

- *許可權有限* – 此角色非常適合應僅具有學生監督許可權且能完整存取其他教職員和授課者之教職員成員。 他們可以與任何完整或有限的使用者開始聊天，但無法與受限制的使用者開始聊天。 如果具有完整許可權的使用者開始與受限制的使用者聊天，則可以將有限的使用者帶入交談。 發生此存取是因為具有完整許可權的使用者會出席，以監督受限制使用者之間的共同作業。

- *受限制的許可權* – 這個角色非常適合需要受監督的學生。 他們只能與擁有完整許可權的使用者開始聊天。 他們可以參與具有完整許可權的使用者開始的任何交談，然後邀請他們加入。 在同盟聊天案例中，只有擁有受限制使用者租使用者之完整許可權的使用者才能將受限制的使用者新增至聊天。

若要設定使用者的聊天許可權角色，請使用 Teams 系統管理入口網站中訊息原則選項內的 **聊天** 許可權 **角色** 原則。 您可以使用 PowerShell 來使用 ChatPermissionRole 原則以及 [完整]、[有限] 或 [受限制] 值來定義角色。 這項原則在 CsTeamsMessagingPolicy 底下。

若要深入瞭解設定。 Teams 原則會參閱適用于教育的 Teams 原則和原則套件，以及指派原則給大量使用者指南。

您無法將角色指派給租使用者中的來賓。 來賓會獲派有限的角色。

### <a name="allow-supervised-chat"></a>允許受監督的聊天

您的租使用者預設會停用受監督的聊天。 設定使用者的聊天許可權角色之後，您可以移至 **Teams Teams** &gt; **設定** 並將 **角色型聊天權** 限原則設定為 [開啟]，在租使用者內啟用受監督的聊天 *。* 您也可以使用 PowerShell 將 AllowRoleBasedChatPermissions 設為 True 來啟用受監督的聊天。 此 Cmdlet 位於 CsTeamsClientConfiguration 底下。

租使用者中的所有使用者都必須啟用受監督的聊天功能，而且您只能為部分使用者啟用。

### <a name="enable-chat"></a>啟用聊天

使用 Teams 系統管理中心提供的現有聊天原則，為所有使用者啟用聊天功能。

## <a name="maintain-supervised-chats"></a>維護受監督的聊天

一開始啟用受監督的聊天之後，您必須執行一些動作，以確保您環境中的聊天保持受到監督：

- 指派適當的角色給任何加入您租使用者的新使用者。 根據預設，系統會指派使用者受限制的角色。

- 如果擁有完整許可權的使用者離開或從租使用者移除，他們監督的聊天會自動保留。 在您移除原始使用者之前，請確定將具有完整許可權的另一個使用者新增至這些交談，讓聊天能夠持續受到監督。 移除原始監督者之後，就無法將新的參與者新增至交談，但目前的參與者可以繼續通訊。

## <a name="related-topics"></a>相關主題

[Teams 教育版受監督的聊天](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
