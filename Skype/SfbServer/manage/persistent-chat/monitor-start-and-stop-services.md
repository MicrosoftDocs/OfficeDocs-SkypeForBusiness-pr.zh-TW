---
title: 在商務用 Skype Server 2015 中監控、啟動和停止持續性聊天服務
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
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要：瞭解如何在商務用 Skype Server 2015 中開始、停止和監視 Persistent 聊天服務。
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814133"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中監控、啟動和停止持續性聊天服務
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中開始、停止和監視 Persistent 聊天服務。
  
Persistent Chat service 和 Persistent Chat 服務規範服務是商務用 Skype 伺服器拓撲的一部分，因此可使用下列 Cmdlet 進行監控、停止和啟動：
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |傳回以 Windows 服務執行之商務用 Skype Server 2015 元件的詳細資訊。  <br/> |
|start-CsWindowsService  <br/> |啟動服務。  <br/> |
|stop-CsWindowsService  <br/> |停止服務。  <br/> |
   
> [!NOTE]
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。 

如需如何使用 Cmdlet 的詳細資訊，請參閱 [商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

