---
title: 管理商務用 Skype Server 2015 中的常設聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器。
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817319"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>管理商務用 Skype Server 2015 中的常設聊天室
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器。
  
當您為您的組織設定持續聊天伺服器時，您會在部署期間指定初始配置。 不過，有時您可能會想要變更實現持久聊天伺服器支援的方式。 例如，您可能需要針對貴組織內的特定團隊或群組，將持續聊天伺服器支援與控制項設定成不同的方式。 本節提供的資訊和程式可協助您自訂持續聊天伺服器部署。 如需有關您可以針對持久聊天伺服器設定的功能和功能的詳細資訊，請參閱[在商務用 Skype server 2015 中規劃持久聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 如需部署持久聊天伺服器的詳細資訊，請參閱[在商務用 Skype server 2015 中部署持久聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來管理持久聊天伺服器。 
  
若要使用 [控制台]：
  
1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。
    
3. 在左側導覽列中，按一下 [**持續聊天**]。
    
下表摘要列出可用來協助您管理持久聊天伺服器的 Windows PowerShell Cmdlet。 如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

|**Cmdlet**|**說明**|
|:-----|:-----|
|新-CsPersistentChatCategory  <br/> |建立新類別  <br/> |
|Set-CsPersistentChatCategory  <br/> |配置現有類別的設定  <br/> |
|CsPersistentChatCategory  <br/> |檢索類別的相關資訊  <br/> |
|移除-CsPersistentChatCategory  <br/> |移除類別  <br/> |
|新-CsPersistentChatRoom  <br/> |建立新聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |配置現有聊天室的設定;將使用者和使用者群組指派給聊天室  <br/> |
|CsPersistentChatRoom  <br/> |檢索會議室的相關資訊  <br/> |
|Clear-CsPersistentChatRoom  <br/> |從聊天室清除聊天室或訊息  <br/> |
|移除-CsPersistentChatRoom  <br/> |移除聊天室  <br/> |
|移除-CsPersistentChatMessage  <br/> |移除聊天室中的郵件  <br/> |
|New-CsPersistentChatAddin  <br/> |建立新的增益集  <br/> |
|Set-CsPersistentChatAddin  <br/> |配置現有增益集的設定  <br/> |
|CsPersistentChatAddin  <br/> |檢索增益集的相關資訊  <br/> |
|移除-CsPersistentChatAddin  <br/> |移除增益集  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |修改現有的合規性配置設定集合  <br/> |
|Export-CsPersistentChatData  <br/> |從持久性聊天資料庫匯出資料  <br/> |
|匯入-CsPersistentChatData  <br/> |匯入從舊版 Lync Server 匯出的資料  <br/> |
   

