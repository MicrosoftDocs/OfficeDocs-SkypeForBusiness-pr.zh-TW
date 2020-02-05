---
title: 在商務用 Skype Server 中設定次要位置資訊服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 在商務用 Skype Server Enterprise Voice 中，針對 E9-1-1 設定次要位置來源（SLS）資料庫。
ms.openlocfilehash: 28168bb10017ccc1e56ce26bb5a88629f19aff41
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767076"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>在商務用 Skype Server 中設定次要位置資訊服務
 
在商務用 Skype Server Enterprise Voice 中，針對 E9-1-1 設定次要位置來源（SLS）資料庫。 
  
商務用 Skype 伺服器提供 web 服務介面，您可以用來將位置資訊服務指向次要位置來源（SLS）資料庫。 連接到 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。 如果已設定位置資料庫和次要位置資料庫，位置資訊服務會先查詢位置資料庫，如果沒有找到相符的專案，則會將位置要求從用戶端傳送到 SLS 資料庫。 如果該位置存在於 SLS 中，則位置資訊服務接著會將該位置傳送回用戶端。 
  
### <a name="to-configure-a-secondary-location-database"></a>若要設定次要位置資料庫

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行下列 Cmdlet 來設定次要位置資料庫位置的 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另請參閱

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

