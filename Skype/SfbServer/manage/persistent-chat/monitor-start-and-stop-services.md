---
title: 在商務用 Skype Server 2015 中監控、啟動和停止 Persistent 聊天服務
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
ms.openlocfilehash: c541964659ceec36209c4ea262d047cf116c35e444354f6e450b7b684e4992ec
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590717"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中監控、啟動和停止 Persistent 聊天服務
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中開始、停止和監視 Persistent Chat service。
  
persistent chat service 和 persistent chat 服務規範服務是商務用 Skype Server 拓撲的一部分，因此可使用下列 Cmdlet 進行監控、停止和啟動：
  
|指令程式|函數|
|:-----|:-----|
|get-CsWindowsService  <br/> |傳回 Windows 服務執行之商務用 Skype Server 2015 元件的詳細資訊。  <br/> |
|start-CsWindowsService  <br/> |啟動服務。  <br/> |
|stop-CsWindowsService  <br/> |停止服務。  <br/> |
   
> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

如需如何使用 Cmdlet 的詳細資訊，請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

