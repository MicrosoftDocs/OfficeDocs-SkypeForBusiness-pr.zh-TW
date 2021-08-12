---
title: 商務用 Skype Server 2019 已被取代的功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：這些功能已從商務用 Skype Server 2019 中移除。
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282466"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>商務用 Skype Server 2019 已被取代的功能

深入瞭解商務用 Skype Server 2019 中已被取代的功能。 如需商務用 Skype Server 2019 中新功能的詳細資訊，請參閱[商務用 Skype Server 2019 中的內容](whats-new.md)。

商務用 Skype Server 2019 中包含一些已加重的功能，與舊版產品的相容性。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中已被取代的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>商務用 Skype Server 的 XMPP 閘道

商務用 Skype Server 2015 及其前置任務可讓您在 Edge server 上設定可延伸的訊息和顯示狀態通訊協定 (XMPP) proxy，或前端伺服器或前端集區上的 XMPP 閘道。 商務用 Skype Server 2019 中已不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>商務用 Skype Server 的持續聊天

Persistent Chat Server 是一種選用角色，可讓您組織中的多位使用者參與隨時間持續的聊天室交談。 無法使用商務用 Skype Server 2019 部署 Persistent 聊天。 此伺服器角色會從拓撲產生器和程式碼中移除。 

Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL商務用 Skype Server 的鏡像

SQL無法使用商務用 Skype Server 2019 部署鏡像。 仍支援其他提供高可用性和嚴重損壞修復的選項，因此您應從這些選項中加以選擇。 請參閱[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)，以複查選項。

### <a name="in-place-upgrades"></a>就地升級 

就地升級可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 支援並排升級和 coexistance，請參閱[遷移至商務用 Skype Server 2019](migration/migration-to-skype-for-business-server-2019.md)以取得詳細資訊。

### <a name="mobility-service-mcx"></a>行動服務 (Mcx) 

舊版行動用戶端所使用的行動服務支援已不再供應商務用 Skype Server 2019。 這先前在商務用 Skype Server 2015 中宣佈。

所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 Mcx 之舊版用戶端的使用者，必須升級至目前的用戶端。

如需詳細資訊，請參閱 Plan for Mobile [for 商務用 Skype Server](../SfbServer/plan-your-deployment/mobility.md)和[Mobile client feature 商務用 Skype 的比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。

## <a name="tools"></a>工具

在最初版本的商務用 Skype Server 2019 上，將無法使用下列工具：

- 商務用 Skype Server 容量規劃電腦
- 商務用 Skype Server調試工具
- 商務用 Skype Server資源工具組工具 (將移除某些工具) 
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
