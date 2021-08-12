---
title: Teams僅模式考慮事項
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 系統管理員可以瞭解如何在系統管理中心Microsoft Teams升級至 Microsoft Teams模式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: da61c6fdda511375010375a785fc06c3549883bf56396fc87daaadb4472cf2af
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312541"
---
# <a name="teams-only-mode-considerations"></a>Teams僅模式考慮事項

組織或Microsoft 365 Office 365系統管理員可以將個別使用者或整個租使用者升級Teams模式。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

升級至 Teams 模式可透過單一用戶端體驗，為使用者提供 Microsoft Teams 的完整權益，Microsoft 365或 Office 365 團隊合作中心。 在 Teams 模式的使用者，無論寄件者是使用 商務用 Skype 或 Teams，都會在 Teams 中接聽所有通話和聊天，並受益于交互操作和聯盟支援。

雖然有數千名客戶已成功升級至 Microsoft Teams，但有些考慮可能會影響貴組織的升級時程表和使用者體驗。 為了獲得最佳使用者體驗，請確認 Teams 符合您的共同作業與通訊需求，並確認您的網路已準備好可支援 Teams，並在將使用者升級至 Teams 之前，先進行您的使用者整備計劃。 

> [!IMPORTANT]
> 如果您剛開始進行升級規劃，請務必參考我們的升級指南Microsoft Teams[入門](upgrade-start-here.md)。 

**共存考慮：** 已經使用 商務用 Skype Online 和/或 商務用 Skype Server 的組織Teams以符合其需求的速度，將應用程式引入環境。 組織可根據需要將 Teams逐步推出至想要的使用者集，而使用 Teams 的使用者可以與使用 商務用 Skype 的使用者通訊，反之亦然。 若要管理此體驗，系統管理員會使用共存模式，定義使用者用戶端體驗、傳入聊天和通話的路由行為，以及是否要在 Teams 或 商務用 Skype 中排程新會議。 如果使用者升級為只升級為 **Teams，使用者可以與其他組織中的使用者進行Teams。** 不過，當兩個使用者使用 Teams。 升級至僅Teams的使用者仍然可以加入商務用 Skype會議。 

> [!IMPORTANT]
> 如需有關共存的詳細資訊，請參閱瞭解Microsoft Teams[及商務用 Skype互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 如要進一Teams與Skype (消費者) ，請參閱Teams[及Skype互通性](teams-skype-interop.md)。


**使用者特定考慮**：某些使用者案例仍在演進中，系統管理員可能會決定暫時延後特定使用者的升級，同時升級組織的其他使用者。 特別是，我們仍在處理主要裝置為 VDI 的使用者案例。 針對網站公告，請監控 Microsoft 365[藍圖](https://www.microsoft.com/microsoft-365/roadmap)。

> [!NOTE]
> 在移至僅Teams模式之前，您需要取代或更新不支援此Teams。 

> [!IMPORTANT]
> **請記住**：移轉Teams移轉並不僅僅是技術移轉。 成功的升級會評估技術準備狀態和使用者準備狀態。 請閱商務用 Skype升級Teams指南，以進一[](upgrade-framework.md)步規劃升級至Teams。  
