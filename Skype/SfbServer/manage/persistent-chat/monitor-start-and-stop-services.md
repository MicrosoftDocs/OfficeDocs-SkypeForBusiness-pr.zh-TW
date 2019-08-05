---
title: 監控、啟動和停止常設聊天室服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中啟動、停止及監視持續聊天服務。'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194064"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>監控、啟動和停止常設聊天室服務
 
**摘要:** 瞭解如何在商務用 Skype Server 2015 中啟動、停止及監視持續聊天服務。
  
持續式聊天服務和持續性聊天規範服務是商務用 Skype Server 拓撲的一部分, 因此可使用下列 Cmdlet 加以監視、停止及啟動:
  
|||
|:-----|:-----|
|CsWindowsService  <br/> |傳回作為 Windows 服務執行之商務用 Skype Server 2015 元件的詳細資訊。  <br/> |
|開始-CsWindowsService  <br/> |啟動服務。  <br/> |
|停止 CsWindowsService  <br/> |停止服務。  <br/> |
   
> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 

如需如何使用 Cmdlet 的詳細資訊, 請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

