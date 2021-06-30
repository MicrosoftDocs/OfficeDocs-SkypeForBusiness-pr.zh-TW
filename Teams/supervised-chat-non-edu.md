---
title: 針對非教育性租使用者使用受監督的聊天
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
description: 瞭解如何在會議中為非教育性租使用者Microsoft Teams聊天。
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203723"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>非教育性租使用者受監督的聊天

監督式聊天可讓指定的主管與組織中任何人開始聊天，並禁止限制使用者開始新的聊天，除非有適當的主管出席。 啟用聊天監督時，主管不得離開聊天，而不允許其他參與者移除聊天，以確保與受限制使用者有關的聊天受到適當的監督。

這些限制僅適用于監督聊天完全啟用後所建立的新私人聊天。 它們不適用於現有的私人聊天、會議聊天或頻道。

監看聊天是專為教育機構的需求量身打造，但非教育租使用者也可以使用。

> [!NOTE]
> 受監督的聊天可保護在強制執行功能後建立的新聊天。 它無法保護現有的聊天。

## <a name="enable-supervised-chat"></a>啟用監督聊天

> [!NOTE]
> 在您為機構啟用聊天之前，請確定您設定聊天許可權角色和角色型聊天許可權政策，以避免使用者對未受監督的聊天進行不必要的限制存取。

**為環境中每個使用者定義聊天許可權角色**

若要讓受監督的聊天如預期一樣工作，您環境中每個使用者必須獲得正確的聊天許可權角色。 使用者可以指派三個角色：

- 完整許可權：此角色應指派給您環境中聊天主管。 他們可以開始與環境中的任何使用者聊天。 擁有完整許可權的使用者應監督他們參與的聊天。 他們無法離開或移除他們啟動的聊天，或他們在聯盟租使用者中監督的聊天。

- 限制許可權：此角色適合只有受監督存取受限制使用者的員工成員。 他們可以開始與任何完整或受限制的使用者聊天，但無法與受限制的使用者開始聊天。 如果擁有完整許可權的使用者開始與受限制的使用者聊天，可以將受限制的使用者加入交談。 發生此存取是因為有完整許可權的使用者存在，以監督受限制和受限制的使用者之間的共同合作。

- 限制許可權：此角色非常適合需要受監管的使用者。 他們只能與擁有完整許可權的使用者開始聊天。 他們可以參與擁有完整許可權的使用者邀請他們進行的任何交談。 在聯合聊天案例中，限制使用者只能由擁有來自受限制使用者租使用者之完整許可權的使用者新加入聊天。

若要設定使用者的聊天許可權角色，請使用系統管理入口網站中的訊息Teams角色策略。 您可以使用 PowerShell 使用 ChatPermissionRole 策略定義角色，其值為完整、限制或限制。 此政策位於 [CsTeamsMessagingPolicy 下](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。

無法將角色指派給租使用者中的來賓。 來賓會指派有限角色。

## <a name="allow-supervised-chat"></a>允許有監督的聊天

您的租使用者預設會停用監督聊天。 為使用者設定聊天許可權角色之後，您可以進入全組織設定 Teams 設定，將角色型聊天權限原則設定為  >  **On，** 在租使用者中啟用監督聊天。  您也可以將 AllowRoleBasedChatPermissions 設定為 True，使用 PowerShell 啟用監督聊天。 此 Cmdlet 位於 [CsTeamsClientConfiguration 下](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)。

必須針對租使用者中的所有使用者啟用受監督的聊天，而且只能為部分使用者啟用。

**啟用聊天**

使用系統管理中心提供的現有聊天Teams聊天。

**維護受監督的聊天**

初始啟用監督聊天后，您必須執行一些操作，以確保您環境中聊天維持受監督狀態：

- 指派適當的角色給加入您租使用者的任何新使用者。 根據預設，使用者會指派受限制的角色。

- 如果擁有完整許可權的使用者離開或從租使用者中移除，則他們監督的聊天會保留為無人看管。 在您移除原始使用者之前，請確保其他擁有完整許可權的使用者已新加入這些交談中，這樣聊天才能繼續受到監督。 一旦移除原始主管，新的參與者無法新加入交談，但目前的參與者可以繼續通訊。
