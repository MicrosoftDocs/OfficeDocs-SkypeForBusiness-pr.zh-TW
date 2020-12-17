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
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701221"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 案例研究：團隊語音遷移概覽

本文將針對虛構的多國企業（Contoso）如何針對其組織實施小組語音方案，提供案例研究。

Contoso 已部署 Microsoft 365 企業版並解決主要的設計決策及實現詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從商務用 Skype 升級至團隊、手機系統和音訊會議。  

本文重點說明 Contoso 如何將內部部署使用者遷移至小組，以進行整合溝通、共同作業及語音。 如需 Contoso 如何使用 Microsoft 的雲端服務加速其數位轉換的背景資訊，請參閱從 [Contoso 案例研究概覽](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)開始的所有核心文章。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

在核心文章中，您會發現下列資訊：  

- Contoso 的 IT 基礎結構需求
- 網
- Identity
- Windows 10 企業版
- Office 365 專業增強版
- 行動裝置管理
- 資訊保護
- Microsoft 365 企業安全性摘要
- 小組中的主要專案
- 高機密數位資產的 SharePoint Online 網站

如需規劃升級的相關資訊，您必須先開始進行 [Microsoft 團隊升級](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Contoso 企業團隊的商務目標

若要將內部部署使用者遷移至小組，以進行整合溝通、共同作業及語音作業，Contoso 決定下列業務目標：

- 團隊啟用 

  Contoso 的整合通訊與共同作業小組已啟用正確的原則來管理及啟用安全的內部與外部共同作業。 

- 從商務用 Skype 升級至 Teams 

  商務用 Skype 是在 Contoso 中廣泛部署。 如果您需要移出舊版系統，Contoso 決定將商務用 Skype 使用者升級至團隊。 如需詳細資訊，請參閱 [Contoso 案例研究：團隊升級方案](voice-case-study-migration-plan.md)。

- 電話系統  

  使用企業語音的商務用 Skype 已在 Contoso 中廣泛部署。 如果您需要移離其中繼伺服器下一個躍點的舊版系統，Contoso 已將商務用 Skype 企業語音使用者遷移至 [電話系統]。 Contoso 網站使用 Microsoft 通話方案、電話系統直傳送或兩者的組合。 如需詳細資訊，請參閱 [Contoso 案例研究： [電話系統](voice-case-study-phone-system.md)]。

- 依位置路由 

  在電話管控國家/地區的 office 位置，Contoso 需要在手機系統部署中，重新建立在商務用 Skype 中所提供的 Location-Based 路由。 如需詳細資訊，請參閱 [Contoso 案例研究： Location-Based 路由](voice-case-study-location-based-routing.md)。

- 緊急電話 

  在直接佈線已實施的位置，Contoso 利用核准的協力廠商設定緊急通話。 如需詳細資訊，請參閱 [Contoso 案例研究：緊急通話](voice-case-study-emergency-calling.md)。

- 音訊會議 

  Contoso 將其 SIP 主幹上託管的音訊會議服務號碼設定為 PSTN 提供者。 如需詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。 

- 本機媒體優化 

  Contoso 利用本機媒體優化功能，可讓他們將一個直接路由主幹移至遠端網站所利用的 Microsoft Phone 系統。 如需詳細資訊，請參閱 [規劃本機媒體優化](direct-routing-media-optimization.md) 並 [設定本機媒體優化](direct-routing-media-optimization-configure.md)。

- 自動語音應答及呼叫佇列

  Covid-19 之後，Contoso 想要在員工進行遠端作業時提供接待員支援。 Contoso 使用自動語音應答及呼叫佇列，管理來電的電話號碼。 如需詳細資訊，請參閱 [Contoso 案例研究：自動語音應答及呼叫佇列](voice-case-study-call-queues.md)。  


