---
title: 常設聊天室增益集主要頁面
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 您可以使用 [Persistent Chat] 頁面的 [增益集] 區段，將 URLs 與 Persistent 聊天室產生關聯。 這些 URLs 會出現在交談擴充性窗格中的聊天室中的用戶端。 管理員必須將增益集加入至已註冊的增益集清單中，且聊天室管理員/創作者必須與其中一個已註冊的增益集產生關聯，使用者才能在用戶端看到此升級。
ms.openlocfilehash: fd24de819167bc766009fb6e56a06c377bba076b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841495"
---
# <a name="persistent-chat-add-in-main-page"></a>常設聊天室增益集主要頁面

您可以使用 [ **Persistent chat** ] 頁面的 [**增益集**] 區段，將 URLs 與 persistent 聊天室產生關聯。 這些 URLs 會出現在交談擴充性窗格中的聊天室中的用戶端。 管理員必須將增益集加入至已註冊的增益集清單中，且聊天室管理員/創作者必須與其中一個已註冊的增益集產生關聯，使用者才能在用戶端看到此升級。

增益集可擴充聊天室體驗。 一般增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號傳送至聊天室時進行截獲，並在 [擴充性] 窗格中顯示 stock 記錄。 其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。

若要建立持久聊天室的增益集，請參閱[在商務用 Skype Server 2015 中設定 persistent 聊天室的增益集](../../manage/persistent-chat/configure-add-ins.md)。 如果您是 Persistent Chat 系統管理員，可以使用 [控制台] 或 Windows PowerShell Cmdlet 來建立增益集。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「增益集」頁面上執行下列工作：

- [在商務用 Skype Server 2015 中設定 Persistent 聊天室的增益集](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>設定聊天室的增益集

下列清單說明頁面上的功能表、命令、欄位及內容。

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需您可以用來啟動控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 系統管理工具](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。

3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [增益集]。

    若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。

4. 在 **[增益集]** 頁面上，按一下 **[新增]**。

5. 在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。

6. 在 **[新增增益集]** 中，執行下列動作：

   - 在 **[名稱]** 中，指定新增益集的名稱。

   - 在 **[URL]** 中，指定要與增益集建立關聯的 URL。URL 限於 http 和 https 通訊協定。

7. 按一下 **[認可]**。

## <a name="see-also"></a>另請參閱

如需 Persistent chat server 功能及功能的詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃 persistent chat server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 Skype Server 2015 中部署 persistent chat](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)server，以及[在商務用 Skype Server 2015 中管理 persistent chat server](../../manage/persistent-chat/persistent-chat.md)。