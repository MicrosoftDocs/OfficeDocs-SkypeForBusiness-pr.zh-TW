---
title: '通話品質儀表板的使用者設定服務 (CQD) '
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要：瞭解使用者設定服務，它是「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 81abbc31a82fc696a5bcb45faf4120b71fc26f74
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856580"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>通話品質儀表板的使用者設定服務 (CQD) 
 
**摘要：** 瞭解使用者設定服務，它是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。
  
## <a name="user-settings-service"></a>使用者設定服務

使用者設定是機碼組，可讓應用程式用來儲存中繼資料，以用於不同的目的，包括自訂每個使用者的應用程式行為。 每個使用者都會收到使用者設定的儲存體。 只有擁有者可以新增、修改和移除使用者設定。
  
 **全域設定**
  
全域設定是系統使用者所擁有的使用者設定，而且所有使用者都具有唯讀的存取權。 全域設定為常數：它們是在建立存放庫期間建立，永遠不會變更。
  
每一位使用者都可以建立具有相同金鑰的使用者設定，以覆寫全域設定。 當應用程式要求有效的使用者設定時，API 會傳回一組通用設定與使用者設定合併，每個使用者設定會取代個別的通用設定（如果機碼相同）。 API 也可以只傳回使用者設定，讓應用程式可以找出已覆寫的設定。 
  
其餘的作業包含在下表中。

|**作業**|**描述**|
|:-----|:-----|
|[取得使用者設定](get-user-settings.md) <br/> |取得使用者設定會傳回指定使用者的設定清單。  <br/> |
|[取得使用者設定](get-user-setting.md) <br/> |取得使用者設定會傳回單一使用者設定。  <br/> |
   

