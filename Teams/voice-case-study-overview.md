---
title: Teams 語音 Contoso 案例研究概觀
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
- highpri
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 適用于多國公司的 Teams 語音案例研究：語音移轉概觀
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b77cffa9bfa56ad445e948a4688e18e35118fd7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999478"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：Teams 語音移轉概觀

本文將介紹有關虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案的案例研究。

Contoso 已部署Microsoft 365 企業版並解決下列重要設計決策和實作詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從商務用 Skype升級 至 Teams、電話系統和音訊會議。  

本文著重于 Contoso 如何將內部部署使用者移轉到 Teams，以進行整合通訊、共同作業和語音溝通。 如需有關 Contoso 如何使用 Microsoft 雲端服務加速數位轉換的背景資訊，請參閱從 [Contoso 案例研究概觀](/microsoft-365/enterprise/contoso-case-study)開始的所有核心文章。

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

在核心文章中，您可以找到下列資訊：  

- Contoso 的 IT 基礎結構需求
- 網路
- Identity
- Windows 10 企業版
- Office 365專業增強版
- 行動裝置管理
- 資訊保護
- Microsoft 365 企業版安全性摘要
- 一個絕密專案的小組
- 適用于高度機密數位資產的 SharePoint Online 網站

如需規劃升級的相關資訊，建議您從 [開始使用 Microsoft Teams 升級](upgrade-start-here.md)開始。

## <a name="contoso-business-goals-for-teams"></a>Teams 的 Contoso 商務目標

若要將內部部署使用者移轉到 Teams 以進行整合通訊、共同作業和語音溝通，Contoso 決定下列商務目標：

- Teams 啟用 

  Contoso 的整合通訊和共同作業小組可讓 Teams 使用正確的原則來管理並啟用安全的內部和外部共同作業。 

- 從商務用 Skype 升級至 Teams 

  商務用 Skype廣泛部署在 Contoso 中。 由於需要移除舊版系統，Contoso 決定將其商務用 Skype使用者升級至 Teams。 如需詳細資訊，請參閱 [Contoso 案例研究：Teams 升級計畫](voice-case-study-migration-plan.md)。

- 電話系統  

  商務用 Skype企業語音已廣泛部署在 Contoso 中。 由於需要移除作為其中轉伺服器下一個躍點的舊版系統，Contoso 會將其商務用 Skype企業語音使用者移轉到電話系統。 Contoso 網站使用 Microsoft 通話方案、電話系統直接路由或兩者的組合。 如需詳細資訊，請參閱 [Contoso 案例研究：電話系統](voice-case-study-phone-system.md)。

- 依位置路由 

  由於辦公室位置位於受電話語音規範的國家/地區，Contoso 需要重新建立電話系統部署中商務用 Skype中出現的Location-Based路由。 如需詳細資訊，請參閱 [Contoso 案例研究：Location-Based路由]](voice-case-study-location-based-routing.md)。

- 緊急電話 

  實作直接路由的位置，Contoso 會與核准的協力廠商設定緊急通話。 如需詳細資訊，請參閱 [Contoso 案例研究：緊急通話](voice-case-study-emergency-calling.md)。

- 音訊會議 

  Contoso 會將裝載在其 SIP 主幹上的音訊會議服務號碼設定為 PSTN 提供者。 如需詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。 

- 本機媒體優化 

  Contoso 利用「本機媒體優化」的位置，其具有遠端網站所運用的 Microsoft Phone System 一條直接路由主幹。 如需詳細資訊，請參閱 [規劃本機媒體優化](direct-routing-media-optimization.md) 和 [設定本機媒體優化](direct-routing-media-optimization-configure.md)。

- 自動語音應答和通話佇列

  由於 Covid-19，Contoso 希望在員工遠端工作時提供接收者支援。 Contoso 使用自動語音應答和通話佇列來管理其接收者電話號碼的來電。 如需詳細資訊，請參閱 [Contoso 案例研究：自動語音應答和通話佇列](voice-case-study-call-queues.md)。
