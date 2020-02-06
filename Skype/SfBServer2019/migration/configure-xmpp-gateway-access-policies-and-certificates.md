---
title: 設定 XMPP 閘道存取原則及憑證
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。 XMPP 設定可讓使用者透過以下方式存取 XMPP 網域使用者：
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813761"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>設定 XMPP 閘道存取原則及憑證

XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。 XMPP 設定可讓使用者透過以下方式存取 XMPP 網域使用者：
  
- IM 和目前狀態-僅限人員的人員
    
- 在商務用 Skype 用戶端中建立 XMPP 同盟連絡人
    
當您設定 XMPP 聯盟夥伴支援的原則時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者或 SIP 聯盟網域的使用者。 您可以針對每個 XMPP 聯盟網域設定 XMPP 聯盟夥伴，以允許使用者新增連絡人並與之通訊。 原則就緒之後，您必須設定 XMPP 閘道憑證。 
  
> [!NOTE]
> 在商務用 Skype Server 2019 中已棄用 XMPP 功能，但在舊版伺服器與商務用 Skype Server 2019 共存的情況下，仍可繼續使用。 請確定您已部署舊版伺服器（商務用 Skype Server 2015/Lync Server 2013） XMPP 閘道，並將訪問原則設定為允許使用者使用舊版 XMPP 閘道。 如需詳細資訊，請參閱[遷移 XMPP 同盟](migrating-xmpp-federation.md)。 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>設定外部存取原則，以允許使用者使用舊版 XMPP 閘道

1. 開啟舊版商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**外部存取原則**]。
    
3. 依序按一下 [新增]**** 和 [使用者原則]****。
    
4. 輸入外部存取使用者原則的名稱。
    
5. 提供外部存取使用者原則的描述。
    
6. 選取 [**啟用與聯盟使用者的通訊**]。
    
7. 選取 [**啟用與 XMPP 聯盟使用者的通訊**]。
    
8. 按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。 
    

