---
title: 針對非教育租使用者使用受監督的聊天
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解Microsoft Teams 會議中非教育租使用者受監督的聊天。
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc7ddf23b600ec2a7f4d4f02c2328587627572fc
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198285"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>非教育租使用者受監督的聊天

受監督的聊天功能可讓指定的監督者與組織中的任何人開始聊天，並禁止受限制的使用者開始新聊天，除非有適當的監督者出席。 啟用聊天監督時，監督者將無法離開聊天，而且不允許其他參與者移除，以確保包含受限制使用者的聊天受到適當監督。

這些限制只會套用至在完全啟用受監督的聊天之後所建立的新私人聊天。 這些專案不適用於現有的私人聊天、會議聊天或頻道。

受監督的聊天是針對教育機構的需求量身訂做，但也適用于非教育租使用者。

> [!NOTE]
> 受監督的聊天會保護在強制執行此功能後建立的新聊天。 它無法保護現有的聊天。

## <a name="enable-supervised-chat"></a>啟用受監督的聊天

> [!NOTE]
> 在為您的機構啟用聊天之前，請先確定您已設定聊天許可權角色和角色型聊天許可權原則，以避免不必要的限制使用者存取不受監督的聊天。

**定義環境中每個使用者的聊天許可權角色**：

若要讓受監督的聊天如預期般運作，您環境中的每個使用者都必須獲派正確的聊天許可權角色。 使用者可以指派三種角色：

- 完整許可權：這個角色應該指派給您環境中的聊天監督者。 他們可以與您環境中的任何使用者開始聊天。 擁有完整許可權的使用者應監督他們參與的聊天。 他們無法離開或從他們所開始的聊天中移除，也無法從同盟租使用者中監督的聊天中移除。

- 有限許可權：此角色最適合只應具有受限制使用者之受監督存取權的教職員成員。 他們可以與任何完整或有限的使用者開始聊天，但無法與受限制的使用者開始聊天。 如果具有完整許可權的使用者開始與受限制的使用者聊天，則可以將有限的使用者帶入交談。 發生此存取是因為具有完整許可權的使用者會出席，以監督受限制使用者之間的共同作業。

- 受限制的許可權：這個角色非常適合需要受到監督的使用者。 他們只能與擁有完整許可權的使用者開始聊天。 他們可以參與具有完整許可權的使用者邀請他們進行的任何交談。 在同盟聊天案例中，只有擁有受限制使用者租使用者之完整許可權的使用者才能將受限制的使用者新增至聊天。

若要設定使用者的聊天許可權角色，請使用 Teams 系統管理入口網站中訊息原則選項內的聊天許可權 **角色** 原則。 您可以使用 PowerShell 來使用 ChatPermissionRole 原則以及 [完整]、[有限] 或 [受限制] 值來定義角色。 這項原則在 [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)底下。

您無法將角色指派給租使用者中的來賓。 來賓會獲派有限的角色。

## <a name="allow-supervised-chat"></a>允許受監督的聊天

您的租使用者預設會停用受監督的聊天。 設定使用者的聊天許可權角色之後，您可以移至 **[Teams Teams** \> **設定** ] 並將 [ **角色型聊天** ] 許可權原則設定為 [ **開** 啟]，在租使用者內啟用受監督的聊天。 您也可以使用 PowerShell 將 AllowRoleBasedChatPermissions 設為 True 來啟用受監督的聊天。 此 Cmdlet 位於 [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)底下。

租使用者中的所有使用者都必須啟用受監督的聊天功能，而且您只能為部分使用者啟用。

**啟用聊天**：

使用 Teams 系統管理中心提供的現有聊天原則，為所有使用者啟用聊天功能。

**維護受監督的聊天**：

一開始啟用受監督的聊天之後，您必須執行一些動作，以確保您環境中的聊天保持受到監督：

- 指派適當的角色給任何加入您租使用者的新使用者。 根據預設，系統會指派使用者受限制的角色。

- 如果擁有完整許可權的使用者離開或從租使用者移除，他們監督的聊天會自動保留。 在您移除原始使用者之前，請確定將具有完整許可權的另一個使用者新增至這些交談，讓聊天能夠持續受到監督。 移除原始監督者之後，就無法將新的參與者新增至交談，但目前的參與者可以繼續通訊。
