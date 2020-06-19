---
title: 團隊語音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785972"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 案例研究：團隊升級方案

在決定要從商務用 Skype 遷移至團隊時，Contoso 想要為使用者提供簡易轉場體驗。 他們決定要設定混合式連線，並使用重迭的功能方法將使用者移至團隊，而不是同時將每個人切換至團隊。 這可讓團隊和商務用 Skype 內部部署的使用者分享目前狀態並進行通訊。 當使用者進入電話系統的試用版時，他們會移至 [僅限團隊] 模式。

若要瞭解有關升級、方法和模式的基本概念，Contoso 請閱讀下列文章：

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [從商務用 Skype 升級至 Teams](upgrade-to-teams-on-prem-overview.md) 
- [遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso 也參與了 Ignite 2019 會話，[設計從商務用 Skype 至團隊的路徑](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。 Contoso 已瞭解：

- 互通性、同盟和升級行為等基本概念 

- 共存模式與以 TeamsUpgradePolicy 為基礎的管理 

- 最終使用者體驗： 

  - 聊天與通話 

  - 會議排程 

  - 團隊用戶端中的共同作業功能可用性 

若要規劃及設定混合式連線性，請先將其內部部署環境移至雲端、Contoso 讀取[規劃混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)並[設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)，以瞭解如何進行下列作業： 

  - 將其內部部署環境服務設定為與 Office 365 聯盟。 

  - 將其內部部署環境設定為信任 Office 365，並啟用 Office 365 共用的 SIP 位址空間 

  - 在其 Office 365 租使用者中啟用共用的 SIP 位址空間。

  - 在技術試驗期間使用孤島模式。

  - 使用者啟用電話系統之後，就能將使用者切換成 TeamsOnly 模式。 TeamsOnly 模式是通話方案和直接路由所必需的。 
