---
title: 在商務用 Skype Server 中設定 SNMP 應用程式
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 在商務用 Skype Server Enterprise Voice 中，將 SNMP 應用程式設定為使用 E9-1-1。
ms.openlocfilehash: fd8db117f590343d3e2f5a0194a0f6d8c3bcfb39
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768136"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 SNMP 應用程式
 
在商務用 Skype Server Enterprise Voice 中，將 SNMP 應用程式設定為使用 E9-1-1。 
  
商務用 Skype 伺服器包含標準的 web 服務介面，您可以用來將位置資訊服務連線至與埠和交換器資訊相符的 MAC 位址的簡單網路管理通訊協定（SNMP）應用程式。 
  
如果已安裝 SNMP 應用程式，且位置資訊服務無法在位置資料庫中找到相符的專案，位置資訊服務會使用用戶端提供的 MAC 位址來自動查詢應用程式。 然後，位置資訊服務會使用 SNMP 應用程式傳回的埠和切換資訊來重新查詢位置資料庫。
  
> [!NOTE]
> MAC 位址無法在執行 Windows 8 的電腦上使用。 
  
### <a name="to-configure-the-snmp-application-url"></a>若要設定 SNMP 應用程式 URL

1.  啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另請參閱

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

