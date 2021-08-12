---
title: 在商務用 Skype Server 2015 中管理 Persistent Chat Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server。
ms.openlocfilehash: daaf1e681436853ebe8987c2d1058019d41b49096f37db6ae8cb9ed57eaa6420
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324212"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中管理 Persistent Chat Server
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server。
  
當您為組織設定 Persistent Chat Server 時，請在部署期間指定初始設定。 不過，在某些情況下，您可能想要變更您如何實施 Persistent Chat Server 支援。 例如，您可能需要為組織內的特定小組或群組設定 Persistent Chat Server 支援和控制項的方式不同。 本節提供協助您自訂 Persistent Chat Server 部署的資訊和程式。 如需您可以針對 Persistent chat server 設定之功能的詳細資訊，請參閱[商務用 Skype Server 2015 中的 Plan for persistent chat server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 如需部署 persistent chat server 的詳細資訊，請參閱[Deploy persistent chat server in 商務用 Skype Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 

> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來管理 Persistent Chat Server。 
  
若要使用控制台：
  
1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [ **Persistent Chat**]。
    
下表摘要說明可協助您管理 Persistent Chat Server 的 Windows PowerShell Cmdlet。 如需語法的詳細資訊（包括所有可用參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

|**指令程式**|**描述**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |會建立新類別  <br/> |
|Set-CsPersistentChatCategory  <br/> |設定現有類別的設定  <br/> |
|Get-CsPersistentChatCategory  <br/> |檢索類別的相關資訊  <br/> |
|Remove-CsPersistentChatCategory  <br/> |移除類別  <br/> |
|New-CsPersistentChatRoom  <br/> |建立新聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |設定現有聊天室的設定;將使用者和使用者群組指派給會議室  <br/> |
|Get-CsPersistentChatRoom  <br/> |檢索聊天室的相關資訊  <br/> |
|Clear-CsPersistentChatRoom  <br/> |清除聊天室或郵件  <br/> |
|Remove-CsPersistentChatRoom  <br/> |移除會議室  <br/> |
|Remove-CsPersistentChatMessage  <br/> |移除聊天室中的郵件  <br/> |
|New-CsPersistentChatAddin  <br/> |建立新的增益集  <br/> |
|Set-CsPersistentChatAddin  <br/> |設定現有增益集的設定  <br/> |
|Get-CsPersistentChatAddin  <br/> |檢索增益集的相關資訊  <br/> |
|Remove-CsPersistentChatAddin  <br/> |移除增益集  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |修改現有的符合性設定設定集合  <br/> |
|Export-CsPersistentChatData  <br/> |從 Persistent Chat 資料庫匯出資料  <br/> |
|Import-CsPersistentChatData  <br/> |匯入從前版本 Lync Server 匯出的資料  <br/> |
   

