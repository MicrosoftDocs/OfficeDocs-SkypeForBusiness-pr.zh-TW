---
title: 設定 Skype 會議廣播的內部部署部署
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要：瞭解為內部部署商務用 Skype Server 混合部署執行的 Skype 會議廣播所需執行的步驟。
ms.openlocfilehash: 6cab2ed4fbb5cb2992b970d5a960bbc0ad2e10af2184588aa6c938e9811d2a50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304485"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>設定 Skype 會議廣播的內部部署部署
 
**摘要：** 深入瞭解為內部部署商務用 Skype Server 混合式部署所需執行的 Skype 會議廣播進行設定的步驟。
  
Skype會議廣播是 Office 365 的一部分線上服務。 如果您正在執行商務用 Skype Server 內部部署，且想要在您的環境中使用 Skype 會議廣播，您必須遵循本主題中的設定步驟。 開始之前，您的環境必須設定為與商務用 Skype 線上的混合使用。 如需詳細資訊，請參閱[Plan 商務用 Skype Server 和商務用 Skype online 之間的混合式連線](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)，以及[在商務用 Skype Server 和商務用 Skype 線上之間部署混合式連線](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>設定 Skype 會議廣播的混合式環境

您必須執行下列動作來準備您的環境，以供 Skype 會議廣播：
  
- 設定與商務用 Skype 線上資源的同盟
    
- 設定 SIP 同盟網域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>設定與商務用 Skype 線上資源的同盟

若要啟用與商務用 Skype 線上資源的同盟，您必須設定 SIP 同盟提供者的外部存取。 若要使用商務用 Skype Server 控制台執行這項作業，請遵循下列步驟：
  
1. 啟動商務用 Skype Server 控制台，然後選取左側的 [**外部存取**]。
    
2. 選取 [ **SIP 同盟提供者** ]，然後按一下 [ **新增**]。
    
3. 使用下列設定來設定新的提供者：
    
|||
|:-----|:-----|
|**啟用與此提供者的通訊：** <br/> |已選取  <br/> |
|**提供者名稱：** <br/> |LyncOnlineResources  <br/> |
|**Access Edge service (FQDN) ：** <br/> |sipfed.resources.lync.com  <br/> |
|**預設驗證層級：** <br/> |允許使用者與使用此提供者的所有人進行通訊。  <br/> |
   
您也可以在商務用 Skype Server 管理命令介面中執行下列 Cmdlet，以啟用商務用 Skype 線上資源的同盟：
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>設定 SIP 同盟網域

接下來，您必須將 SIP 同盟網域新增至允許的網域清單。 針對所列的每個網域重複這些步驟，以建立4個新的 SIP 同盟網域。 這些網域包括在商務用 Skype 線上使用的區域資料中心。
  
1. 啟動商務用 Skype Server 控制台，然後選取左側的 [**外部存取**]。
    
2. 選取 [ **SIP 同盟網域** ]，然後按一下 [ **新增**]。
    
3. 針對 [ **功能變數名稱 (] 或 [FQDN) ：**]，輸入網域，針對下列每個網域重複此程式：
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
您也可以在商務用 Skype Server 管理命令介面中執行下列 Cmdlet，以設定 SIP 同盟網域的外部存取：
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

完成這些設定步驟之後，您就可以開始在部署中使用 Skype 會議廣播。 如需 Skype 會議廣播的詳細資訊，請參閱[什麼是 Skype 會議廣播？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 會議廣播管理員指南](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。
