---
title: Teams Contoso 案例研究概觀
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
description: Teams多國公司的語音案例研究：語音移移概觀
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae8a09ab48215b1915c06e46b3d6a3a693958621
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587172"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams語音移移概觀

本文介紹一個案例分析，瞭解一家虛構的多國公司 Contoso 如何為組織Teams語音解決方案。

Contoso 已部署 Microsoft 365 企業版，並解決下列主要設計決策和實現詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從 商務用 Skype 升級至 Teams、電話系統 和音訊會議。  

本文著重說明 Contoso 如何將內部部署使用者移Teams統一通訊、共同合作和語音。 有關 Contoso 如何使用 Microsoft 雲端服務加速其數位轉換的背景資訊，請參閱從 [Contoso](/microsoft-365/enterprise/contoso-case-study)案例研究概觀開始的所有核心文章。

[https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

在核心文章中，您可以找到下列相關資訊：  

- Contoso 的 IT 基礎結構需求
- 網路
- Identity
- Windows 10 企業版
- Office 365 Pro加號
- 行動裝置管理
- 資訊保護
- 安全性Microsoft 365 企業版摘要
- 最高機密專案的小組
- SharePoint高度機密數位資產的線上網站

若要取得規劃升級的資訊，您首先想要從快速入門[開始Microsoft Teams升級](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Contoso 商務目標Teams

若要將內部部署使用者遷移到Teams通訊、共同合作和語音，Contoso 決定下列商業目標：

- Teams啟用 

  Contoso 的一致通訊和共同Teams提供正確的政策，以管理及啟用安全的內部和外部共同合作。 

- 從商務用 Skype 升級至 Teams 

  商務用 Skype在 Contoso 中廣泛部署。 由於需要移轉舊版系統，Contoso 決定將其使用者商務用 Skype升級Teams。 詳細資訊，請參閱[Contoso 案例研究：Teams方案](voice-case-study-migration-plan.md)。

- 電話系統  

  商務用 Skype企業語音功能廣泛部署在 Contoso 中。 由於需要將舊版系統移轉為中繼伺服器的下一個躍點，Contoso 將其商務用 Skype企業語音使用者移電話系統。 Contoso 網站使用 Microsoft 通話方案、電話系統直接路由，或兩者的組合。 詳細資訊，請參閱[Contoso 案例研究：電話系統。](voice-case-study-phone-system.md)

- 依位置路由 

  在受電話規範的國家/地區擁有辦公室位置，Contoso 需要重新Location-Based部署中目前商務用 Skype路由電話系統路由。 詳細資訊，請參閱 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。

- 緊急電話 

  在已執行直接路由的地方，Contoso 會與核准的協力廠商設定緊急電話。 詳細資訊，請參閱 [Contoso 案例研究：緊急電話](voice-case-study-emergency-calling.md)。

- 音訊會議 

  Contoso 會設定其 SIP 主幹上託管至 PSTN 提供者的音訊會議服務號碼。 詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。 

- Local Media 優化 

  Contoso 在有一個直接路由主幹至遠端網站所Microsoft 電話系統的位置，運用了 Local Media 優化。 詳細資訊，請參閱規劃本地[媒體優化和](direct-routing-media-optimization.md)[設定本地媒體優化](direct-routing-media-optimization-configure.md)。

- 自動電話機和通話佇列

  由於 Covid-19，Contoso 想要在員工遠端工作期間提供接待員支援。 Contoso 使用自動電話機和通話佇列來管理接收者電話號碼的來電。 詳細資訊，請參閱 [Contoso 案例研究：自動總機和通話佇列](voice-case-study-call-queues.md)。
