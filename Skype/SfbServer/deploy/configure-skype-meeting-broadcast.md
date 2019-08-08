---
title: 針對 Skype 會議廣播設定內部部署部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '摘要: 瞭解針對內部部署商務用 Skype Server 混合式部署所需執行的步驟, 以設定 Skype 會議廣播。'
ms.openlocfilehash: bd87c64dd1e54c8092186a3e233557ebd11eec77
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234583"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>針對 Skype 會議廣播設定內部部署部署
 
**摘要:** 瞭解針對您的內部部署商務用 Skype Server 混合式部署所需執行的步驟, 以設定 Skype 會議廣播。
  
Skype 會議廣播是 Office 365 中的一種線上服務。 如果您在內部部署執行商務用 Skype Server, 且想要在您的環境中使用 Skype 會議廣播, 您必須遵循本主題中的設定步驟。 在您開始之前, 您的環境必須設定為與商務用 Skype Online 混合使用。 如需詳細資訊, 請參閱[規劃商務用 Skype server 與商務用 Skype online 之間的混合式連接](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json), 以及[在商務用 Skype server 和商務用 Skype online 之間部署混合式連線](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>針對 Skype 會議廣播設定您的混合式環境

您必須執行下列動作, 才能為您的 Skype 會議廣播準備您的環境:
  
- 設定與商務用 Skype Online 資源的同盟
    
- 設定 SIP 聯盟網域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>設定與商務用 Skype Online 資源的同盟

若要啟用與商務用 Skype Online 資源的同盟, 您必須為 SIP 聯盟提供者設定外部存取。 若要使用商務用 Skype Server 的 [控制台] 執行此動作, 請依照下列步驟執行:
  
1. 啟動商務用 Skype Server 的 [控制台], 然後選取左側的 [**外部存取**]。
    
2. 選取**SIP 聯盟提供者**, 然後按一下 [**新增**]。
    
3. 使用下列設定來設定新的提供者:
    
|||
|:-----|:-----|
|**啟用與此提供者的通訊:** <br/> |選定  <br/> |
|**提供者名稱:** <br/> |LyncOnlineResources  <br/> |
|**存取邊緣服務 (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**預設驗證層級:** <br/> |允許使用者與使用這個提供者的每個人進行通訊。  <br/> |
   
您也可以在商務用 skype Server Management Shell 中執行下列 Cmdlet, 在商務用 Skype Online 資源中啟用同盟:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>設定 SIP 聯盟網域

接下來, 您需要將 SIP 聯盟網域新增到 [允許的網域] 清單。 針對列出的每個網域重複這些步驟, 建立4個新的 SIP 聯盟網域。 這些網域包括適用于商務用 Skype Online 中的地區資料中心。
  
1. 啟動商務用 Skype Server 的 [控制台], 然後選取左側的 [**外部存取**]。
    
2. 選取 [ **SIP 聯盟網域**], 然後按一下 [**新增**]。
    
3. 針對**功能變數名稱 (或 FQDN):**, 請輸入網域, 並針對下列每個網域重複此程式:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
您也可以在商務用 Skype Server Management Shell 中執行下列 Cmdlet, 以設定 SIP 聯盟網域的外部存取:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

完成這些設定步驟之後, 您就可以開始在您的部署中使用 Skype 會議廣播了。 如需 Skype 會議廣播的詳細資訊, 請參閱[什麼是 Skype 會議廣播？](https://go.microsoft.com/fwlink/?LinkId=617071)和[skype 會議廣播系統管理指南](https://go.microsoft.com/fwlink/?LinkId=617075)。
  

