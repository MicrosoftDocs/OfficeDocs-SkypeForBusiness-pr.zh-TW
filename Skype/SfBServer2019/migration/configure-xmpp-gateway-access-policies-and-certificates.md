---
title: 設定 XMPP 閘道的存取原則和憑證
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定（XMPP）定義外部部署。 XMPP 設定可讓使用者依下列方式存取 XMPP 網域使用者：
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753933"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>設定 XMPP 閘道的存取原則和憑證

XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定（XMPP）定義外部部署。 XMPP 設定可讓使用者依下列方式存取 XMPP 網域使用者：
  
- IM 和目前狀態-僅限人員
    
- 在商務用 Skype 用戶端中建立 XMPP 同盟連絡人
    
當您設定支援 XMPP 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用到會話初始通訊協定（SIP）立即訊息（IM）服務提供者或 SIP 同盟網域的使用者。 您可以為每個 XMPP 同盟網域設定 XMPP 同盟協力廠商，讓您的使用者能夠新增連絡人及與其通訊。 原則就緒後，您必須設定 XMPP 閘道憑證。 
  
> [!NOTE]
> XMPP 功能在商務用 Skype Server 2019 中已被取代，但可以繼續使用與商務用 Skype Server 2019 共存的舊版伺服器。 請確認您已部署舊版伺服器（商務用 Skype Server 2015/Lync Server 2013） XMPP 閘道，並設定存取原則以啟用舊版 XMPP 閘道的使用者。 如需詳細資訊，請參閱[遷移 XMPP 同盟](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>設定外部存取原則以允許使用者使用舊版 XMPP 閘道

1. 開啟舊版商務用 Skype Server [控制台]。
    
2. 在左導覽列中，按一下 [**同盟和外部存取**]，然後按一下 [**外部存取原則**]。
    
3. 依序按一下 **[新增]** 和 **[使用者原則]**。
    
4. 輸入外部存取使用者原則的名稱。
    
5. 提供外部存取使用者原則的描述。
    
6. 選取 [啟用與同盟使用者的通訊]****。
    
7. 選取 [啟用與 XMPP 同盟使用者的通訊]****。
    
8. 按一下 [認可]**** 以儲存對網站或使用者原則的變更。 
    

