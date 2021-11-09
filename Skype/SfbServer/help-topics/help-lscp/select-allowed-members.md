---
title: 選取允許的成員
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。 Persistent Chat 管理員可以定義每個類別的 AllowedMembers 和建立者，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 Persistent Chat 系統管理員可以使用控制台或 Windows PowerShell Cmdlet 來建立及管理類別。
ms.openlocfilehash: e08673c6b2d29e24aabef0d56ddbbb19ef776f35
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840215"
---
# <a name="select-allowed-members"></a>選取允許的成員

正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。 Persistent Chat 管理員可以定義每個類別的 **AllowedMembers** 和建立 **者** ，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 Persistent Chat 系統管理員可以使用控制台或 Windows PowerShell Cmdlet 來建立及管理類別。

使用者、組織單位 (Ou) ，以及識別為類別建立者的使用者群組，都是唯一可以在類別中建立聊天室的個人和群組。 在建立類別之後，他們可以從類別的 **AllowedMembers** 清單選擇使用者、ou 和使用者群組做為聊天室管理員和成員，以管理及參與會議室。

## <a name="tasks-that-you-can-perform"></a>您可以執行的工作

您可以在「 **選取允許的成員** 」頁面上執行下列工作：

- [設定類別](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [新的持久聊天伺服器功能](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

如需使用商務用 Skype Server 控制台可執行之不同程式的詳細資訊，請參閱[Manage 商務用 Skype Server 2015](../../manage/manage.md)。

## <a name="to-configure-categories-for-chat-rooms"></a>設定聊天室的類別

在 [ **成員資格**] 的 [ **允許的成員** ] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。


如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 。 如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in Operations 檔中。

## <a name="see-also"></a>另請參閱

[瞭解 Persistent Chat 成員資格](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)