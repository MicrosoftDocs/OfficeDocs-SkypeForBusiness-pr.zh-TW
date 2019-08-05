---
title: 通話品質儀表板 (CQD) 的使用者設定服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '摘要: 瞭解使用者設定服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186847"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>通話品質儀表板 (CQD) 的使用者設定服務
 
**摘要:** 瞭解 [使用者設定] 服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。
  
## <a name="user-settings-service"></a>使用者設定服務

使用者設定是一些鍵值對, 應用程式可以用來儲存中繼資料以進行各種用途, 包括自訂每個使用者的應用程式行為。 每個使用者都會收到使用者設定的儲存空間。 只有擁有者可以新增、修改及移除使用者設定。
  
 **全域設定**
  
全域設定是系統使用者所擁有的使用者設定, 且所有使用者都可以以唯讀方式存取它們。 全域設定是常數: 它們是在建立儲存庫期間建立的, 而且永遠不會變更。
  
每個使用者都可以使用相同的索引鍵來建立使用者設定, 以覆寫全域設定。 當應用程式要求有效的使用者設定時, API 會傳回一組與使用者設定合併的全域設定, 每個使用者設定都會取代各個全域設定 (如果鍵相同)。 API 也可以只傳回使用者設定, 讓應用程式可以找出哪些設定會被重寫。 
  
其餘的作業包括在下表中。

|**一道**|**說明**|
|:-----|:-----|
|[取得使用者設定](get-user-settings.md) <br/> |[取得使用者設定] 會傳回指定使用者的設定清單。  <br/> |
|[取得使用者設定](get-user-setting.md) <br/> |[取得使用者] 設定會傳回單一使用者設定。  <br/> |
   

