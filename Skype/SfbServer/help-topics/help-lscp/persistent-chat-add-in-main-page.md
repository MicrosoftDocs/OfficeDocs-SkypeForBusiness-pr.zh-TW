---
title: 常設聊天室增益集主要頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 您可以使用 [永久聊天] 頁面上的增益集區段，將 Url 與持續聊天室建立關聯。 這些 URL 會出現在交談擴充性窗格的聊天室之用戶端中。 系統管理員必須將增益集新增至已註冊的增益集清單中，而聊天室管理員/建立者必須先將聊天室與其中一個已註冊的增益集建立關聯，使用者才會在其用戶端中看到此升級。
ms.openlocfilehash: 60cf60c6f6691725161182c5cc4e5c2fd38a0576
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822576"
---
# <a name="persistent-chat-add-in-main-page"></a>常設聊天室增益集主要頁面

您可以使用 [**永久聊天**] 頁面上的**增益集**區段，將 url 與持續聊天室建立關聯。 這些 URL 會出現在交談擴充性窗格的聊天室之用戶端中。 系統管理員必須將增益集新增至已註冊的增益集清單中，而聊天室管理員/建立者必須先將聊天室與其中一個已註冊的增益集建立關聯，使用者才會在其用戶端中看到此升級。

增益集可擴充聊天室體驗。 典型的增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號張貼到聊天室時截獲，並在 [擴充性] 窗格中顯示股票歷程記錄。 其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。

若要建立持久聊天室的增益集，請參閱[在商務用 Skype Server 2015 中設定持久聊天室的增益集](../../manage/persistent-chat/configure-add-ins.md)。 如果您是永久性聊天管理員，您可以使用 [控制台] 或 [Windows PowerShell Cmdlet] 建立增益集。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [增益集]**** 頁面上執行下列工作：

- [設定常設聊天室的增益集](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>設定聊天室的增益集

下列清單說明頁面上的功能表、命令、欄位及內容。

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2. 從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。 如需各種控制台啟動方法的詳細資訊，請參閱〈[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)〉。

3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [增益集]****。

    如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。

4. 在 [增益集]**** 頁面上，按一下 [新增]****。

5. 在 [**選取服務**] 中，選取與您需要建立增益集的持續聊天伺服器池相對應的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。

6. 在 [新增增益集]**** 中，執行下列動作：

   - 在 [名稱]**** 中，指定新增益集的名稱。

   - 在 [URL]**** 中，指定要與增益集建立關聯的 URL。URL 限為 http 和 https 通訊協定。

7. 按一下 [認可]****。

## <a name="see-also"></a>另請參閱

如需持久聊天伺服器功能與功能的詳細資訊，請參閱[在商務用 Skype server 2015 中規劃持續聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 skype server 2015 中部署持續聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)，以及[在商務用 Skype Server 2015 中管理持續聊天伺服器](../../manage/persistent-chat/persistent-chat.md)。


