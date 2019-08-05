---
title: 商務用 Skype Server 2019 已棄用的專案
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 這些功能已從商務用 Skype Server 2019 中移除。'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194048"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>商務用 Skype Server 2019 已棄用的專案

瞭解商務用 Skype Server 2019 中已過時的功能和功能。 如需商務用 Skype Server 2019 中新功能的相關資訊, 請參閱[商務用 Skype server 2019 中的內容](whats-new.md)。

在商務用 Skype Server 2019 中, 有一些更強調的功能, 可與舊版產品相容。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中已棄用的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>商務用 Skype Server 的 XMPP 閘道

商務用 Skype Server 2015 及其前置任務允許您在 Edge 伺服器上設定可擴展的訊息和目前狀態通訊協定 (XMPP) proxy, 以及前端伺服器或頂層端池中的 XMPP 閘道。 商務用 Skype Server 2019 已不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>商務用 Skype Server 的持續聊天

持續聊天伺服器是一個可讓貴組織中的多位使用者參與在一段時間內保留的聊天室交談的選擇性角色。 無法使用商務用 Skype Server 2019 來部署持續聊天。 此伺服器角色已從拓撲建立器以及程式碼中移除。 

團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。

### <a name="sql-mirroring-for-skype-for-business-server"></a>商務用 Skype Server 的 SQL 鏡像

無法使用商務用 Skype Server 2019 來部署 SQL 鏡像。 提供高可用性和災害復原的其他選項仍受到支援, 而且您應該在其中加以選擇。 請參閱[在商務用 Skype 伺服器中的高可用性和災難復原方案](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md), 以查看選項。

### <a name="in-place-upgrades"></a>就地升級 

商務用 Skype Server 2015 提供就地升級, 但商務用 Skype Server 2019 已不再支援。 並行升級及 coexistance 是受支援的, 請參閱[遷移至商務用 Skype Server 2019](migration/migration-to-skype-for-business-server-2019.md)以取得詳細資訊。

### <a name="mobility-service-mcx"></a>行動服務 (Mcx)

舊版行動用戶端使用的行動服務支援已不再提供給商務用 Skype Server 2019。 這是先前在商務用 Skype Server 2015 中宣告的。

所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 Mcx 的舊版用戶端的使用者將需要升級至目前的用戶端。

如需詳細資訊, 請參閱針對商務用 Skype 的[商務用 Skype Server 及行動](../SfbServer/plan-your-deployment/mobility.md)[用戶端功能比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)規劃。

## <a name="tools"></a>工具箱

在商務用 Skype Server 2019 初次發行時, 將無法使用下列工具:

- 商務用 Skype Server 容量規劃計算機
- 商務用 Skype Server 調試工具
- 商務用 Skype Server 資源套件工具 (某些工具將會被移除)
    - 呼叫 Parkometer
    - 查閱使用者主控台
    - 取消指派的號碼宣告遷移

商務用 Skype Server 2019 不支援下列工具:

- 通話品質方法 (但不是通話品質儀表板)
- Microsoft 通話品質方法計分卡, v 1。5
- 使用規劃工具設計 Lync Server 2013 的拓撲
- 商務用 Skype Server 2015 應力與效能工具

### <a name="see-also"></a>另請參閱

[商務用 Skype Server 2019 的新功能](whats-new.md)

[遷移 XMPP 同盟](migration/migrating-xmpp-federation.md)
