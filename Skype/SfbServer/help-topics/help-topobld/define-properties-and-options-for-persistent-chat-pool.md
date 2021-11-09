---
title: 定義常設聊天室集區的屬性與選項
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 您可以透過定義下列內容，來設定 Persistent Chat Server 或 Persistent Chat Server 集區的選項：
ms.openlocfilehash: 72afab6d9c74f2347bd14a4d597cf82525c11b48
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851307"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>定義常設聊天室集區的屬性與選項
 
您可以透過定義下列內容，來設定 Persistent Chat Server 或 Persistent Chat Server 集區的選項：
  
 **Persistent chat 集區的顯示名稱**：必要屬性，可定義此 Persistent chat Server 或 Persistent chat server 集區所顯示的使用者易記名稱。
  
 **Persistent chat port**：一個必要的屬性，會定義此 Persistent chat Server 或 Persistent chat server 集區將接聽的埠號碼。
  
 **啟用規範**：如果您計畫要部署及執行選用的持續性聊天規範功能和資料庫，請選取此核取方塊。
  
 **使用 backup SQL Server 儲存以啟用** 嚴重損壞修復：如果您計畫要部署及執行 Persistent SQL Server Chat 的嚴重損壞復原，請從另一個 SQL Server 的儲存區設定備份組內，，選取此核取方塊。 如需詳細資訊，請參閱[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。
  
> [!NOTE]
> 此選項僅適用于具有多部伺服器的集區。 
  
 **使用此集區作為 \<site that this server or pool is being configured in\> 網站的預設值**：如果這會是網站的預設 persistent Chat Server 或 persistent chat server 集區，請選取此核取方塊。 每個網站必須有一個預設的持久聊天伺服器或 pol。
  
> [!NOTE]
> 如果拓撲包含多個網站，也會顯示 [ **使用此集區作為所有網站的預設值** ] 核取方塊。
  
按 [上一步] 回到上一個集區定義對話方塊。
  
完成輸入此集區的選項之後，按 **[下一步]** 以繼續使用 Persistent Chat Server 集區定義。
  
按一下 [取消] 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]。
  
按一下 [說明] 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
