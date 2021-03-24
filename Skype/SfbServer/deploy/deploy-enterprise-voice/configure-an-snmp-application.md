---
title: 在商務用 Skype Server 中設定 SNMP 應用程式
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 在商務用 Skype Server Enterprise Voice 中，設定 SNMP 應用程式來搭配 E9-1-1。
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103629"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 SNMP 應用程式
 
在商務用 Skype Server Enterprise Voice 中，設定 SNMP 應用程式來搭配 E9-1-1。 
  
商務用 Skype 伺服器包含標準的 web 服務介面，您可以用來將位置資訊服務連線至簡易網路管理通訊協定 (SNMP) 應用程式，該應用程式會與埠及切換資訊相符的 MAC 位址。 
  
如果已安裝 SNMP 應用程式，且 Location 資訊服務無法在位置資料庫中找到相符的位置，則位置資訊服務會自動使用用戶端所提供的 MAC 位址來查詢應用程式。 然後，位置資訊服務會使用 SNMP 應用程式傳回的埠及切換資訊，以重新查詢位置資料庫。
  
> [!NOTE]
> MAC 位址無法在執行 Windows 8 的電腦上使用。 
  
### <a name="to-configure-the-snmp-application-url"></a>設定 SNMP 應用程式 URL

1.  啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另請參閱

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)