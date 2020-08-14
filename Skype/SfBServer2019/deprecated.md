---
title: 商務用 Skype Server 2019 中已被取代的功能
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：這些功能已從商務用 Skype Server 2019 中移除。
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125216"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中已被取代的功能

深入瞭解商務用 Skype Server 2019 中已被取代的功能。 如需商務用 Skype Server 2019 中新功能的相關資訊，請參閱 [商務用 Skype server 2019](whats-new.md)。

商務用 Skype Server 2019 中包含一些已加重的功能，與舊版產品的相容性。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中已被取代的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>商務用 Skype Server 的 XMPP 閘道

商務用 Skype Server 2015 及其前置任務可讓您設定可延伸的訊息和顯示狀態通訊協定 (XMPP Edge Server 上的) proxy，以及前端伺服器或前端集區上的 XMPP 閘道。 商務用 Skype Server 2019 已不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>商務用 Skype Server 的持續聊天

Persistent Chat Server 是一種選用角色，可讓您組織中的多位使用者參與隨時間持續的聊天室交談。 無法使用商務用 Skype Server 2019 部署持續性聊天。 此伺服器角色會從拓撲產生器和程式碼中移除。 

小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。

### <a name="sql-mirroring-for-skype-for-business-server"></a>商務用 Skype Server 的 SQL 鏡像

無法使用商務用 Skype Server 2019 部署 SQL 鏡像。 仍支援其他提供高可用性和嚴重損壞修復的選項，因此您應從這些選項中加以選擇。 請參閱 [規劃商務用 Skype Server 中的高可用性和嚴重損壞修復](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) ，以查看選項。

### <a name="in-place-upgrades"></a>就地升級 

您可以在商務用 Skype 2015 Server 中取得就地升級，但在商務用 Skype Server 2019 中已不再支援就地升級。 支援並排升級和 coexistance，請參閱 [遷移至商務用 Skype Server 2019](migration/migration-to-skype-for-business-server-2019.md) 以取得詳細資訊。

### <a name="mobility-service-mcx"></a>行動服務 (Mcx) 

商務用 Skype Server 2019 不再提供舊版行動用戶端所使用的行動服務支援。 這是先前在商務用 Skype Server 2015 中宣佈的宣告。

所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 Mcx 之舊版用戶端的使用者，必須升級至目前的用戶端。

如需詳細資訊，請參閱為商務用 Skype 進行[商務用 Skype Server 和行動](../SfbServer/plan-your-deployment/mobility.md)[用戶端功能比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)的計畫。

## <a name="tools"></a>工具

下列工具在初次發行商務用 Skype Server 2019 時不可使用：

- 商務用 Skype Server 容量規劃計算機
- 商務用 Skype Server 調試工具
- 商務用 Skype 伺服器資源套件工具 (將會移除某些工具) 
    - 呼叫 Call parkometer
    - 查閱使用者主控台
    - 未指派號碼宣告遷移

商務用 Skype Server 2019 不支援下列工具：

- 通話品質方法 (，但未呼叫品質儀表板) 
- Microsoft 通話品質方法計分卡，v 1。5
- 商務用 Skype Server 2015 規劃工具
- 商務用 Skype Server 2015 應力和效能工具

### <a name="see-also"></a>另請參閱

[商務用 Skype Server 2019 的新功能](whats-new.md)

[移轉 XMPP 同盟](migration/migrating-xmpp-federation.md)
