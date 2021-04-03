---
title: 使用受監督的聊天
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解 Microsoft Teams 會議中受監督的聊天。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506676"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Microsoft Teams 中的受監督聊天

教育機構為學生提供安全且健康的網際空間。 網際空間包括 Teams 中的電子郵件、線上會議和通話，以及傳訊。 為了防止不當的訊息行為，許多學校停用 Teams 中的私人聊天。 很抱歉，停用聊天也會讓教師無法私下與學生聯繫，進行個人化學習。 當學生不想在班級團隊中公開張貼訊息時，他們無法與教師聯繫。

監督式聊天可讓指定的教育者與學生開始聊天，並阻止學生開始新的聊天，除非有適當的教師出席。 啟用聊天監督時，主管不得離開聊天，而不允許其他參與者移除聊天，以確保與學生有關的聊天受到適當的監督。

這些限制僅適用于監督聊天完全啟用後所建立的新私人聊天。 它們不適用於現有的私人聊天、會議聊天或頻道。 若要深入瞭解會議聊天、頻道安全及確保學生安全的最佳作法，請觀看使用 Teams 時保護[學生安全。](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> 受監督的聊天可保護在強制執行功能後建立的新聊天。  它無法保護現有的聊天。

## <a name="review-use-cases-for-supervised-chats"></a>審查受監督聊天的使用案例

下列範例說明何時需要監督聊天。

- 當學生不習慣公開分享或提出問題時，與教育者進行 1.1 追蹤。

- 教師會以 1.1 方式向學生說明作業、最近的班級互動 (或缺少) 或其他主題。

- 由教師監控的學生群組討論。

- 允許非教職員在受監督的環境中與學生聊天。

## <a name="enable-supervised-chat"></a>啟用有監督的聊天

> [!Note]
> 在您為機構啟用聊天之前，請確定您設定聊天許可權角色和角色型聊天許可權政策，以避免學生對未監督的聊天進行不必要的存取。

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>為環境中每個使用者定義聊天許可權角色

若要讓受監督的聊天如預期一樣工作，您環境中每個使用者必須獲得正確的聊天許可權角色。 使用者可以指派三個角色：

- *完整許可權* – 此角色適用于應能完整存取學生和其他教職員成員的教育工作者。 他們可以開始與環境中的任何使用者聊天。 擁有完整許可權的使用者應監督他們參與的聊天。 他們無法離開或移除他們啟動的聊天，或他們在聯盟租使用者中監督的聊天。

- *有限許可權* – 此角色適用于只有學生受監督存取權且能完全存取其他教職員和教育工作者的員工成員。 他們可以開始與任何完整或受限制的使用者聊天，但無法與受限制的使用者開始聊天。 如果擁有完整許可權的使用者開始與受限制的使用者聊天，可以將受限制的使用者加入交談。 發生此存取是因為有完整許可權的使用者存在，以監督受限制和受限制的使用者之間的共同合作。

- *限制許可權* – 此角色適用于需要受監管的學生。 他們只能與擁有完整許可權的使用者開始聊天。 他們可以參與擁有完整許可權的使用者邀請他們參與的任何交談。 在聯合聊天案例中，限制使用者只能由擁有來自受限制使用者租使用者之完整許可權的使用者新加入聊天。

若要設定使用者的聊天許可權角色，請使用 Teams系統管理入口網站中的訊息策略選項中找到的聊天許可權角色策略。 您可以使用 PowerShell 使用 ChatPermissionRole 策略定義角色，其值為完整、限制或限制。 此政策位於 CsTeamsMessagingPolicy 下。

若要深入瞭解設定。 Teams 策略請參閱適用于教育的 Teams 策略和策略套件，以及將策略指派給大量使用者指南。

角色無法指派給租使用者中的來賓。 來賓會指派有限角色。

### <a name="allow-supervised-chat"></a>允許有監督的聊天

您的租使用者預設會停用監督聊天。 為使用者設定聊天許可權角色之後，您可以進入全組織設定Teams 設定，將角色型聊天權限原則設定為 &gt; **** *On，* 在租使用者中啟用監督聊天。 您也可以將 AllowRoleBasedChatPermissions 設定為 True，使用 PowerShell 啟用監督聊天。 此 Cmdlet 位於 CsTeamsClientConfiguration 下。

必須針對租使用者中的所有使用者啟用監控聊天，而且無法只針對部分使用者啟用。

### <a name="enable-chat"></a>啟用聊天

使用 Teams 系統管理中心提供的現有聊天政策，為所有使用者啟用聊天。

## <a name="maintain-supervised-chats"></a>維護受監督的聊天

初始啟用監督聊天后，您必須執行一些操作，以確保您環境中聊天維持受監督狀態：

- 指派適當的角色給加入您租使用者的任何新使用者。 根據預設，使用者會指派受限制的角色。

- 如果擁有完整許可權的使用者離開或從租使用者中移除，則他們監督的聊天會保留為無人看管。 在您移除原始使用者之前，請確保其他擁有完整許可權的使用者已新加入這些交談中，這樣聊天才能繼續受到監督。 一旦移除原始主管，新的參與者無法新加入交談，但目前的參與者可以繼續通訊。

## <a name="related-topics"></a>相關主題

[在教育用 Teams 進行有監督的聊天](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
