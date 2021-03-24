---
title: Teams Voice Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097489"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams 語音移移概觀

本文介紹一個案例分析，瞭解一家虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案。

Contoso 已部署 Microsoft 365 企業版，並針對下列專案解決主要設計決策和實現詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從商務用 Skype 升級到 Teams、電話系統及音訊會議。  

本文著重說明 Contoso 如何將內部部署使用者移遷移到 Teams，以便進行統一通訊、共同合作和語音。 有關 Contoso 如何使用 Microsoft 雲端服務加速其數位轉換的背景資訊，請參閱從 [Contoso](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)案例研究概觀開始的所有核心文章。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

在核心文章中，您可以找到下列相關資訊：  

- Contoso 的 IT 基礎結構需求
- 網路
- Identity
- Windows 10 企業版
- Office 365 專業增強版
- 行動裝置管理
- 資訊保護
- Microsoft 365 企業版安全性摘要
- 最高機密專案的小組
- 適用于高度機密數位資產的 SharePoint Online 網站

若要取得規劃升級的資訊，您首先想要從 Microsoft Teams 升級快速 [入門開始](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Teams 的 Contoso 商務目標

若要將內部部署使用者遷移到 Teams 以進行統一通訊、共同合作和語音，Contoso 決定下列商業目標：

- Teams 啟用 

  Contoso 的一致通訊和共同合作小組可讓 Teams 擁有正確的政策，以管理及啟用安全的內部和外部共同合作。 

- 從商務用 Skype 升級至 Teams 

  商務用 Skype 已廣泛部署在 Contoso 中。 由於需要移轉舊版系統，Contoso 決定將其商務用 Skype 使用者升級至 Teams。 詳細資訊，請參閱 [Contoso 案例研究：Teams 升級計畫](voice-case-study-migration-plan.md)。

- 電話系統  

  具有企業語音的商務用 Skype 已廣泛部署在 Contoso 中。 由於需要將舊版系統移轉為中繼伺服器的下一個躍點，Contoso 將其商務用 Skype 企業語音使用者移轉至電話系統。 Contoso 網站使用 Microsoft 通話方案、電話系統直接路由或兩者的組合。 詳細資訊，請參閱 [Contoso 案例研究：Phone System](voice-case-study-phone-system.md)。

- 依位置路由 

  在受電話語音規範的國家/地區擁有辦公室位置，Contoso 需要重新Location-Based電話系統部署中目前存在於商務用 Skype 的路由。 詳細資訊，請參閱 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。

- 緊急電話 

  在已執行直接路由的地方，Contoso 會與核准的協力廠商設定緊急電話。 詳細資訊，請參閱 [Contoso 案例研究：緊急電話](voice-case-study-emergency-calling.md)。

- 音訊會議 

  Contoso 會設定其 SIP 主幹上託管至 PSTN 提供者的音訊會議服務號碼。 詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。 

- Local Media 優化 

  Contoso 在有一個直接路由主幹到由遠端網站所利用的 Microsoft Phone System 位置，運用了 Local Media 優化。 詳細資訊，請參閱[規劃本地媒體優化和](direct-routing-media-optimization.md)[設定本地媒體優化](direct-routing-media-optimization-configure.md)。

- 自動電話機和通話佇列

  由於 Covid-19，Contoso 想要在員工遠端工作期間提供接待員支援。 Contoso 使用自動電話機和通話佇列來管理接收者電話號碼的來電。 詳細資訊，請參閱 [Contoso 案例研究：自動總機和通話佇列](voice-case-study-call-queues.md)。