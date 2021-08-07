---
title: 在商務用 Skype Server 中設定次要位置資訊服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 針對商務用 Skype Server 企業語音中的 E9-1-1，設定次要位置來源 (SLS) 資料庫。
ms.openlocfilehash: 9fe548c30dd7f90f854143a9d3e8261214f9c837a692a0afe07173ac98a730b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305895"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>在商務用 Skype Server 中設定次要位置資訊服務
 
針對商務用 Skype Server 企業語音中的 E9-1-1，設定次要位置來源 (SLS) 資料庫。 
  
商務用 Skype Server 提供 web 服務介面，您可以用來將位置資訊服務指向次要位置來源， (SLS) 資料庫。 連接至 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。 如果已設定位置資料庫和次要位置資料庫，則位置資訊服務會先查詢位置資料庫，如果找不到相符的位置，就會將位置要求從用戶端傳送至 SLS 資料庫。 如果該位置存在於 SLS 中，則位置資訊服務會將該位置傳回用戶端。 
  
### <a name="to-configure-a-secondary-location-database"></a>設定次要位置資料庫

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列 Cmdlet 以設定次要位置資料庫的位置 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另請參閱

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)